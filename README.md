## SARS-CoV Pipeline 
This project aims to analyze NGS data of recent SARS outbreak samples for genome assembly, mutation detection, and lineage identification. Results were displayed in two data frames listing the mutations in each genome and a third data frame displaying shared mutations between the two genomes.

Requirements include:
* Pandas
* bwa
* samtools
* bcftools
* cyvcf2

Files needed:
* Sample genomes
* Reference genome

### Pipeline

After installing the required tools, download the sample and genome references using down. Use bwa index to index the reference genome and bwa mem to align the reference and one of the sample genomes into a SAM file for each genome. Then, use samtools to sort each SAM file. bcftools and mpileup sort the variants from the reads using the reference genome and makes the vcf files. Open the vcf files using gzip. CYVCF2 then parses VCF files. Use pandas to format the vcf files and create dataframes showing the mutations for each genome and their shared mutations. Plt.hist makes a histogram displaying the distribution of quality scores in one of the dataframes. 

