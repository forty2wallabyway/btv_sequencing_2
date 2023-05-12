# btv_sequencing_2

#This is a sloppy working notebook for changes made to the original "btv_sequencing" pipeline forked from the Stenglein lab at CSU. 

#4.19.23
- Added MultiQC to conda env ("btv_new_isolates")
- Added "2> ${file_base}.trimm.log" to preprocessing script in order to generate log file that can be used by MultiQC
- Edited 2> redirector for log_f in run_bt_align_paired script
- Changed log_f to .bowtie.log
	Unsure if last two changes were good or not
- Added step at end of run_mapping script to run MultiQC command
- Added FastQC to conda env and added command to run_mapping script
- Added Mosdepth to conda env and trialed the following script (and then imported manually through MultiQC)
	'mosdepth plaque21.mosdepth.summary.txt plaque21_R1_fu.fastq.btv_index.paired_sorted.bam'
