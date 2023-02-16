
# 2023_01_10 
###### [[Daily_Notes/2023_01_10 |Tue-2023_01_10 ]] - 4:00 pm: 
looking into Nanopore techniques
1. They have websites dedicated to different techniques
	1. Detecting splice variants
		1. https://nanoporetech.com/applications/investigation/splice-variation
		2. They link to RNA seq kits
		3. They call out this paper
			4. Clark, M. B. _et al._ Long-read sequencing reveals the complex splicing profile of the psychiatric risk gene CACNA1C in human brain. _Mol. Psychiatry_ **25**, 37–47 (2020)
			5. With talk here: https://nanoporetech.com/resource-centre/revealing-mrna-alternative-splicing-complexity-human-brain
		4. They also link this white paper
			1. _The value of full-length transcripts without bias_. https://nanoporetech.com/resource-centre/rna-sequencing-white-paper-value-full-length-transcripts-without-bias (2019)
	2. Detecting fusion transcripts
		1. https://nanoporetech.com/applications/investigation/fusion-transcripts
		2. List 3 types of RNA sequencing that are possible
			1. Direct RNA seq
				1. No PCR Bias
				2. Base modifications
			2. Direct cDNA seq
				1. No PCR bias
				2. Higher throughput
			3. PCR cDNA seq
				1. Highest throughput 
		3. Recommend this paper on gene fusion detection
			1. Jeck, W. R. _et al._ A Nanopore Sequencing–Based Assay for Rapid Detection of Gene Fusions. _J. Mol. Diagn._ **21**, 58–69 (2019)
			2. Talk is here: https://nanoporetech.com/resource-centre/william-jeck-nanopore-sequencing-and-rapid-fusion-testing-killer-app-molecular
		4. Recommend PCR based methods for fusion detection in order to amplify the specific transcript (or semi specifically with 1 known primer)
	3. Isoform-level gene expression analysis
		1. https://nanoporetech.com/applications/investigation/gene-expression
		2. PCR amplified libraries show less diversity that total RNA
			1. Amplification efficiency differences can cause changes in observed transcript levels
			2. Short read tech has a GC bias where far from 50% is under detected
		3. Link a paper
			1. Bayega, A. _et al._ Nanopore long-read RNA-seq and absolute quantification delineate transcription dynamics in early embryo development of an insect pest. _Sci. Rep._ **11**, 1–14 (2021)
			2. Spotlight: https://nanoporetech.com/sites/default/files/s3/literature/ResearchSpotlight_Olive_Fruit_Fly_17Jun2019_FAW_WEB_INTERACTIVE.pdf
			3. Talk: https://nanoporetech.com/resource-centre/anthony-bayega-transcriptome-landscape-developing-olive-fruit-fly-embryo-delineated
		4. 
	4. Detection of methylation on RNA (or DNA)
		1. https://nanoporetech.com/applications/investigation/epigenetics
		2. Claim to be better at CpG methylation detection than bisulfite sequencing
			1. Higher coverage
			2. Less bias
			3. Easier haplotyping
			4. High reproducibility
			5. faster data analysis
		3. adaptive sampling
			1. Can enrich for regions of interest on the machine without changes to library prep
				1. LOOK MORE INTO THIS!
			2. Mention work looking into methylation of repetitive elements of the genome
				1. https://nanoporetech.com/resource-centre/videos/NCM2020/Into-the-unknown%3A-the-epigenetics-of-repetitive-DNA
			3. Need to avoid both amplification and RT
			4. 
	5. Gene expression using direct RNA or cDNA 
		1. https://nanoporetech.com/applications/rna-sequencing

I will start digging in in more detail now

They also have a white paper on RNA sequencing that I've downloaded!

Summary figure of RNA sequencing modalities
![[Pasted image 20230110163410.png]]


# 2023_01_11 
###### [[Daily_Notes/2023_01_11 |Wed-2023_01_11 ]] - 10:13 am: 
Entering some details on papers I read yesterday/on the train
[[nanopore_rna_seq_witepaper_2019_The_value_of_full-length_transcripts_without_bias]]

[[Clark_et al._2020_Long-read_sequencing_reveals_the_complex_splicing_profile_of_the_psychiatric_risk_gene_CACNA1C_in_human_brain]]

###### [[Daily_Notes/2023_01_11 |Wed-2023_01_11 ]] - 10:33 am: 
Reading more nanopore RNA-seq papers

[[Bolisetty_et_al.-2015-Determining_exon_connectivity_in_complex_mRNAs_by_nanopore_sequencing]]

###### [[Daily_Notes/2023_01_11 |Wed-2023_01_11 ]] - 11:21 am: 
Off to find sequencing manuals for the 3 nanopore RNA-seq kits and to look for RNA pull down based nanopore sequencing

