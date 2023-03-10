- The list of species that have less than 10 chromosomes and actually have assemblies according to NCBI entrez
  collapsed:: true
	- Numbers for assemblies generated using this one-liner :`esearch -db assembly -query $line | xtract -pattern ENTREZ_DIRECT -element Count`
	- The name of the bash script used is `entrez_automation` and the jupyter notebook used was `6.ipynb`
	- Dysphania ambrosioides
	  Aristolochia cretica
	  Arabidopsis thaliana
	  Brassica napus
	  Brassica rapa
	  Erucastrum elatum
	  Physaria acutifolia
	  Physaria berlandieri
	  Physaria cinerea
	  Physaria cordiformis
	  Physaria geyeri
	  Physaria lepidota
	  Physaria oregona
	  Physaria palmeri
	  Physaria parvula
	  Physaria rectipes
	  Physaria reediana
	  Physaria rollinsii
	  Physaria valida
	  Physaria vitulifera
	  Bradburia pilosa
	  Emilia baberka
	  Erigeron arizonicus
	  Erigeron philadelphicus
	  Erigeron vetensis
	  Osbertia stolonifera
	  Pulicaria angustifolia
	  Senecio lelyi
	  Senecio nikoensis
	  Sedum pusillum
	  Cucurbita pepo
	  Rhynchospora breviuscula
	  Rhynchospora tenuis
	  Ricinus communis
	  Juncus effusus
	  Juncus sorrentinii
	  Cicer echinospermum
	  Cicer reticulatum
	  Lupinus barkeri
	  Sesbania bispinosa
	  Vicia faba
	  Vicia sativa
	  Vicia serinica
	  Vicia sosnowskyi
	  Theobroma cacao
	  Corrigiola litoralis
	  Erycina pusilla
	  Oxalis juruensis
	  Oxalis praetexta
	  Macleaya cordata
	  Plantago insularis
	  Plantago major
	  Brachypodium distachyon
	  Coix aquatica
	  Coix lacryma-jobi
	  Digitaria aequiglumis
	  Oropetium thomaeum
	  Pennisetum glaucum
	  Morinda officinalis
	  Santalum album
	  Tetracentron sinense
	  Pleurozium schreberi
	  Rhytidiadelphus loreus
