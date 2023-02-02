- #Rlang
- Use the following code to install R
	- `devtools::install_github("YuLab-SMU/ggtree")`
	- No longer working
	  collapsed:: true
		- ```R
		  if (!requireNamespace("BiocManager", quietly = TRUE))
		      install.packages("BiocManager")
		  BiocManager::install("ggtree")
		  ```
- According to ChatGPT, to add names next to labels:
	- ```R
	  # Install and load the GGtree package
	  install.packages("GGtree")
	  library(GGtree)
	  
	  # Load your data into R. For this example, we'll use a built-in data set provided by GGtree.
	  data(ape.example)
	  
	  # Use the ggtree function to create a phylogenetic tree from the data.
	  tree <- ggtree(ape.example)
	  
	  # Use the nodeParams function to add labels to the nodes of the tree.
	  tree <- nodeParams(tree, label=node_id)
	  
	  # Use the ggsave function to save the tree as a PDF or other image file.
	  ggsave("phylogenetic_tree.pdf", tree)
	  
	  node_labels <- paste(df$name, df$number, sep=": ")
	  tree <- nodeParams(tree, label=node_labels)
	  ```