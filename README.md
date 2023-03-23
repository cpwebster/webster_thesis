# webster_thesis
This project contains 3 scripts that analyze genetic variation occuring among genes in a given VCF. These scripts were originally developed for parsing, filtering, and transforming at a specific threshold within a subgroup of genes, such as a gene family or genes grouped by Gene Ontology, however the scripts can be easily altered for application to larger data sets. Arguments that pertain to input/output files and allele depth and frequency parameters were included for each script.

Link to written thesis:
https://scholarworks.utep.edu/open_etd/3369/

#filter_genes_by_mutation_qual.py:

This script reads in a VCF file, filters for Phytochrome gene mutations at a given threshold by allele depth and frequency, parses lines containing information on those mutations, and writes to a new VCF file.

USAGE: python filter_genes_by_mutation_qual.py -i <VCF_file> -o <output_file_name> -a <allele_depth> -m <minimum_allele_frequency>

#transform_FASTA_from_VCF.py:

This script parses Phytochrome gene mutations that meet requirements from a VCF, reads the reference and alternate nuclotides and stores the information. Then, it copies and transforms a FASTA file to contain sequence mutations stored from the VCF. Every output file contains mutated sequence data from every sample in the VCF.

USAGE: python transform_FASTA_from_VCF.py -f <FASTA_file_input> -v <VCF_file_input> -ad <allele_depth> -sd <sample_depth> -o <output_directory_name>

#isolate_SSRs_inside_coding.py:

This script utilizes a SciRoKo 3.4 (Kofler et al., 2008) output file (.td) and identifies SSRs of a given length in the coding regions of genes from the input FASTA file. The script reads in the FASTA file and translates genes on each reading frame, and stores where the longest coding region occurs. The positions of the SSRs are compared with the coding region start and stop positions, and 2 output files are created. A FASTA file with sequences of coding regions where SSRs occur (designed to be aligned with Clustal Omega), and a text document that lists gene names containing SSRs in coding regions.

USAGE: python isolate_SSRs_inside_coding.py -f <FASTA_file_input_name> -s <SciRoKo_output_file.td> -l <SSR_minimum_repeat_(dinucleotide=2)> -out_file <output_file_name> -out_fasta <FASTA_file_output_name>
