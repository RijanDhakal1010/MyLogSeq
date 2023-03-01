- # Core
- [SOADenovo-Trans](https://github.com/aquaskyline/SOAPdenovo-Trans)
- # Miscellaneous
- According to Jessie Pelosi : *I've heard that Soapdenovo-trans handles isoforms the best out of the de novo transcriptome assemblers, so that's what we used in hope of reducing this problem. I didn't personally test out different  clustering parameters - I think I used a threshold of 98% because I wanted to preserve paralogs (I would think that paralog sequences would differ enough that we could separate them using a high-ish % similarity value without failing to cluster isoforms of  an ortholog)*
- # How to use SOAPDenovo-trans
- Configuration file
	- What it is: SOAPDenovo uses a configuration file that tells the assembler where to find the relevant files and relevant information.
		- SOAPDenovo-trans says that it has the same kind of configuration file like SOAPdenovo but that says very little about the configuration file of SOAPDenovo-trans itself. It also says that there is no "rank" information and no idea what that means.
		  :LOGBOOK:
		  CLOCK: [2023-02-28 Tue 20:52:07]--[2023-02-28 Tue 20:52:08] =>  00:00:01
		  CLOCK: [2023-02-28 Tue 20:52:09]--[2023-02-28 Tue 20:52:10] =>  00:00:01
		  :END:
	- Parts that make the config:
	  collapsed:: true
		- Global
		  collapsed:: true
			- `max_rd_len` - The maximum read length for the read that the assembler will use. Any read longer than this in the input will be cut to this.
		- Multiple library section
		  collapsed:: true
			- The library information and the information of sequencing data generated from the library should be organized in the corresponding library section.
			- Start each library section with a tag [LIB]. The following items can be included:
				- avg_ins
				  collapsed:: true
					- This value indicates the average insert size of this library or the peak value position in the insert size distribution figure.
				- reverse_seq
				  collapsed:: true
					- This option takes value 0 or 1. It tells the assembler if the read sequences need to be complementarily reversed. Illumima GA produces two types of paired-end libraries: a) forward-reverse, generated from fragmented DNA ends with typical insert size less than 500 bp; b) reverse-forward, generated from circularizing libraries with typical insert size greater than 2 Kb. The parameter "reverse_seq" should be set to indicate this: 0, forward-reverse; 1, reverse-forward.
				- asm_flags
				  collapsed:: true
					- This indicator decides in which part(s) the reads are used. It takes value 1(only contig assembly), 2 (only scaffold assembly), 3(both contig and scaffold assembly).
				- rd_len_cutof
				  collapsed:: true
					- The assembler will cut the reads from the current library to this length.
				- map_len
				  collapsed:: true
					- This takes effect in the "map" step and is the mininum alignment length between a read and a contig required for a reliable read location. The minimum length for paired-end reads and mate-pair reads is 32 and 35 respectively. The assembler accepts read file in three kinds of formats: FASTA, FASTQ and BAM. Mate-pair relationship could be indicated in two ways: two sequence files with reads in the same order belonging to a pair, or two adjacent reads in a single file (FASTA only) are belonging to a pair. In the configuration file single end files are indicated by "f=/path/filename" or "q=/path/filename" for fasta or fastq formats separately. Paired reads in two fasta sequence files are indicated by "f1=" and "f2=". While paired reads in two fastq sequences files are indicated by "q1=" and "q2=". Paired reads in a single fasta sequence file is indicated by "p=" item. Reads in bam sequence files is indicated by "b=". All the above items in each library section are optional. The assembler assigns default values for most of them. If you are not sure how to set a parameter, you can remove it from your configuration file.
- Example config
-