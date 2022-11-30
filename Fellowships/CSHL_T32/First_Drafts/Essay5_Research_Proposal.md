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

# Draft

When human genes are transcribed, the pre-mRNA produced contains both introns and exons.[^cite] This pre-mRNA must then be spliced to remove the introns and stitch together the exons to make an mRNA that can be translated.[^cite] Greater than 95% of human multi-exon genes can be spliced differentially to generate different mRNAs.[^cite] One form of alternate splicing is to have a set of potential exons where only one of the set is selected to be included in the final transcript.[^cite] These are known as mutually exclusive exons (MXEs). As this allows different sections of the final protein to be switched out, it is perhaps not surprising that this process is regulated to produce programmed changes across cell types and developmental stages[^Hatje2017-oj] or that this regulation can be subverted in cancer.[^Wang2012-dr][^Li2016-kt][^Christofk2008-bu] 

In fact, the conversion of Pyruvate Kinase M (PKM) from the adult isoform (PKM1) to the embryonic isoform (PKM2) by a splicing change where exon 9 is repressed and exon 10 is activated is a primary driver of the Warburg effect. Accordingly this isoform change is seen in samples of lung, colorectal, breast, kidney, and cervical cancers and has been shown to be important for lung cancer progression in xenograft studies.[^Wang2012-dr] [^Christofk2008-bu] Similarly, the gene ketohexokinase (KHK) undergoes a switch from the C  (KHKC) to A (KHKA) isoforms in hepatocellular carcinoma driving a reduction in fructose consumption and an increase in nucleotide synthesis from glycolysis.[^Li2016-kt] This change is important for disease progression in xenograft models and correlates with worse patient outcomes when observed in tumor samples.[^Li2016-kt] 

Much of our current knowledge about splicing has been gained from low throughput experiments which can only interrogate small numbers of variants or mining of RNA-seq datasets which only report on natural changes in isoform abundance. However, new techniques in high throughput variant screening make it possible to assay many tens or hundreds of thousands of of perturbations in parallel. This provides an opportunity for gathering information about the regulation of splicing events at a much faster rate. Synergistically, advances in data analysis and modeling are allowing us to leverage these larger datasets.

I am interested in using high throughput screening and computational modeling to study the mechanisms behind the regulation of splicing in mutually exclusive exons. I will use the exons of PKM and KHK that are misregulated in cancer as a lens to focus on this issue. More particularly, I am interested in the following questions: What sequences are important for regulating the MXE in these genes? How do factors like splice site strength and splice enhancer or splice suppressor sequences control MXE in these genes? What factors are important for causing mutual exclusivity in these systems? Finally, do these insights suggest mechanisms for altering MXE splicing to treat cancers? 

In order to answer these questions I propose a series of four experiments. In the first experiment, I will expand the Kinney lab multiplex assay of variant effect (MAVE) for splicing outcomes to use single-cell, single-gene, long-read sequencing for quantification of all splicing isoforms produced in each cell. In the second experiment, I will use this assay and dCas13 guide tilling to map locations in the gene where binding to the pre-mRNA causes changes in splicing. In the third experiment, I will use mini-genes to measure the effects of libraries of mutations in splice sites or regulatory elements on the splicing patterns of these MXEs in the context of splice modifying drugs to map regulatory elements at much finer grain and assess the effect of element strength on MXE competition. In the final aim, I will use data from these experiments to build models of how regulatory sequences interact to determine splicing outcomes.

In past MAVE experiments of splicing amplification with junction specific primers followed by short read sequencing has been used to measure splicing efficiency.[^Wong2018-vq] However, while this technique worked well it was only capable of assaying for expected splice variants. In recent years, droplet based single cell long read techniques have been developed to enable splicing isoform characterization on the single cell level.[^AlKhafaji2021-ra][^Gupta2018-lp] However these systems are unfocused spending reads on all of the RNAs present in the cell. In order to make these methods amenable to the MAVE context, where much deeper sequencing is needed but the focus is on a single transcript, I will use beads with primers designed to just amplify the relevant transcript. This will allow unbiased quantification of the isoforms produced from a single gene in response to thousands of different mutations or guide RNAs. 

With this new technique in hand, I will turn to mapping the regulatory elements that control MXE splicing in PKM and KHK. One way to map regulatory elements is to systematically disrupt different segments of a gene to see how that effects the regulation of the process of interest. However when mutating a gene to map regulatory elements it can be difficult to rule out the possibility that the mutation introduced a new regulatory element instead of just removing an old one. Stericly occluding regulatory elements is one way around this issue as it doesn't make any changes to the underlying sequence. Steric occlusion of regulatory sites is the operating principle behind antisense oligonucleotide (ASO) splice modifying drugs, however, ASOs must be chemically modified which means they must be artificially synthesized and cannot be genetically encoded. This makes it more difficult to screen tilling libraries of ASOs against a genes of interest. Cas13 is an RNA guided RNA nuclease, and it's nuclease inactivated form dCas13 is an RNA guided RNA binding protein.[^Konermann2018-bx] The binding of dCas13 to a transcript has been shown to alter the splicing of that transcript.[^Konermann2018-bx][^Leclair2020-vs] In order to map splicing regulatory elements that control MXE splicing in PKM and KHK, I will generate tiling libraries, where dCas13 is targeted to a sliding window along the gene sequence. I will then use single-cell single-gene long read RNA-seq to measure the effects of occlusion on splice isoform production. In addition to providing a map of the sequences important for regulating MXE splicing, these results might identify sequences that are imporant for mutual exclusivity or that cause both exons to be lost helping to flesh out what enforces the mutual exclusivity of these exons. I can repeat these experiments in both cancerous and noncancerous cells and across cancer types to look at how the regulatory landscape changes in these different contexts. The results of these assays can also be validated using synthesized ASOs. If the observed results correlate with those produced by ASO treatment, this could suggest that dCas13 based screens could be used as an easier alternative to ASO screens for ASO candidate nomination. 

