# Bio-410-Final-Project
## Background 
The data consists of 6 smaples from the organism Zaire ebolavirus. This organism is a enveloped, non-segmented, negative strand RNA virus which is the causative agent of Ebola Virus Disease. Ebola Virus is a frequently fatal human viral hemorrhagic fever

## Purpose 
The purpose of this project was to create a phylogenetic tree from 6 samples of Zaire ebolavirus in order to determine the evolutionary relationship between the samples.


## Methouds
Data Sources and Repository Structure: Sequencing Reads, the NGS sequencing experiment data (FASTQ files) for the six viral samples are located in the folder named Grace. Assembled Reads, the output generated after the assembly process, specifically the final.contigs.fa files, are stored within the t1_out through t6_out folders. 

Sequence Assembly: Sequence Assembly, the NGS reads were assembled into contigs using MEGAHIT, an ultra fast single cell genomic and metagenomic assembler. Procedure, each sample was processed using the command line to overlap short reads into longer contiguous sequences. 
 
Link: MEGAHIT GitHub Repository 
 

Data Compilation and Filtering: Compilation, the assembly results from all six samples were imported into R and compiled into a single DNAStringSet object using a custom loop. Filtering, To ensure the quality of the analysis, only contigs longer than 5,000 bp were retained. This filters out small genomic fragments, focusing on the most substantial parts of the 18 kbp viral genome. 

Multiple Sequence Alignment: Software, alignment was performed using the DECIPHER R package. Procedure, the filtered contigs were aligned using the AlignSeqs function to identify homologous regions and mutations across the samples. 
 

Phylogenetic Reconstruction: Software, Phylogenetic analysis was conducted using the DECIPHER R package. 
Method, a phylogenetic tree was reconstructed using the maximum likelihood method using the Treelinefunction. This method calculates the most likely evolutionary relationships based on the observed genetic variations in the alignment. 
 
## Results 

Here is the phylogenetic tree: 
<img width="1286" height="952" alt="image" src="https://github.com/user-attachments/assets/e5b70cbd-350e-42e7-a946-cb83d3d87e9b" />

In a phylogenetic tree, vertical branch lengths represent the genetic distance or substitution rate between sequences. Samples 5 and 6 are the most closely related; these two samples are the most closely related in the entire set of samples. They share a very recent common ancestor, indicated by the shortest horizontal distance between their branching point and the tips, samples 1 and 3 are highly related this pair forms a separate cluster of high similarity. While they are slightly more divergent from each other than the 5 and 6 samples pair, they are significantly more related to each other than to any other samples in the dataset. The clustered groups were 2,5, and 6 and 1,3, and 4. Sample 2 shares a common ancestor with 5 and 6 more recently than it does with the other three samples. Sample 4 is the "outgroup" of this specific cluster, being more genetically distinct from 1 and 3. Based on the tree structure and the historical data based on the Zaire ebolavirus isolate likely has a number of one individual because of the background information which includes the Kikwit-9510621 isolate was originally derived from a single 65-year-old female patient during the 1995 outbreak. The tree showed differences by the genetic variation observed between these 6 samples, which is typically the result of viral passaging or internal host evolution. When a virus is grown in a lab through different cell lines or used in different experimental groups, it acquires mutations. So, in the data there are 6 samples, but they likely represent different versions or replicates of the same original human isolate used in various lab studies and trials; they all technically trace back to the same single human source. 
