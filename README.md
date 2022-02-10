# QUT VRES 2021/22 Poster
This repo consists of some Jupyter Notebooks used to generate graphs used for the VRES final poster.

# Abstract
CRISPR-Cas9 is a method of editing genomes, by removing, altering or adding sections of genomic sequences. Cas9 is an enzyme that acts as a pair of scissors, and cuts the strands of DNA at a specific location. This location needs to be identified by a guide RNA. Selection of the guide RNA is a computationally demanding task, as it's important to maximise the likelihood of obtaining a successful cut, while minimising off-target risks. Cracking is a new method for identifying guide RNA sequences. Crackling is a faster and better method to design guide RNAs.

We aim to increase the performance of Crackling, focusing on the file loading process and initial identification of candidate guides. For test sequences, such as Durum Wheat (GCA_900231445.1), this step can take in excess of 25 minutes.

We tested 5 different approaches to optimise performance. We found the best results from separating the genomic sequences into chunks, and evaluating each chunk in a separate process. We then had to combine the resultant guides, finding duplicates and candidates that will need further evaluation later in the Crackling process.

This approach decreased the initial processing time down to 15 minutes, a 28.4% improvement, over the base implementation with no loss in accuracy.

These findings show that there are significant performance gains to be made in this approach. However the gains are not linear, as moving to a parallel architecture requires significant processing overheads for communication between disparate processes, and collation of results.
