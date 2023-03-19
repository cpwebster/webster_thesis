# webster_thesis
This project contains 3 scripts that analyze genetic variation occuring among genes in a given VCF. These scripts were originally developed for parsing and filtering at a specific threshold within a subgroup of genes, such as a gene family or genes grouped by Gene Ontology, however the scripts can be easily altered for application to larger data sets. Arguments that pertain to input/output files and allele depth and frequency parameters were included for each script.

Link to written thesis:
https://scholarworks.utep.edu/open_etd/3369/

#chapter_1_preliminary.py:

This script reads in a VCF file, filters for Phytochrome gene mutations at a given threshold by allele depth and frequency, parses those mutations, and writes to a new VCF file.

USAGE: python -i chapter_1_preliminary.py <VCF_file> -o <output_file_name> -a <allele_depth> -m <minimum_allele_frequency>

#chapter_1_filter_SNPs_from_VCF.py:

This script parses Phytochrome gene mutations that meet requirements from a VCF, reads the reference and alternate muclotides and stores the information. Then, it copies and transforms a FASTA file to contain sequence mutations stored from the VCF. Every output file contains mutated sequence data from every sample in the VCF.

USAGE: python chapter_1_filter_SNPs_from_VCF.py -f <FASTA_file_input> -v <VCF_file_input> -ad <allele_depth> -sd <sample_depth> -o <output_directory_name>

#chapter_2_isolate_SSRs_inside_coding.py:

This script was developed to be used with the program SciRoKo 3.4, this program output file has information on microsatellite markers that occur in a given FASTA file. The script reads in the FASTA file and translates these genes on each reading frame, then storing where the longest coding region occurs. The positions of the microsatellites are compared with the coding region positions, and an output file is created with only the microsatellites that occur inside the coding regions. The script can also be easily altered the look at microsatellites outside the coding regions.

Script Arguments: -f FASTA file input name -s SciRoKo output file -l SSR (microsatellite) minimum repeat (ex. dinucleotide = 2) -out_file Output file -out_fasta FASTA file output