NVM, taking a break for lunch before the noon QB seminar

double NVM, free lunch from the seminar


###### [[Daily_Notes/2023_01_11 |Wed-2023_01_11 ]] - 2:22 pm: 
Just finished a paper on direct RNA capture that was quite interesting! will write it up now!
[[Tan_et_al.-2019-A_novel_method_for_the_capture-based_purification_of_whole_viral_native_RNA_genomes]]

###### [[Daily_Notes/2023_01_11 |Wed-2023_01_11 ]] - 2:44 pm: 
Starting [[Keller_et_al.-2018-Direct_RNA_sequencing_of_the_coding_complete_influenza_A_virus_genome]] now!

Methods for enriching sequences of interest

1. rtPCR
	1. Enables large fold enrichment by amplifying the target
2. Pull down
	1. Enables 100-1000x enrichment by purifying target from mixed samples
3. Adaptor complementarity
	1. Enables large fold enrichment by only ligating sequencing adaptors to target 
2. Adaptor complementarity and pull down
	1. Using a 3' compatible adaptor with a desthiobiotin modification, it is possible to get a double enrichment by both concentrating and preferentially sequencing the target
3. Adaptive sampling
	1. Enables a 5-10x improvement in enrichment by ejecting DNA molecules that don't match a pattern from the pores during sequencing
4. Some possible options I haven't seen confirmation of yet
	1. Primer specificity in cDNA synthesis
	2. Primer specificity in RCA
	3. RNA cleavage followed by adaptor complementarity


###### [[Daily_Notes/2023_01_11 |Wed-2023_01_11 ]] - 4:36 pm: 
Looking into ways to cut off the poly-A tail of an mRNA to allow 3' seq based methods so read some about dna-zymes
[[Feldman_and_Sen-2001-A_new_and_efficient_DNA_enzyme_for_the_sequence-specific_cleavage_of_RNA]]


# 2023_01_12 

### Brainstorming possible long read RNA-seq Prep steps
![[Kinney_lab_remarkable - page 6.png]]

Did some more reading:
- Good review (from Andalus)
	[[De_Paoli-Iseppi_et_al.-2021_Isoform_Age-Splice_Isoform_Profiling_Using_Long-Read_Technologies]]
- Single cell RT + capture for nanopore sequencing
	[[Singh_et_al.-2019-High-throughput_targeted_long-read_single_cell_sequencing_reveals_the_clonal_and_transcriptional_landscape_of_lymphocytes]]
- R2C2 in single cell context
	[[Volden_&_Vollmers-2022-Single-cell_isoform_analysis_in_human_immune_cells]]
- Capture seq tiling probe production and efficiency
	[[Sheynkman_et_al.-2020-ORF_Capture-Seq_as_a_versatile_method_for_targeted_identification_of_full-length_isoforms]]
- Has a good figure on capture seq validation
	[[Hardwick_et_al.-2019-Targeted_High-Resolution_RNA_Sequencing_of_Non-coding_Genomic_Regions_Associated_With_Neuropsychiatric_Functions]]
- Capture seq protocol paper (for illumina)
	[[Mercer_et_al.-2014-Targeted_sequencing_for_gene_discovery_and_quantification_using_RNA_CaptureSeq]]

Some concerns
1. Just emailed a nanopore rep and he suggested avoiding sequence specific RT though I'm not sure why
	1. Will follow up tomorrow
2. We need to figure out what percentage of our bulk RNA we expect to be low concentration interesting isoforms

![[2023_01_12_Kinney_Andalus_project_planning_meeting]]

# 2023_01_13
Met with nanopore service rep
![[2023_01_13_Nanopore_service_rep_meeting]]

# 2023_01_17
![[2023_01_17_Long_read_planning_meeting]]

# 2023_01_18 
Yesterday on the train, I worked up some controls to identify template exchange in our long-read MPSA data when we don't have built in dual barcodes
![[Kinney_lab_remarkable - page 12.png]]
Saw a very cool talk on splicing today: [[2023_01_18_David_Knowles_QB_seminar]]

read a very interesting paper with a really good looking reference list! I will look through for MPSA papers I haven't looked at yet to make sure no one is doing a long read version and ID what people are studying
[[Rogalska_et_al.-2022-Regulation_of_pre-mRNA_splicing_roles_in_physiology_and_disease_and_therapeutic_prospects]]

![[2023_01_18_MXE_minigene_cloning_plan]]

# 2023_01_23
## Summary of Long read MPSA papers
![[Existing_MPSAs]]

# [[2023_02_07]]
Read [[Ke_et_al.-2018-Saturation_mutagenesis_reveals_manifold_determinants_of_exon_definition]]