- It seems very possible that `NCBI entrez` might not be the way to go and the only way to do this might be with [`NCBI datasets`](https://www.ncbi.nlm.nih.gov/datasets/docs/v2/how-tos/)
  collapsed:: true
	- The issue with NCBI has been that for some reason it is completely ignoring the specific name of a whole species name (using `datasets summary genome taxon 'Aristolochia cretica'`). For example, when sending in `datasets summary genome taxon 'Aristolochia cretica'`, only `Aristolochia` is used.
- `esearch -db assembly -query "Aristolochia cretica" | efetch -format uid` this is it.
	- `efetch -db assembly -id 10829611` produces an error that just says "Bad request"
	- `efetch -db assembly -id 10829611 -format xml` does not work either.
- This is it: `esearch -db assembly -query "Aristolochia cretica" | esummary`
- This produces the proper species names: `esearch -db assembly -query "Aristolochia cretica" | esummary | xtract -pattern DocumentSummary -element SpeciesName`
- I completely forget why I dropped the following species:
	- Lonchitis hirsuta - VVRN
	- Lindsaea microphylla - YIXP
	- Dennstaedtia davallioides - This one is MTGC and was particularly problematic because it was missing nucleotide data all together
- The list of species with 112 names is
  collapsed:: true
	- Acacia argyrophylla
	  Adiantum raddianum
	  Agave tequilana
	  Amborella trichopoda
	  Anemia tomentosa
	  Arabidopsis thaliana
	  Araucaria rulei
	  Aristolochia elegans
	  Asparagus densiflorus
	  Asplenium platyneuron
	  Atriplex prostrata
	  Austrobaileya scandens
	  Austrotaxus spicata
	  Azolla Pinnata
	  Azolla carliniana
	  Botrypus virginianus
	  Cedrus libani
	  Ceratophyllum demersum
	  Ceratopteris thalictroides
	  Chamaecyparis lawsoniana
	  Cleome gynandra
	  Cycas micholitzii
	  Cystopteris utahensis
	  Danaea nodosa
	  Dendrolycopodium obscurum
	  Dennstaedtia davallioides 
	  Dichroa febrifuga
	  Dioon edule
	  Diphasiastrum digitatum
	  Dipteris conjugata
	  Drimys winteri
	  Dryas octopetala
	  Eleusine coracana
	  Ephedra sinica
	  Equisetum diffusum
	  Equisetum hyemale
	  Erigeron canadensis
	  Eschscholzia californica
	  Freycinetia multiflora
	  Gaga arizonica
	  Ginkgo biloba
	  Gnetum montanum
	  Gymnocarpium dryopteris
	  Hakea drupacea
	  Heliotropium mendocinum
	  Huperzia lucidula
	  Huperzia myrsinites
	  Huperzia squarrosa
	  Hydrocotyle umbellata
	  Hymenophyllum bivalve
	  Isoetes tegetiformans
	  Leiosporoceros dussii
	  Lindenbergia philippensis
	  Lindsaea linearis
	  Lindsaea microphylla
	  Lonchitis hirsuta
	  Loropetalum chinense
	  Lycopodiella appressa
	  Lycopodium annotinum
	  Lycopodium deuterodensum
	  Lygodium japonicum
	  Magnolia grandiflora
	  Marattia attenuata
	  Marchantia polymorpha
	  Marsilea quadrifolia
	  Metasequoia glyptostroboides
	  Metzgeria crassipilis
	  Nothoceros vincentianus
	  Nothotsuga longibracteata
	  Nuphar advena
	  Onoclea sensibilis
	  Ophioglossum petiolatum
	  Oryza sativa
	  Osmunda javanica
	  Osmundastrum cinnamomeum
	  Physcomitrella patens
	  Picea engelmannii
	  Pilularia globulifera
	  Pinus radiata
	  Plagiogyria japonica
	  Polypodium glycyrrhiza
	  Polystichum acrostichoides
	  Populus trichocarpa
	  Pseudolarix amabilis
	  Pseudolycopodiella caroliniana
	  Psilotum nudum
	  Pteris ensiformis
	  Pteris vittata
	  Rhododendron scopulorum
	  Salvinia natans
	  Santalum acuminatum
	  Sassafras albidum
	  Sceptridium dissectum
	  Selaginella apoda
	  Selaginella kraussiana
	  Selaginella moellendorffii
	  Selaginella selaginoides
	  Selaginella wallacei
	  Selaginella willdenowii
	  Sisyrinchium angustifolium
	  Solanum xanthocarpum
	  Sphagnum palustre
	  Taiwania cryptomerioides
	  Taxodium distichum
	  Thyrsopteris elegans
	  Timmia austriaca
	  Tmesipteris parva
	  Torreya taxifolia
	  Vittaria appalachiana
	  Wollemia nobilis
	  Zea may
	  Zingiber officinale
- The one with 110 names is
  collapsed:: true
	- Acacia argyrophylla 
	  Adiantum raddianum 
	  Agave tequilana 
	  Amborella trichopoda 
	  Anemia tomentosa 
	  Arabidopsis thaliana 
	  Araucaria rulei 
	  Aristolochia elegans 
	  Asparagus densiflorus 
	  Asplenium platyneuron 
	  Atriplex prostrata 
	  Austrobaileya scandens 
	  Austrotaxus spicata 
	  Azolla carliniana 
	  Azolla Pinnata 
	  Botrypus virginianus 
	  Cedrus libani 
	  Ceratophyllum demersum 
	  Ceratopteris thalictroides 
	  Chamaecyparis lawsoniana 
	  Cleome gynandra 
	  Cycas micholitzii 
	  Cystopteris utahensis 
	  Danaea nodosa 
	  Dendrolycopodium obscurum 
	  Dennstaedtia davallioides 
	  Dichroa febrifuga 
	  Dioon edule 
	  Diphasiastrum digitatum 
	  Dipteris conjugata 
	  Drimys winteri 
	  Dryas octopetala 
	  Eleusine coracana 
	  Ephedra sinica 
	  Equisetum diffusum 
	  Equisetum hyemale 
	  Erigeron canadensis 
	  Eschscholzia californica 
	  Freycinetia multiflora 
	  Gaga arizonica 
	  Ginkgo biloba 
	  Gnetum montanum 
	  Gymnocarpium dryopteris 
	  Hakea drupacea 
	  Heliotropium mendocinum 
	  Huperzia lucidula 
	  Huperzia myrsinites 
	  Huperzia squarrosa 
	  Hydrocotyle umbellata 
	  Hymenophyllum bivalve 
	  Isoetes tegetiformans 
	  Leiosporoceros dussii 
	  Lindenbergia philippensis 
	  Lindsaea linearis 
	  Loropetalum chinense 
	  Lycopodiella appressa 
	  Lycopodium annotinum 
	  Lycopodium deuterodensum 
	  Lygodium japonicum 
	  Magnolia grandiflora 
	  Marattia attenuata 
	  Marchantia polymorpha 
	  Marsilea quadrifolia 
	  Metasequoia glyptostroboides 
	  Metzgeria crassipilis 
	  Nothoceros vincentianus 
	  Nothotsuga longibracteata 
	  Nuphar advena 
	  Onoclea sensibilis 
	  Ophioglossum petiolatum 
	  Oryza sativa 
	  Osmunda javanica 
	  Osmundastrum cinnamomeum 
	  Physcomitrella patens 
	  Picea engelmannii 
	  Pilularia globulifera 
	  Pinus radiata 
	  Plagiogyria japonica 
	  Polypodium glycyrrhiza 
	  Polystichum acrostichoides 
	  Populus trichocarpa 
	  Pseudolarix amabilis 
	  Pseudolycopodiella caroliniana 
	  Psilotum nudum 
	  Pteris ensiformis 
	  Pteris vittata 
	  Rhododendron scopulorum 
	  Salvinia natans 
	  Santalum acuminatum 
	  Sassafras albidum 
	  Sceptridium dissectum 
	  Selaginella apoda 
	  Selaginella kraussiana 
	  Selaginella moellendorffii 
	  Selaginella selaginoides 
	  Selaginella wallacei 
	  Selaginella willdenowii 
	  Sisyrinchium angustifolium 
	  Solanum xanthocarpum 
	  Sphagnum palustre 
	  Taiwania cryptomerioides 
	  Taxodium distichum 
	  Thyrsopteris elegans 
	  Timmia austriaca 
	  Tmesipteris parva 
	  Torreya taxifolia 
	  Vittaria appalachiana 
	  Wollemia nobilis 
	  Zea may 
	  Zingiber officinale
- # [[Feb 14th, 2023]]
- I used `8.ipynb` to compare the old list of 110 species and the new list of species with 35 (34 + Arabidopsis thaliana). The only similarity was Arabidopsis which I dropped from the list with 35 names.
  collapsed:: true
	- The list of 34 species is as follows:
	  collapsed:: true
		- Dysphania ambrosioides
		  Brassica napus
		  Brassica rapa
		  Erucastrum elatum
		  Physaria acutifolia
		  Erigeron philadelphicus
		  Cucurbita pepo
		  Rhynchospora breviuscula
		  Rhynchospora pubera
		  Rhynchospora tenuis
		  Ricinus communis
		  Juncus effusus
		  Cicer echinospermum
		  Cicer reticulatum
		  Sesbania bispinosa
		  Vicia faba
		  Vicia sativa
		  Theobroma cacao
		  Corrigiola litoralis
		  Erycina pusilla
		  Macleaya cordata
		  Turnera subulata
		  Plantago major
		  Plantago ovata
		  Brachypodium distachyon
		  Coix aquatica
		  Coix lacryma-jobi
		  Oropetium thomaeum
		  Pennisetum glaucum
		  Morinda officinalis
		  Santalum album
		  Tetracentron sinense
		  Pleurozium schreberi
		  Rhytidiadelphus loreus
- `esearch -db assembly -query "Brassica rapa[ORGN]" | esummary | xtract -pattern DocumentSummary -sep "|" -element GbUid SpeciesName AssemblyStatus AssemblyType LastUpdateDate`
- # [[Feb 15th, 2023]]
- What is the different between a scaffold level assembly and a chromosome level assembly
  :LOGBOOK:
  CLOCK: [2023-02-15 Wed 12:57:25]--[2023-02-15 Wed 12:57:26] =>  00:00:01
  CLOCK: [2023-02-15 Wed 12:57:27]--[2023-02-15 Wed 12:57:27] =>  00:00:00
  :END:
	- According to [ensemble](https://useast.ensembl.org/info/genome/genebuild/chromosomes_scaffolds_contigs.html) and [JGI](https://mycocosm.jgi.doe.gov/help/scaffolds.jsf)
	- Contigs - continuous portion of a genome sequence reconstructed from shotgun data.
	- Scaffolds - Are structures made of contigs and gaps.
	- Chromosomes - Chromosomes are scaffolds without gaps
- # [[Feb 23rd, 2023]]
- Comments from Norm
	- *When using transcriptomes there can be a lot of assembly error, and the data may include alternative splice forms. Even though the 1KP data is relatively cleaned up for these issues, there are likely (well, not likely, I happen to know for a fact) still more than a single sequence that represents a gene. The effect of this is that you may be over-counting membership in a gene family, particularly when you have mixed genome/transcriptome data. If it’s not too late, I would look into tree-based methods of selecting the single best transcript for any one gene - we’ve used this in the path and I quite like it: https://bitbucket.org/dfmoralesb/target_enrichment_orthology/src/master/ (there is another implementation I haven’t tried that may be easier to use here: https://github.com/chrisjackson-pellicle/Yang-and-Smith-paralogy-resolution).*
	- *This is a bit more of a “philosophical” issue, but I think it would be good to think about how to really associate gene family changes or selection with the evolution of heterospory. I guess what I’m getting at is that you (or we) should think about what other traits may have arisen at the same nodes where heterospory arises. How can we be sure that we’re not looking at an association with other traits? The best way to do this would be to include other clades where those traits have evolved in homosporous lineages, or in heterosporous lineages but much later than the evolution of heterospory. I’m not sure how much of a big deal this is, but it’s just a little nagging thought in the back of my head*
- Thesis Feedback from Norm (not in order)
  collapsed:: true
	- *However, the scientific community still lacks a plausible explanation for this association of two seemingly unrelated traits.*
		- Norm said: *They could still be unrelated! To test this, it would be interesting to look at other nodes where chromosome numbers have decreased. If the same genes are involved at these nodes as your 3 focal nodes, you could potentially eliminate some of the candidates!*
		-
- # [[Feb 28th, 2023]]
- {{embed [[Working with SoapDenovo-Trans]]}}
- # [[Mar 2nd, 2023]]
- Tasks
	- Make a list of the old 111 species
	  collapsed:: true
		- Do this using the peptide files in onedrive
	- Split the list according to sources
		- Down the onekp data using the Rpackage.
		- If you are going to use Jessie's data do it using his github.
		- Use phytozome for Blaine's species
			- {{embed ((6400e71b-3b0c-46a5-8ac7-644228ebc376))}}
			- |Species X Source|Blaine|Phytozome primary transcript|Phytozome transcript|
			  |--|--|--|--|
			  |Arabidopsis thaliana|27628|27654|48455|
			  |Oryza sativa|42189|42189|52424|
			  |Physcomitrella paten |32926|32926|87533|
			  |Poplus trichocarpa|34699|42950|63498|
			  |Zea mays|39756|39498|131484|
			-
	- TODO Not sure why but there are two different types of genome files on phytozome, for both peptides and cds files. One type that is labelled `.cds_primaryTranscriptOnly.fa.gz` and the second type is labelled `cds.fa.gz`. Not sure what the difference is.
	  collapsed:: true
	  :LOGBOOK:
	  CLOCK: [2023-03-02 Thu 14:10:55]--[2023-03-02 Thu 14:10:56] =>  00:00:01
	  :END:
		- [Discussion on reddit](https://www.reddit.com/r/bioinformatics/comments/11gd520/transcript_vs_primary_transcript_on_phytozome/)
		- [Discussion on biostars](https://www.biostars.org/p/9556284/)
		- [According to Wikidpedia](https://www.wikiwand.com/en/Primary_transcript) A primary transcript is the single-stranded ribonucleic acid (RNA) product synthesized by transcription of DNA, and processed to yield various mature RNA products such as mRNAs, tRNAs, and rRNAs. The primary transcripts designated to be mRNAs are modified in preparation for translation. For example, a precursor mRNA (pre-mRNA) is a type of primary transcript that becomes a messenger RNA (mRNA) after processing.
	-
- # [[Mar 10th, 2023]]
- Removed MTGC (Dennstaedtia davallioides) from the list because it has no assembly on onekp archives. But there is data on Jessie's repo.
-