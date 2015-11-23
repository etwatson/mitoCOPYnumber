#README  
##mitoCOPYnumber   
Estimate the copy number of mitochondrial genomes from mapped reads (BAM).   
##Prerequisites
- BBMAP
- Perl 5.8 or higher
- R 2.7 or higher
- samtools  
##Pipeline
1. map reads to mitochondrial and nuclear genome using BBSPLIT (jgi)
2. create pileup using samtools mpileup command
3. create sync file using popoolation scripts
4. create a genewise sync file using your gtf features file. 
5. calculate average depth of coverage across mtDNA genes.
6a. calculate average depth of coverage across 13 randomly sampled nuclear genes, performing 10,000 permutations.
6b. for each permutation, divide the nuclear average from the mitochondrial average. 
##Warnings  
This script is pretty slow and it would be a good idea to split your .sync files by chromosome and run in parallel. 
##USAGE
