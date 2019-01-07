Since I can install Trinity 2.8 and 2.7 after multiple tries, I decide to go with version 2.5.1 on info. 
```bash
export PATH="/home/xue/software/bowtie2-2.3.4.3:$PATH";time /home/xue/software/trinityrnaseq-Trinity-v2.5.1/Trinity --seqType fq  --left /home/xue/tropicalis_gonad_transcriptome_Dec2018/trim/XT_R1.fastq.gz --right /home/xue/tropicalis_gonad_transcriptome_Dec2018/trim/XT_R2.fastq.gz --CPU 20 --inchworm_cpu 6 --full_cleanup --max_memory 200G --min_kmer_cov 2 --output /home/xue/tropicalis_gonad_transcriptome_Dec2018/tropicali_gonad_transcriptome_trinityOut;echo "trinity done in screen tropicalis_gonad on info114"|mail songxy2@mcmaster.ca
```

Graham alread have the newest version of Trinity (Trinity 2.8.4) installed, I am running the newest verion on Graham with the below bash script.
```
```
It ran for a little bit more than 1 days with max 191Gb of memories. Much shorter time than I expected. 

# Mapping to *X.tropicalis* genome (v91)
I mapped the *de novo* assembled tropicalis transcriptome to the tropicalis genome (v91) using gmap on Graham. 
```
#downloading the genome 
wget ftp://ftp.xenbase.org/pub/Genomics/JGI/Xentr9.1/XT9_1.fa.gz

#indexing
gmap_build -d db_gmap_tropicalis_v91/ -D /home/songxy/scratch/tropicalis_transcriptome/tropicalis_genome/db_gmap_tropicalis_v91 -g /home/songxy/scratch/tropicalis_transcriptome/tropicalis_genome/XT9_1.fa.gz


#mapping 
time gmap -D /home/songxy/scratch/tropicalis_transcriptome/tropicalis_genome/db_gmap_tropicalis_v91 -d db_gmap_tropicalis_v91 -A -B 5 -t 15 -f samse /home/songxy/scratch/tropicalis_transcriptome/transcriptome_building/tropicalis_transcriptome_trinityOut.Trinity.SuperTrans.fasta | samtools view -S -b > /home/songxy/scratch/tropicalis_transcriptome/mapping_transcriptome_to_genome/tropicalis_denovoT_tropicalisv91_genome_gmap.bam


```

