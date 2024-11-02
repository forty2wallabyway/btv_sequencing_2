# btv_sequencing_2

This is pipeline was forked from the Stenglein Lab at CSU. It was built for this purpose but has since been updated. 


It is currently intended for use with paired-end, Illumina short-read sequences. In brief, it will:

- Trim low quality reads and adapters, then consolidate duplicates.
- Map retained reads against a custom reference database (provided in this repository).
- Use custom scripts to generate consensus sequences for each genome segment by re-mapping reads against the "best" (i.e. closest provided) reference sequences. 
- Produce a MultiQC report with relevent metrics.

To use this pipeline:

- Ensure that samples are located in the same directory as these scripts, gzipped, and labeled as:
	- ```<isolate_name>_R1.fastq.gz``` and ```<isolate_name>_R2.fastq.gz```
- Clone this repository into your working directory and ensure that the following dependencies are installed:
	- fastQC, multiQC, mosdepth, picard
	- bowtie2, trimmomatic, cd-Hit, samtools, bcftools
 - Finally, initiate the pipeline by running the ```run_mapping_pipeline_one_sample``` script along with your ```<isolate name>``` as a command line argument.

**Please make sure to update local paths to TRIMMOMATIC .jar files or this pipeline will not work.**
