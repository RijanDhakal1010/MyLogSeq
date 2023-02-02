- What is the difference between Sanger and NGS?
  collapsed:: true
	- Sanger sequencing and next-generation sequencing (NGS) are two methods of DNA sequencing that are commonly used in biology and medicine. Both methods are based on the same principle of determining the sequence of a DNA molecule, but they differ in the way they approach this problem. Sanger sequencing is a traditional method that was developed in the 1970s, while NGS is a more recent technology that has revolutionized the field of genomics.
	- The main difference between Sanger sequencing and NGS is the throughput, or the amount of DNA that can be sequenced in a given time. Sanger sequencing is a slower, more labor-intensive process that is typically used to sequence long stretches of DNA, whereas NGS is a faster, more efficient method that can generate millions of short DNA sequences in parallel. This makes NGS more suitable for large-scale sequencing projects, such as whole-genome sequencing or transcriptome analysis.
	- Another key difference between Sanger sequencing and NGS is the cost and accuracy of the two methods. Sanger sequencing is generally more accurate than NGS, but it is also more expensive and time-consuming. In contrast, NGS is less accurate than Sanger sequencing, but it is much faster and more cost-effective, which makes it more suitable for large-scale sequencing projects.
	- Overall, the choice of which method to use for DNA sequencing depends on the specific requirements of the project, including the length of the DNA fragments to be sequenced, the desired accuracy and precision, and the budget and time constraints. Both Sanger sequencing and NGS have their own strengths and limitations, and each can be used effectively in different scenarios.
- How is a transcriptome made?
  collapsed:: true
	- The transcriptome is the set of all the RNA molecules that are produced from the genes in a cell or tissue. To create a transcriptome, the first step is to extract the RNA from the cells or tissue. This is typically done using a chemical process that breaks open the cells and releases the RNA. The RNA is then purified to remove any contaminants, and the quality and quantity of the RNA is determined using specialized techniques.
	- Once the RNA has been extracted and purified, it is ready to be sequenced. This is typically done using a method known as next-generation sequencing (NGS), which generates millions of short DNA sequences, known as reads, that correspond to the RNA molecules in the sample. The reads are then aligned to a reference genome to determine their order and orientation, and specialized software is used to assemble the reads into longer sequences, called contigs. The contigs are then annotated to identify the genes they correspond to, and this information is used to create the transcriptome.
	- The transcriptome provides valuable information about the genes that are expressed in a given cell or tissue, and can be used to study the function and regulation of these genes. It can also be used to identify genes that are differentially expressed in different conditions or diseases, and to investigate the mechanisms underlying these changes.