While these guide tilling screens will provide a global look at splicing regulation, they have a couple of important shortfalls. They don't have the ability to tune the strength of a regulatory element and they can have limited resolution due to the length of the guide and the presence of very closely homologous sequences in MXEs. So I need a different technique to allow me to ask more targeted questions about the effects of particular regions on splicing regulation. For finer grained evaluation of regulatory sequences, I will use a mini-gene based assay. In this assay, a region of a gene containing the differentially spliced exons and their neighbors is cloned into a plasmid so it can be directly manipulated. This plasmid can then be transfected into the appropriate cell types and the splicing outcomes observed. I will use minigene assays to build much finer grained understandings of how the strengths of  various regulatory elements mediate the competition between the two MXEs. I will build this finer grained understanding by making libraries of minigenes with mutagenized regulatory elements such as 5'-splice sites, 3'-splice sites, Branch points, known regulatory sites, or new regulatory elements identified through guide tilling. By generating large libraries of these elements, I will be able to see how smoothly strengthening or weakening that element affects the outcome of splicing in order to learn about how that sequence plays a role in regulation. To gain even more precise estimates, I can assay minigene libraries in the context of a risdaplam or branaplam sensitive 5' splice site and measure changes in splicing outcomes for each library member as a function of the concentration of the small molecule. This will allow precise measurements of how different elements interact with smooth changes in 5' splice site strength. Similarly, the expression of known splicing factors can be changed or experiments can be performed across healthy and cancer cell lines to derive information about how these regulatory sequences interact with the cellular complement of splicing factors.  

Finally, I will use the information generated by these screens to inform mechanistic models MXE splicing in PKM and KHK. I will consider a variety of kinetic, thermodynamic, and more general models and evaluate them against the results of the minigene experiments. By doing this I can quantify the predictions of hypotheses and design experiments to test these predictions. I will iterate in this fashion, going back between modeling and minigene assays to refine and test understanding of the mechanistic details of MXE splicing regulation. A mechanistic understanding of splicing regulation will allow predictions of how adjustments to splice factor expression levels or the blocking of interactions with an ASO will affect splicing. This will providing a deeper understanding of the basic biology of splicing and predicting efficacious interventions to treat cancers that rely on aberrant splicing events. 

In this proposal, I have set out a plan for using single-cell single-gene RNA-seq, Cas13 tilling screens, minigene libraries, and mechanistic modeling to understand the regulation of MXE splicing in PKM and KHK. Understanding the regulation of these genes offers a window into a deeper understanding of MXE splicing in general and an opportunity to understand a unique aspect of cancer biology. The difference between normal and cancerous cells in their splicing of these MXEs and the importance of the alternate isoforms in the progression of the cancers makes these MXEs potentially interesting targets for splice modifying drugs. 

[^Hatje2017-oj]: Hatje, K. _et al._ The landscape of human mutually exclusive splicing. _Mol. Syst. Biol._ **13**, 959 (2017)
[^Wang2012-dr]: Wang, Z. _et al._ Exon-centric regulation of pyruvate kinase M alternative splicing via mutually exclusive exons. _Journal of molecular_ (2012)
[^Li2016-kt]: Li, X. _et al._ A splicing switch from ketohexokinase-C to ketohexokinase-A drives hepatocellular carcinoma formation. _Nat. Cell Biol._ **18**, 561–571 (2016)
[^Christofk2008-bu]: Christofk, H. R. _et al._ The M2 splice isoform of pyruvate kinase is important for cancer metabolism and tumour growth. _Nature_ **452**, 230–233 (2008)
[^Wong2018-vq]: Wong, M. S., Kinney, J. B. & Krainer, A. R. Quantitative Activity Profile and Context Dependence of All Human 5’ Splice Sites. _Mol. Cell_ **71**, 1012–1026.e3 (2018)
[^AlKhafaji2021-ra]: Al’Khafaji, A. M. _et al._ High-throughput RNA isoform sequencing using programmable cDNA concatenation. _bioRxiv_ 2021.10.01.462818 (2021) doi:10.1101/2021.10.01.462818
[^Gupta2018-lp]: Gupta, I. _et al._ Single-cell isoform RNA sequencing characterizes isoforms in thousands of cerebellar cells. _Nat. Biotechnol._ (2018) doi:10.1038/nbt.4259
[^Konermann2018-bx]: Konermann, S. _et al._ Transcriptome engineering with RNA-targeting type VI-D CRISPR effectors. _Cell_ **173**, 665–676.e14 (2018)
[^Leclair2020-vs]: Leclair, N. K. _et al._ Poison Exon Splicing Regulates a Coordinated Network of SR Protein Expression during Differentiation and Tumorigenesis. _Mol. Cell_ **80**, 648–665.e9 (2020)