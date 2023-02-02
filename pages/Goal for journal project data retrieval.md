- Task/TL;DR : Trying  the ideal way to find trancriptomic and cDNA or verify the absence of "reputable" public data for a long list of non-model organism.
- What I am trying to do boils down to this: I wan to automate queries for assemblies (transcriptomes and cDNA) of species using `Entrez` using species names. (If `Entrez` is not the right tool for the job, I am open to other tools.)
- So far I have used species names through `Entrez`'s set of tools to find out if a species has publicly available transcriptomes and cDNA data and which ones don's. The list is 1500 items long and almost entirely non-model species, so automation is the only realistic way to go about this.
	- Examples of some of the species in the list:
		- `Paronychia echinulata Chater`
		- `Nothoscordum nudum Beauverd`
		- `Tristagma berteri Phil`
		- `Bupleurum komarovianum Lincz`
- Reading the following description, perhaps NCBI `Bioproject` is my best source:
	- > The [BioProject](https://www.ncbi.nlm.nih.gov/bioproject/)
	   database is a searcheable collection of complete and incomplete 
	  (in-progress) large-scale molecular projects including genome sequencing
	   and assembly, transcriptome, metagenomic, annotation, expression and 
	  mapping projects. BioProject provides a central point to link to all 
	  data associated with a project in the NCBI molecular and literature 
	  databases.
- But using something like `esearch -db bioproject -query "Paronychia echinulata"` on the my list of species has consistently returned almost nothing.
- Looking around the following are also some of the most suggested tools for the task:
	- [Plaza](https://bioinformatics.psb.ugent.be/plaza/)
	- [Phytozome](https://phytozome-next.jgi.doe.gov/)
	- [TSA](https://www.ncbi.nlm.nih.gov/genbank/tsa/)
	- [GEO](https://www.ncbi.nlm.nih.gov/geo/info/seq.html)
	- [Biomart](https://www.ensembl.org/biomart/martview)
- None of the above five really produced any results with a few manual searches.
- Are there any other "reputable" sources conducive to