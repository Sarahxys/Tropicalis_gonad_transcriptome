Since I can install Trinity 2.8 and 2.7 after multiple tries, I decide to go with version 2.5.1 on info. 
```bash
export PATH="$PATH:/home/xue/software/bowtie2-2.3.4.3";export PATH="$PATH:/home/xue/software/bowtie2-2.3.4.3/bowtie2-build";export PATH="$PATH:/home/xue/software/bowtie2-2.3.4.3/bowtie2-inspect";time /home/xue/software/trinityrnaseq-Trinity-v2.5.1/Trinity --seqType fq  --left /home/xue/tropicalis_gonad_transcriptome_Dec2018/trim/XT_R1.fastq.gz --right /home/xue/tropicalis_gonad_transcriptome_Dec2018/trim/XT_R2.fastq.gz --CPU 20 --inchworm_cpu 6 --full_cleanup --max_memory 200G --min_kmer_cov 2 --output /home/xue/tropicalis_gonad_transcriptome_Dec2018/tropicali_gonad_transcriptome_trinityOut;echo "trinity done in screen tropicalis_gonad on info114"|mail songxy2@mcmaster.ca


```



Graham alread have the newest version of Trinity (Trinity 2.8.4) installed, I am running the newest verion on Graham.

