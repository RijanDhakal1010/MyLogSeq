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