# Project Proposal
## Python and bash based RNAseq processing

[Project Overview](#project-overview)

[Computational Overview](#computational-overview)

[Basics of RNAseq Data Processing](#basics-of-RNAseq-Data-Processing)

# Project Overview

I am currently collecting an RNAseq dataset to examine gene expression across sex and age in brown anoles.
The timepoints range from sexual maturity (7 months) to extreme old age (5 years).
The average lifespan of these lizards in the wild is approximately 2 years for males and 3 years for females, reversing the pattern of early female death due to reproductive burden.
The 5-year-old timepoint is an advanced age and samples from this age group are extremely rare, providing a unique opportunity to examine the health of the animals and potential differences in expression that could explain their longevity.
We suspect that genes in the Insulin and Insulin-Like (IIS) signaling network are important to this altered pattern of longevity and are of extreme interest as they closely match human expression patterns where we also see a trend of female-favored longevity. 

# Computational Overview

Many python-based pipelines and packages already exist for these datasets which process fastq files, clean the data, align it to a reference genome, create count tables, and normalization of count values.
Analysis of the data is not included in the project as moving beyond this point shifts from CLI coding to the use of programs such as GSEA, Cytoscape, and R.
*If you think including this would be appropriate, I would be happy to do what I can to include it. It won’t be trackable via github, but may be reproducible through sufficient documentation of protocols.*

To create a unique project that does not merely follow an established pipeline, I will process the data using all common packages rather than a singular workflow.
This will allow us to compare the quirks of each package and how they impact our final data, potentially showing us ways to combat biases introduced by each package’s assumptions. 

# Basics of RNAseq Data Processing

Fastq files are received from the sequencing company and must first be cleaned.
Paired-end reads are the standard for cleaning and a package such as FASTQC can be used to assess sequencing quality and removing paired reads where either the forward or reverse read is below a set quality score (phred33 is common with the most recent Illumina architecture).
Reads are then mapped to the closest available reference genome. SAM files are converted into BAM format before summarizing count data.
Finally, count data is normalized to control for sequencing depth before proceeding to data analysis.
