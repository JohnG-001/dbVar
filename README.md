## dbVar human "non-redundant structural variations" (nr SVs) data files

## ****This work is subject to change due to work in progress****

# Last updated: 
04/04/18

# Link to FTP site: ftp site: ftp://ftp.ncbi.nlm.nih.gov/pub/dbVar/sandbox/human_non_redundant/

# Introduction

NCBI's database of Human Genomic Structural Variation is dbVar.  

  https://www.ncbi.nlm.nih.gov/dbvar

An overview of "Structural Variation" is found here:

  https://www.ncbi.nlm.nih.gov/dbvar/content/overview/#datamodel

Sets of "non-redundant structural variations" (nr SVs) derived from dbVar are 
available via FTP as tab delimited files by assembly, GRCh37 & GRCh38, and by 
type of variant.  

Non-redundant refers to variant coordinates, i.e. chr, outermost start, and 
outermost stop.  Please note: the non-redundant coordinates are based strictly 
on exact overlap of coordinates, not on partial overlaps.  

Variant types are grouped into three "aggregation types".  

* aggregated deletions and losses
* aggregated duplications and gains
* aggregated insertions

The variant types in each of the three "aggregation types" are:

* "aggregated deletions and losses" include:
** alu_deletion
** copy_number_loss
** deletion
** line1_deletion
** sva_deletion

* "aggregated duplications and gains" include:
** copy_number_gain
** copy_number_variation
** duplication
** tandem_duplication 

* "aggregated insertions" include:
** alu_insertion
** insertion
** line1_insertion
** mobile_element_insertion
** novel_sequence_insertion
** sva_insertion

# Summary Statistics

Number of input SV:
                                 	 Mar 9, 2018	Mar 9, 2018
category	type		 	 GRCh37		GRCh38
-------------------------------------------------------------------
deletions	alu_deletion	 	 1700117	1683546
		copy_number_loss 	 2409362	2392904
		deletion	 	 13091839	12903950
		herv_deletion	 	 197		197
		line1_deletion	 	 82103		81940
		sva_deletion	 	 14254		14254
		copy_number_variation	 1164548	1106074

duplications	copy_number_gain	 1247923	1208729
		duplication		 1926155	1915335
		tandem_duplication	 11478		11446

insertions	alu_insertion		 19908		19764
		insertion		 1220439	1226610
		line1_insertion		 3916		3901
		mobile_element_insertion 88610		88773
		novel_sequence_insertion 4067		4041
		sva_insertion		 1097		1087

Number of output NR Coordinates as of Mar 9, 2018:

nr coordinates	GRCh38 nr file
---------------------------------------------------------------------
  2207235 	all_nr_GRCh38_aggregated_deletion_loss.tsv
   326596 	all_nr_GRCh38_aggregated_duplication_gain.tsv
  1101221 	all_nr_GRCh38_aggregated_insertions.tsv
  3635052 total

nr coordinates	GRCh37 nr file
---------------------------------------------------------------------
  2219439 	all_nr_GRCh37_aggregated_deletion_loss.tsv
   336634 	all_nr_GRCh37_aggregated_duplication_gain.tsv
  1095615 	all_nr_GRCh37_aggregated_insertions.tsv
  3651688 total

# Files

The "nr SVs" will be in six files on the FTP site:

Available now:

del/all_nr_GRCh37_aggregated_deletion_loss.tsv
del/all_nr_GRCh38_aggregated_deletion_loss.tsv

Coming soon:

dup/all_nr_GRCh37_aggregated_duplication_gain.tsv  
ins/all_nr_GRCh37_aggregated_insertions.tsv  

dup/all_nr_GRCh38_aggregated_duplication_gain.tsv  
ins/all_nr_GRCh38_aggregated_insertions.tsv  

# Records in the aggregated_deletion_loss files 

Records in the aggregated_deletion_loss files contain the following tab-separated fields.

| chr | outer_most_start | outermost_stop | ssv_count | variant_type | method | analysis | platforms | studies | ssvs |


# Examples of records in "aggregated deletions and losses" files:

1       10001   1535693 1       deletion;       Oligo_aCGH;     Probe_signal_intensity; NA;     Boone2013;      nssv1614481;

Explanation:

The non-redundant coordinates for this record in dbvar are chr1, with
an outermost start of 10001 and outermost stop of 1535693.

The ssv_count of 1 indicates there is only one ssv with an exact match to the given placement, and does not include ssvs with a partial match.

The variant_call_type is "deletion".

The method of "Oligo_aCGH" and analysis of "Probe_signal_intensity" indicates
how the one variant was evaluated.

NA indicates the no platform was specified this one deletion variant.

Boone2013 is the study name as found in dbVar.

The dbVar variant_accession for the variaant is "nssv1614481".

URLs using the study name or variant_accession can be created to access the data
in dbVar, e.g.:
https://www.ncbi.nlm.nih.gov/dbvar/?term=Boone2013
https://www.ncbi.nlm.nih.gov/dbvar/?term=nssv1614481

From the latter page you may click on the "Variant Region ID" on the left to see
the variant's region in the NCBI Variation Viewer at:

https://www.ncbi.nlm.nih.gov/dbvar/variants/nsv933473/

A more complicated example deletiion NR record contains multiple variants with 
multiple types, methods, and analyses from multiple studies, using multiple
platforms:

1       72300544        72346418        7       copy_number_loss;deletion;      Oligo_aCGH;Sequencing;  Probe_signal_intensity;Read_depth;   Agilent 24M aCGH;Illumina IIx;  Park2010;Ju2010;        nssv1423530:nssv1425248:nssv1428032:nssv1428830:nssv1434173:nssv1439464:nssv1420391;

# Mehods include eg:

BAC_aCGH
Curated
MLPA
Merging
Multiple
Not_provided
Oligo_aCGH
Optical_mapping
ROMA
SNP_array
Sequencing
qPCR
ROMA
SNP_array
Sequencing

# Analyses include, eg:

Curated
Genotyping
Local_sequence_assembly
Manual_observation
Merging
Multiple
Not_provided
Optical_mapping
Other
Paired-end_mapping
Probe_signal_intensity
Read_depth
Read_depth_and_paired-end_mapping
SNP_genotyping_analysis
Sequence_alignment
Split_read_and_paired-end_mapping
Split_read_mapping
de_novo_sequence_assembly

# README files for del, dup and ins

Please see README files for del, dup and ins, under the current directory for 
additional details.

# Brief Outline of algorithm used to generate NR-SV.

The algorithm makes use of existing processes, so it isn't how it would have 
been designed if done from the ground up.

Input files are generated from the dbVar database with tab separated values and
contain SVs by assembly, type, and other relevant fields.

Selected type files are grouped into "aggregated type files" as specified above, 
by chr.

The "aggregated type files" are converted into XML records containing all the 
neccessary fields required by the nr process.

The XML is then parsed to generate SV records with coordinates, type, 
method, analysis, platform, insertion_length, SV accession and study.  

The SV records are then proccessed to genearte the nr records described above, 
and in the README files for del, dup and ins.

# Questions or feedback

For questions or feedback please contact: John Garner, jg95r@nih.gov

# Thank you!

Thanks for your interest in human "non-redundant structural variations" (nr SVs) data files
derived from dbVar.

Please check back soon for updates.

