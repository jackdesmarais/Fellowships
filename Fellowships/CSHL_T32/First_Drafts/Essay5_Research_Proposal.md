# Prompt
Please provide a brief narrative description of your proposed research project. 
2 page maximum

# Outline
1. goal
	1. Investigate the mechanisms and regulation of mutually exclusive splicing through the lens of PKM and KHK mis-regulation in cancer
2. Cancer relevance
	1. PKM and KHK are alternatively spliced in human disease including cancer
		2. KHK Hepatocellular carcinoma
		3. PKM - lung carcinoma, colorectal cancer, breast cancer 
			1. Also kidney, cervical, and breast cancer cancer/immortalized cell lines
	2. Alternate splicing drives characteristic changes in cancer cell metabolism
		1. KHK - Reduction in fructose metabolism up regulation of glycolysis
		2. PKM - Conversion of metabolism to aerobic glycolysis (the warburg effect)
	3. This alternative splicing has been shown to be important for disease progression in hepatocellular carcinoma (KHK) and lung carcinoma (PKM)
3. Questions
	1. What sequences are important for regulating MXE in these genes
	2. How do factors like splice site strength and SE/SS sequences control MXE selection
	3. What factors are important for ensuring xor behavior
	4. How can these insights guide the use of ASO's or splice modifying drugs for the treatment of splicing dependent cancers
4. Experiments
	1. Expand Kinney lab splicing assay
		1. Long read sequencing based assay to measure a variety of possible alternate isoforms
		2. Get the assay working in cell lines with different MXE splicing profiles
	2. cas13 guide tiling
		1. Objective: Generate a map of how occluding different parts of the pre-mRNA sequence changes splicing outcomes
			1. Help to map important regulatory elements
			2. Hopefully indicates sites interesting to target with ASO therapies in a much cheaper and easier experiment
		2. Perform experiments in cell lines with different MXE splicing patterns
			1. Cancerous and non Cancerous cells
			2. Different tissues where the splicing is different
		3. Compare interesting guides to ASOs targeting the same sites to confirm that the cas13 experiment identifies interesting ASO targets
	3. Minigene MSE competition assays
		1. Objective: Measure the effect of different regulatory sequences at much finer grain
		2. Make minigenes from MXEs
		3. Confirm that they recapitulate MXE behavior in the proper cell types
		4. Measure the effects of targeted libraries
			1. 5'-ss, 3'-ss, bp, new regulatory elements identified in the cas13 screen
		5. Measure the effects of changing 5'-ss strength on competition using 5'-ss libraries and splice modifying drugs
	4. Use the data to inform models
		1. Objective: develop mechanistic and computational models of MXE exon selection
			1. Understand how different regulatory sequences interact to drive exon selection
			2. Predict interventions to change exon selection
		3. Use large RNA-seq datasets (Hatje et al) and data we generate to inform models
		4. Consider both large ML models and curated mechanistic models

