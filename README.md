metagenomics
============

Analysis of Xiangming's metagenome data
Directory is currently projects/metagenomics/run_july2014
Make sure you have the github library in your path

Step 1 
Process the files

process_files.sh short.txt

Step 2

Get the file list

ls | while read i; do echo $i | sed -e "s/_001.fastq.gz//"; done > names.txt


Step 3
Ensure the test.txt document is in the working directory
Run the metagenomics workflow

nohup metagenomics_analysis.sh names.txt ../working_databases/custom_qiime.txt ../working_databases/custom.fasta &


-------------custom database preparation
In the database folder projects/metagenomics/database I ran

database_maker_v2.pl ./consensus/consensus.fasta custom.fasta custom_qiime.txt

which created the files in the database folder

I copied these to the working databases folder for clarity. 






