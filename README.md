# RetroFinder
RetroFinder is a tool of the universal pipeline, which is convenient for researchers to use it to quickly and comprehensively identity and analyze retrocopies in the genomes.

It uses the protein coding sequences as templates to align with the whole genome and integrates a series of bioinformatics tools (tblastn, LAST, FASTA, exonerate, clustalw, KaKs_Calculator, BEDtools, HISAT2, StringTie, Shiny, etc.) to scan retrocopies. What's more, it also can analyze heterosense substitution and synonymous substitution, compare the structure of parental genes and retrocopies and calculate the expression of them. In addition, this tool provides displays the information and analysis results in an intuitive graphical interface using the Shiny package in R. RetroFinder can be installed directly by docker and conda or downloading the source code from github (http)

# Dependencies
There is number of additional dependencies not provided by RetroFinder authors. Additional programs include:

1. **AXTConvertor:**
2. **bedtools:**
3. **blast+:**
4. **clustalw2:**
5. **exonerate:**
6. **FASTA:**
7. **gffread:**
8. **HISAT2:**
9. **KaKs_Calculator:**
10. **LAST:**
11. **seqkit:**
12. **Shiny:**
13. **StringTie:**

# Installation

# bin

# Usage
The input of Retrofinder are only two files: genome sequences file (fasta) and corresponding annotation file (gff).

**Usage**: RetroFinder  
<p>positional arguments:
Genome.fasta　　　　　　　　　- Fasta file with the reference genome sequences
Reference.gff　　　　　　　　&nbsp- Gff file with the reference genome
Output_dir　　　　　　　　　　- Path to the directory where all intermediate and final results will be stored
Tools_dir　　　　　　　　　　 - Path to the tools which are used</p>

optional arguments:  
　-h, --help            show this help message and exit  
　--FASTA [FASTA]       - Path of FASTA  
　--alignment_tool {LAST,tblastn} [{LAST,tblastn} ...]  
  　　　　　　　　　　　　- Choose LAST or tblastn to align proteins with genome sequences. ['LAST']  
　--thread [int]        - Number of threads to be used [1]  
　--exonerate [EXONERATE] - Path of exonerate  
　--identity [int]      - Rate of identity between retrocopy and parent gene [50]  
　--coverage_rate [int] - Rate of coverage between retrocopy and parent gene [50]  
　--coverage_len [int]  - Length of coverage between retrocopy and parent gene[50]  
　--intron_loss_num [int] - Number of intron which loss in parent gene [2]  
　--gap_len [int]       - Length of gap between regions to be merged [40]  
　--parent_loss_intron_len [int] - Minimum length of the loss intron in parent gene to be as valid intron [60]  
　--retro_one_exon_len [int] - Maximum length of the intron in retrocopy to be as valid intron [30]  
　--kaksmethod {NG,LWL,LPB,MLWL,MLPB,GY,YN,MYN,MS,MA,GNG,GLWL,GLPB,GMLWL,GMLPB,GYN,GMYN} [{NG,LWL,LPB,MLWL,MLPB,GY,YN,MYN,MS,MA,GNG,GLWL,GLPB,GMLWL,GMLPB,GYN,GMYN} ...]  
　　　　　　　　　　　　　- Methods for estimating Ka and Ks and theirs references(Default = MA)  
　--version             show program's version number and exit