- P-value?
  collapsed:: true
	- The p-value tells us the likelihood of obtaining the observed results, 
	  or a more extreme result, if the null hypothesis is true.
	- P- Values are one of the most commonly used tools for statistical testing, but also one of the most misunderstood. Most people summarize a P-Value incorrectly as the "likelihood that the results from your data do not show a true correlation and are just random chance." We would love to know that number (because then we could be much more confident in whether or not our data was pointing to a real connection between the test and the outcome), but we can't know that. No amount of data will tell us our error rate.
	- A P-value actually tells us the likelihood that you observe this outcome in your data given that your counter-assumption is true (i.e. a true null hypothesis). Remember that in statistical testing, you have an assumption you are studying (for example, let's assume that smoking cigarettes makes you live longer) and the opposite of that assumption (smoking does not make you live longer). The assumption is called your hypothesis and the counter-assumption is called your null hypothesis. In a statistical test, we make a conclusion by rejecting the null hypothesis, or being able to confidently say that the opposite of our study's assumption is NOT true. I know it's confusing that statisticians take a double-negative approach, but it's the best we can do given the limits of what we can do with our math.
	- Now, we know that smoking cigarettes doesn't help you live longer, so the counter-assumption is actually true. But there is a chance that our study will incorrectly show a connection between smoking and a longer life. If we have a P-Value of 0.05 for our data, this means that given that smoking doesn't makes us live longer, we will still see a connection between smoking and a long life 5% of the time.
	- Most importantly, notice that the statement above tells us NOTHING about the likelihood that our assumption (or counter-assumption) is true (or false). A P-value cannot tell us how confident we are that we got the "right" results or how likely it is that our results were due to chance. Given that there is no connection, random chance will will tell us there is a connection some of the time. The percent of times we can expect to get this wrong is the P-Value.
- What is a reference genome, how is it made and what do you do if there is no reference genome?
  collapsed:: true
	- A reference genome is a genome that serves as a point of comparison for other genomes. It is a comprehensive, annotated sequence of a species' entire genome, and it is used as a reference against which other genomes can be compared. Reference genomes are typically created through a process called genome sequencing, in which the DNA of an organism is sequenced and assembled into a complete genome. This process involves a number of different steps, including DNA extraction, fragmentation, amplification, sequencing, and assembly.
	- If there is no reference genome for a particular species, researchers can still study its genome by using a combination of different techniques, such as de novo genome sequencing, in which the genome is sequenced and assembled from scratch, or comparative genomics, in which the genome of a closely related species is used as a reference. In some cases, researchers may also be able to use data from multiple sources, such as transcriptome data or other genomic data, to study the genome of a species without a reference genome.
- what basics should I learn to understand optimization?
  collapsed:: true
	- To understand optimization, you should first have a basic understanding 
	  of mathematical concepts such as calculus and linear algebra. In 
	  particular, you should be familiar with derivative and gradient 
	  calculations, which are used to find the optimal values of a function. 
	  It can also be helpful to have some familiarity with algorithms, as many
	   optimization techniques are implemented using algorithms. Additionally,
	   having some background in the specific application or field in which 
	  you want to use optimization can be helpful in understanding the context
	   in which the optimization is being performed.
- What are some good books to learn R?
	- Some good books to learn R include "R for Data Science" by Hadley 
	  Wickham and Garrett Grolemund, "An Introduction to R" by W. N. Venables,
	   D. M. Smith, and the R Core Team, and "Advanced R" by Hadley Wickham. 
	  These books provide a thorough introduction to the R language and its 
	  capabilities, and they include a variety of examples and exercises to 
	  help you learn and apply the concepts covered in the book. Additionally,
	   there are many online resources available for learning R, including 
	  tutorials, documentation, and forums where you can ask questions and get
	   help from other R users.
	- Here are some books that you might find helpful for learning R:
		- "R for Data Science" by Hadley Wickham and Garrett Grolemund
		- "The Art of R Programming" by Norman Matloff
		- "R in Action" by Robert Kabacoff
		- "Data Science with R" by Jared Lander
		- "Practical Data Science with R" by Nina Zumel and John Mount
		  
		  These books cover a range of topics and levels of difficulty, so you should be able to find one that matches your needs and experience level. Additionally, there are many online resources for learning R, including tutorials, video courses, and forums where you can ask questions and get help from other R users.
- Different methods of DNA sequencing?
  collapsed:: true
	- There are several different methods of DNA sequencing, including:
	- Sanger sequencing: This method uses the dideoxy chain termination method to sequence DNA. It involves synthesizing a new DNA strand complementary to the template strand, and adding dideoxy nucleotides (ddNTPs) that terminate DNA synthesis at specific positions. The resulting fragments are then separated by size using gel electrophoresis and sequenced using a specialized DNA sequencer.
	- Next-generation sequencing (NGS): This method uses high-throughput DNA sequencing technologies that can sequence millions or billions of DNA fragments simultaneously. NGS technologies include Illumina sequencing, PacBio sequencing, and Oxford Nanopore sequencing, among others.
	- Single-molecule sequencing: This method directly sequences individual DNA molecules without the need for PCR amplification or cloning. It uses specialized sequencing platforms that can detect the sequence of a single DNA molecule in real time.
	- Massively parallel sequencing: This method involves sequencing multiple DNA fragments simultaneously using a large array of sequencing reactions. The resulting sequence data is then combined to generate a complete sequence of the original DNA sample.
	- Hybrid sequencing: This method combines the advantages of different sequencing methods to achieve high accuracy and throughput. It typically involves using NGS technologies to generate a large number of short sequence reads, which are then used to generate a high-quality reference sequence that can be used to correct errors and improve accuracy.
- Difference between a genome and a transcriptome?
  collapsed:: true
	- A genome is the complete set of genetic material (DNA) present in an organism, while a transcriptome is the set of all RNA molecules (transcripts) produced by an organism's genes. The genome contains all of the genetic information necessary to build and maintain an organism, including the genes that encode proteins and other functional molecules. In contrast, the transcriptome includes only the RNA molecules that are actively being expressed, or transcribed, at a given time.
- How are cDNA libraries made?
  collapsed:: true
	- cDNA libraries are collections of DNA molecules that are derived from the RNA molecules present in a cell or tissue sample. To create a cDNA library, the RNA molecules are first extracted from the sample and treated with an enzyme called reverse transcriptase, which converts the RNA into complementary DNA (cDNA). The resulting cDNA molecules are then inserted into a vector, such as a plasmid or bacteriophage, which can be replicated and amplified in a host organism.
	- The cDNA molecules are then cloned, or reproduced, many times in the host organism to create a large number of identical copies. These copies are then isolated and arranged in a predetermined order, creating a cDNA library that can be used for a variety of purposes, such as gene expression analysis and functional genomics studies.
- What are the limits of the hill climbing algorithms?
  collapsed:: true
	- Hill climbing algorithms are a class of optimization algorithms that aim to find the optimal solution to a problem by iteratively making small changes to the current solution in order to improve it. However, hill climbing algorithms have some limitations that can make them ineffective in certain situations.
	- One limitation of hill climbing algorithms is that they can get stuck in local optima, which are suboptimal solutions that are not the global optimum. For example, if the landscape of the optimization problem is rugged, with many local optima, the hill climbing algorithm may become trapped at one of these suboptimal solutions and be unable to find the global optimum.
	- Another limitation of hill climbing algorithms is that they may require a large number of iterations to find the optimal solution, which can make them computationally inefficient for complex problems. In addition, hill climbing algorithms can be sensitive to the initial starting point, so if the initial solution is not close to the global optimum, the algorithm may take even longer to find the optimal solution.
- Differences between MLE and baysian stats?
  collapsed:: true
	- Maximum likelihood estimation (MLE) and Bayesian statistics are two approaches to statistical inference that are used to estimate the parameters of a statistical model. MLE and Bayesian statistics have some differences and similarities, as well as their own strengths and weaknesses.
	  
	  One key difference between MLE and Bayesian statistics is that MLE is a frequentist approach, which means it assumes that the true values of the model parameters are fixed, but unknown. In contrast, Bayesian statistics is a Bayesian approach, which means it uses prior knowledge about the model parameters to incorporate uncertainty and make probabilistic predictions about their values.
	  
	  Pros of MLE:
	- MLE is a consistent estimator, which means that it will converge to the true parameter values as the sample size increases.
	- MLE is relatively easy to implement and can be computationally efficient for simple models.
	- MLE provides point estimates of the model parameters, which can be useful for making predictions or making decisions.
	  
	  Cons of MLE:
	- MLE is sensitive to the choice of initial starting values and can be prone to getting stuck in local optima.
	- MLE provides no measure of uncertainty or confidence in the estimated parameter values, so it cannot be used to make probabilistic predictions.
	- MLE relies on the assumption of a correct model, so it can be biased if the model is misspecified.
	  
	  Pros of Bayesian statistics:
	- Bayesian statistics provides a natural framework for incorporating prior knowledge and uncertainty into the analysis.
	- Bayesian statistics can produce full posterior distributions for the model parameters, which can be used to make probabilistic predictions and assess uncertainty.
	- Bayesian statistics allows for the incorporation of non-standard models or complex data structures, such as hierarchical or multi-level models.
	  
	  Cons of Bayesian statistics:
	- Bayesian statistics can be computationally intensive, especially for complex models or large data sets.
	- Bayesian statistics requires the specification of prior distributions, which can be subjective and may affect the results.
	- Bayesian statistics can be more difficult to interpret than MLE, especially for non-experts.