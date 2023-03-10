## Project
[[Fellowship Apps]]

## 2023_03_08 Brainstorming
1. Develop a Long-read MPSA and analysis pipeline
	1. Develop a synthetic data generation pipeline
	2. Write a data analysis pipeline that can correctly determine the ground truth from the simulated data
	3. Generate data from libraries we already understand well
	4. Demonstrate that the assay works as expected on SMN2 Data
	5. Issues
		1. I don't know that the Nanopore really brings much additional to downstream experiments unless we have reasons we need the additional length which our possible downstream experiments generally don't seem to need
2. Investigate the determinants of MXE in model exons
	1. Determine the mechanism conveying MXE splicing in PKM
		1. Look for mutations that violate MXE in allelic series
			1. Allelic series generation
				1. ASO
				2. risdaplam sensitive splice site (has this been previously tested)
				3. Differentiating cell type
			2. Mutagenesis methods
				1. epPCR
				2. Purchase twist libraries of random mutants and deletions
					1. It has been shown that MXE behavior is driven by the exon sequences
						1. So these seqs are small enough to be bought
		2. Deeply mutagenize MXE determining features to build quantitative models of their effects
			1. Look for deviation from allelic series
			2. Train deep and principled models to predict sequence effects
		3. Issues
			1. Current minigene shows partial disruption of MXE phenotype
			2. Nanopore is probably largely not needed for this experiment
		4. Can probably target ketohexokinase as well with this strategy...
	2. Build a quantitative understanding of secondary structure effects on MXE splicing in ATE1
		1. Deeply mutagenize features to build quantitative models of their effects
			1. Allelic series generation
				1. ASO
					1. There are ASOs known that disrupt 2ndary structure to modulate MXE-ness
					2. There are ASOs known that disrupt 2ndary structure to modulate exon choice
				2. risdaplam sensitive splice site (This hasn't been previously tested)
			2. Try to understand how secondary structure interacts with other splicing control features by mutagenizing (or drugging) those features while sliding along allelic series
				1. Measure deviation from expected behavior
				2. Train deep and principled models to predict sequence effects
		2. Issues
			1. Current minigene behavior hasn't been characterized in HeLa
				1. But they have shown it in A549 cells
			2. Nanopore is probably largely not needed for this experiment
3. Investigate the behavior of more complicated co-ordinated splicing events
	1. Characterize mechanisms of multi-exon MXE clusters in human contexts
		1. Gene targets
			1. CD55
			2. CUX1
		2. Look for mutations that deviate from MXE
			1. epPCR probably forms mutations first
			2. Then do deep mutagenesis of detected features with twist libraries
		3. Issues
			1. These cassettes have been observed in [[Hatje_et_al-2017-The_landscape_of_human_mutually_exclusive_splicing]] RNA-seq datasets, but have never been experimentally confirmed (at least that I have seen)
			2. Again nanopore is probably not needed
	2. Characterize mechanisms of long distance splicing correlation
		1. Gene targets
			1. MYL1
			2. TPM1
			3. MAPT
		2.  Look for mutations that deviate from MXE
			1. epPCR probably forms mutations first
			2. Then do deep mutagenesis of detected features with twist libraries
		3. Issues
			1. These cassettes have been observed in [[Hatje_et_al-2017-The_landscape_of_human_mutually_exclusive_splicing]] RNA-seq datasets, but have never been experimentally confirmed (at least that I have seen)
			2. Mutagenesis is likely to be difficult on such large substrates

## Original brainstorming
1. Aims
	1. Long-read MPSA and analysis pipeline
	2. Biological application
		1. MXE in cancer relevant genes
		2. Sequence determinants of small molecule splicing drug efficacy
			1. long distance effects on hill coefficient
			2. integration of 5' and 3' splice site strengths
			3.  Small molecule driven intron retention
			4. New 5' library but aimed at doing drug titrations
		3. Use drug titration to cause defined changes in 5'-ss U1 binding energy and look at how this affects splicing processes
			1. MXEs
			2. Cryptic site competition
			3. in connection with a 3'-ss library
			4. Use faster library production techniques to test the 5'-ss library with drug titration across different contexts to look for context effects
			5. We can distinguish cryptic 5'-ss activation
			6. We have protocols worked out, but no one has done it
			7. Mutations seem to be able to change hill coeficient, activate cryptic sites, and change maximal activation. so there is a lot of new biology here
				1. What caused the hill coeficient > 1?
				2. Are there mutants that change hill coeficient?
					1. Certain u6 site mutations maybe?
					2. Can we purposefully separate u1 and u6 binding sites and mutagenize them separately?
					3. Random mutagenesis and look for altered hill coeficient?
			9. Illumina junction sequencing can't get cryptic sites deep in big introns, confidently assess intron retention, or handle MXE. But Illumina junction sequencing is a good backup for if the long reads fail, and allows much deeper sequencing.
