# btv_sequencing_2

This is a sloppy working notebook for changes made to the original "btv_sequencing" pipeline forked from the Stenglein lab at CSU. 

Dependencies:
- QC Related: FastQC, MultiQC, Mosdepth, Picard
- Analysis Related: Bowtie2, Trimmomatic, Cd-Hit, Samtools, Bcftools
- Additionally Needed: BTV Reference FASTA

# MAKE SURE TO UPDATE LOCAL PATHS TO TRIMMOMATIC .jar FILES OR THIS PIPELINE WILL NOT WORK

4.19.23
- Added MultiQC to conda env
- Added "2> ${file_base}.trimm.log" to preprocessing script in order to generate log file that can be used by MultiQC
- Edited 2> redirector for log_f in run_bt_align_paired script
- Changed log_f to .bowtie.log
	- (Unsure if last two changes were good or not)
- Added step at end of run_mapping script to run MultiQC command
- Added FastQC to conda env and added command to run_mapping script
- Added Mosdepth to conda env and trialed the following script (and then imported manually through MultiQC)

5.12.23
- Updated this repo to include README.md in the form of a sloppy lab notebook
- Added initial FastQC step on input data (is this useful?)
- Added mosdepth to run_mapping script
- Worked for a while to get FastQ_Screen working (had to find/build reference genomes for config file)
- Installed and tested Picard tools to use for MarkDup and InsertSize metrics (all tests passed)
- Tested CollectInsertSize and MarkDuplicates tools in Picard, recognition of MultiQC regarding these reports, and then adding these steps to the run_mapping script

5.17.23
- Added commands to run_mapping script to generate Picard metrics (insert size and mark duplicates) from sorted BAM files 
- Added a few commands at the end of the run_mapping script to move all newly generated files into a new subdirectory

5.24.23
- Started using simple_scheduler script to run consecutive samples
- Changed Picard and Mosdepth metrics to collect from new best_10 BAM file (this dramatically changed mean coverage reported by Mosdepth) and moved to the end of run_mapping script
 
