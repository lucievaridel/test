# Metabolomics analysis report
SBL.20004 

31.05.2024

----
Group C
- Thuerler Elias
- Zenuni Bujar
- Varidel Lucie 
----


## Introduction

Following Darwin’s model of evolution, all living beings on earth are related to each other to some extent. Hence, it is a central aspect of biology to classify the phylogenetic relationship between species. The degree of relation between species can be determined on different levels of organization. Living things can be classified by their macroscopic or microscopic characteristics. Macroscopic description of relation can be based on morphology (phenotype) and ecological traits. Microscopic properties on the other hand such as the molecular omics (the study of the whole set of specific molecules in a living unit) can relate species to each other based on their molecular build up. Within the metabolome, specialized metabolites are useful for constructing the phylogenetic tree of plants because those molecules indicate a common ancestor which evolved the required pathway to synthesize this kind of molecules.    

In this study, we have chosen to verify the phylogeny of 9 plants from the economical and societal important *Rosaceae* family (*Malus sylvestris, Malus pumila, Malus floribunda, Prunus tomentosa, Prunus padus, Prunus cerasifera, Drymocallis (Potentilla) rupestris, Potentilla sterilis, Potentilla recta*). Phylogenetically the genus of *Malus* and *Prunus* are closer to each other than *Potentilla*. Due to this relation we wanted to investigate if the metabolome of each species, reflects this classification depicted in Figure 1. The chemotaxonomic relationship between each three genera was determined by comparing their metabolome. The metabolome of each plant was acquired by mass spectrometry.

The phylogenetic tree (Figure 1) of the plants specie investigated in this study shows the relation beteween the genera depending on macroscopic and microscopic properties of the plants. The information was taken from the [NCBI website](https://www.ncbi.nlm.nih.gov/Taxonomy/Browser/wwwtax.cgi) and the phylogenetic tree was generated on [phyloT](https://phylot.biobyte.de/).  

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/image.png)

<p align="center"> Figure 1: Phylogenetic tree of the nine selected species

Mass spectrometry is a method for measuring the abundance of ions with a specific mass to charge ratio in gas phase. The corresponding machine, the mass spectrometer (MS), consists of 3 essential parts: An ion source which converts analytes into ions in gas phase, a mass analyzer which separates the ions corresponding to their mass to charge ratio and a detector which measures the abundance of a specific ion. The output of this method is a spectrum of ion peaks with their mass to charge ratio and intensities (abundance). Mass spectrometers can be coupled to other mass spectrometers to get fragmentation patterns helpful for determining the structure of the ions in the first MS system. Furthermore, a high-pressure liquid chromatography system can be used before injecting the complex samples into the mass spectrometer to get a better separation of the ions and thus make it easier to determine the molecule. 

Mass spectrometers generate an enormous amount of data, impossible for humans to interpret by hand. Therefore, computers are used to do this task. Many different programs exist to analyze the MS output. Such programs and their application will be explained in the methods part.   


## Material & Methods

### Sample collection

Nine samples chosen from the *Rosaceae* family were collected from the Botanical Garden of the University of Fribourg: *[Malus pumila](https://www.inaturalist.org/observations/208861725), [Malus sylvestris](https://www.inaturalist.org/observations/208861749), [Malus floribunda](https://www.inaturalist.org/observations/208861702), [Prunus cerasifera](https://www.inaturalist.org/observations/208861819), [Prunus padus](https://www.inaturalist.org/observations/208861835), [Prunus tomentosa](https://www.inaturalist.org/observations/208861852), [Potentilla sterilis](https://www.inaturalist.org/observations/208861803), [Potentilla rupestris](https://www.inaturalist.org/observations/208861779), [Potentilla recta](https://www.inaturalist.org/observations/208861763)*. These samples were collected for the DBGI project and were registered accordingly on iNaturalist. More details for the nine samples are available [here](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/observations-441128.csv). 

Leaves were collected using a sterilized scalpel and placed into coffee filters. The coffee filters were individually placed in a 50mL Falcon tube prior to drying of the leaves in a freeze dryer for one week. 

### Sample preparation

For each specie ~50mg (Table 1) of the dried leaves were weighted in a 2mL Eppendorf and grinded using metallic beads in a Retsch grinder (2.5min, 25 Hz). 1.7mL of a solvent mixture of 80% methanol, 20% water and 0.1% formic acid were then added. The sample was then centrifugated (2 min, 13’000 rpm). The cleared supernatant was then collected for storage at -80°C. 120µL aliquots were taken to inject in the LC-MS. A quality control (QC) was prepared with a mixture of all the nine samples in equal parts. A blank was prepared with the extraction solvent mixture. 

Table 1: Dried leaf weight for each sample

|Sample                   |Weight [mg]|
|---------------------------|------|
|Malus pumila               |52.2|
|Malus sylvestris           |49.7|
|Malus floribunda           |47.5|
|Prunus cerasifera          |50.9|
|Prunus padus               |51.4|
|Prunus tomentosa           |49.3|
|Potentilla sterilis        |52.5|
|Potentilla rupestris       |50.5|
|Potentilla recta           |51.2|


### LC-MS Analysis

All samples with the blank and the QC were measured in a Liquid Chromatography coupled to a Mass Spectrometer (LC-MS). The Liquid Chromatography was performed with a Reversed phase C18 column. The LC conditions are available [here](https://github.com/commons-teaching/SBL.20004.2024/blob/main/lc_conditions.txt). The Mass Spectrometer had an Electrospray ionization source and the mass analyzer/detector is an orbital ion trap. The MS conditions are available [here](https://github.com/commons-teaching/SBL.20004.2024/blob/main/ms_conditions.txt).

### Data treatment
The raw data were converted to mzML format using [Proteowizard software](https://proteowizard.sourceforge.io). *This step was performed by the lecture supervisor*. The .mzML files were treated using the [MzMine 2.53 software](https://github.com/mzmine/mzmine2/releases). The following steps were performed for each sample: 
1.	Centroid mass peak detection from the total ion chromatogram (MS1 noise level=2.0E4, MS2 noise level=0)
2.	Chromatogram building using the ADAP chromatogram builder (group intensity threshold=2.0E4, minimum highest intensity=6.0E4, m/z tolerance=0.001 m/z, min group size in number of scan=5,)
3.	Chromatogram deconvolution with the ADAP wavelelets algorithm (m/z range for MS2 pairing=0.025 Da, RT range for MS2 pairing=0.15 min, minimum feature height=2.0E4, minimum signal to noise ratio (S/N)=15, RT wavelet range= 0.02-0.09) 
4.	Isotope grouping to remove redundancy using the isotopic peak grouper function (m/z tolerance=0.001 m/z, maximum charge=4, RT tolerance=0.09 min)
5.	Feature alignment using the join aligner function (m/z tolerance = 0.001, RT tolerance = 0.1 min, weight for m/z=75, weight for RT =25)
6.	Gap filling using the peak finder (multithreaded) function (intensity tolerance=10.0%, m/z tolerance = 0.001, retention time tolerance = 0.2 min)
7.	Filtering of the gap-filled features with New Average filter mode (m/z tolerance=0.001 m/z)

The final feature list was exported as both .CSV and .MGF files. Both files with the metadata were uploaded to GNPS to create a molecular network. *This step was performed by the lecture supervisor*. The molecular network was visualized using the [Cytoscape software 3.82](https://cytoscape.org). Statistical analyses were also performed on the dataset. *This step was performed by the lecture supervisor*. 

## Results


### MS1

4380 features were cleaned after finalizing the data treatment. The final feature list is available [here](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/results/mzmine/mapp_batch_00111_quant.csv).

### Statistical analyses

#### Heatmap

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/heatmap_legend.png)

<p align="center"> Figure 2: Heatmap - Abundance of MS features

The heatmap (Figure 2) shows rather clearly distinct groups of features, characteristic for both the *Malus* and *Potentilla* genera, while *Prunus* appears to share its most intense features with the two other groups. As can be seen at the top of the graphic, the similarity tree shows *Potentilla* and *Prunus* as being more closely related to each other than to *Malus*. This is unexpected as this does not reflect the reality of the phylogenetic relationship existing between the three genera, where *Malus* and *Prunus* are closely related and *Potentilla* is more distant.

#### PCA
![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/PCA.png)

<p align="center"> Figure 3: Principal Component Analysis (PCA) on the nine samples

The Principal Component Analysis (PCA) (Figure 3) scores show *Malus* and *Potentilla* as being relatively close in the variable space in comparison to *Prunus*, which is slightly more distant. This stands in contrast to the results given in the heatmap where *Malus* is the clear outlier. Because PCA only allows the visualization of separation across the two main components of the variable space [^15], it could be the case that *Malus* possesses many small variations on least significant components that can not be reflected in this visualization, but are taken into account when making the hitmap and tree. This would explain the apparent contradiction of the results.

#### PCoA

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/PCoA.png)

<p align="center"> Figure 4: Principal Coordinates Analysis (PCoA) on the nine samples

The Principal Coordinates Analysis (PCoA) (Figure 4) shows the three groups to be equidistant. Similarly to the PCA, a lot of variation is lost in this visualization, which could explain the differences with the heatmap’s results. In contrast to the PCA, PCoA requires a calculation of the distances between the points prior to the reduction of the component space. This additional step explains the difference with the PCA results.

#### PLS-DA

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/PLS-DA.png)

<p align="center"> Figure 5: Partial Least-Squares Discriminant Analysis (PLS-DA) on the nine samples

The Partial Least-Squares Discriminant Analysis (PLS-DA) (Figure 5) shows *Malus* and *Prunus* as being closer to one another than to *Potentilla*, the outlier. This is in accordance with the hypothesis that the chemotaxonomy should match the phylogeny of the genera that we analyzed. It is not in accordance, however, with the heatmap, PCA, and PCoA outputs. Contrary to the PCA, the PLS-DA is made while being aware of the group labels [^16]. The calculation then aims to separate the groups by variance rather than to separate the points. Although this returns a result more in line with the initial working hypothesis, it is complicated to take it as gospel given the variety of other results obtained through other methods. No general trend can be discerned.

#### PLS-VIP

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/VIP.png)


<p align="center"> Figure 6: VIP scores in the PLS-DA analysis

The VIP score for the PLS-DA analysis (Figure 6) shows the principal differentiating features between genera. Most features reported appear as single nodes or small connected networks in cytoscape making them difficult to interpret and discuss but some of them are part of bigger clusters which will be discussed in the following parts of this study.

### Molecular Network

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/molecular_network_figure.png)

<p align="center"> Figure 7: Molecular network based on MS features

The molecular network (Figure 7) shows a wide range of trees containing many interconnected nodes. The selection of trees of interest for this study is based on a few criteria. Firstly, because the interest lies in the differentiation of genera, the most important metabolites of the network must be present in more than one species of a given genus. Secondly, the network must contain a sufficient amount of nodes so as to minimize the chances of analyzing an artefact. Lastly, the metabolites of interest should not be present in the blank, or in very small amounts. The following section will show some of the networks meeting these standards.

#### *Potentilla* discriming features
Some features found in this analysis discriminate the *Potentilla* genus from the *Malus* and *Prunus* genera and three will be presented below.

1. **D-sorbitol**

According to the molecular network that was build, D-sorbitol (feature id 11) is found in both the *Malus* and *Prunus* genera but not in the *Potentilla* genus (Figure 8). D-sorbitol accumulation occurs when plants encounter stress conditions and serve as carbon and energy source [^1]. It has been shown that plants rely either on sorbitol or sucrose as the predominant photosynthetic product [^2]. This is the case in the *Malus* and *Prunus* families [^2]. From the molecular network is seems therefore that the *Potentilla* genus rely more on sucrose (Figure 9) and its related compounds than on sorbitol. Indeed sucrose compounds are found mostly in the *Potentilla* genus and less in the *Malus* and *Prunus* families Another study performed in *Prunus armeniaca* relates the sorbitol synthesis and therefore accumulation linked to aging of the leaves [^1], which could be one of the reason for the difference in *Potentilla* if indeed they were older than the others when collected. 

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/d-sorbitol_figure.png)

<p align="center"> Figure 8: MS2 spectra of D-sorbitol and molecular network of D-sorbitol 

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/sucrose_figure.png)

<p align="center"> Figure 9: Molecular network of sucrose and its related compounds

2. **Salicylic acid**

On the molecular network, salicylic acid (feature id 1229) is mostly found in the *Potentilla* genus and not in the *Malus* or *Prunus* genus (Figure 10). Salicylic acid is a phenolic acid involved in plant defense against pathogens and plant growth regulation upon stress [^3]. Salicylic acid is also involved in stress responses such as heat and drought. Reduced levels of salicylic acid show an enhanced susceptibility to pathogens [^4]. It is therefore speculated that the *Potentilla* rely on different defense mechanism than *Malus* and *Prunus*. 

*Note: The full molecular network were the salicylic acid is located is displayed in Figure 13. In Figure 10 a closer screenshot was taken to better vizualise the closely related features of salicylic acid.*

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/salicylic_acid_figure.png)

<p align="center"> Figure 10: MS2 spectra of salicylic acid and molecular network of salicylic acid 

3. **Imidurea (Imidazolidinyl urea)**

On the molecular network, imidurea (feature id 1942) is mostly in found in the *Potentilla* genus and less present in both the *Malus* and *Prunus* families (Figure 11). Imidurea is known to exhibit antimicrobial agent properties against various microorganisms and is used in pharmaceutical and cosmetic products [^5]. It is therefore speculated that imidurea might be linked to a plant defense mechanism, which would align with the speculation made in the previous paragraph, that *Potentilla* have different defense mechanism compared to the two other genera. 

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/imidurea_figure.png)

<p align="center"> Figure 11: MS2 spectra of imidurea (imidazolidinyl urea) and molecular network of imidurea (imidazolidinyl urea)

#### *Malus* discriming features
Some features found in this analysis discriminate the *Malus* genus from the *Potentilla* and *Prunus* genera and will be presented below.

1. **Flavonoids**

Phloretin (feature id 1), Phlorizin (feature id 16), Naringenin (feature id 134) were identified from the molecular network. They are all classified as flavonoids, which also make the most abundant metabolite group of the *Malus* genus. Flavonoids are polyphenolic Flavan derivates present in plants. In general, flavonoids are biochemically synthesized in plants via the shikimate pathway. [^6]

Phloretin and Phlorizin are specially interesting because they were found only in the *Malus* genus at equal parts for each species in this study (Figure 12), making them a good distinguishing factor for this genus. Regarding that phloretin was exclusively found in the *Malus* genus (see [Phloretin](https://lotus.naturalproducts.net/compound/lotus_id/LTS0003293) and [Phlorizin](https://lotus.naturalproducts.net/compound/lotus_id/LTS0198771 ) entries on [Lotus](https://lotus.naturalproducts.net)) and it is structurally very similar to phlorizin because it is the glycoside of phloretin, it makes sense that phlorizin is also found exclusively in this genus. 

Naringenin is a flavonoid found enriched the *Malus* genus (*Malus pumila and Malus domestica*). In the molecular network (Figure 12) there was shown that also a smaller part of the Naringenin clade was included in the *Potentilla* and *Prunus* genus. The Naringenin node conversely represents only the *Malus* genus making it also a distinguishing factor for the genus.

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/flavonoid_figure.png)

<p align="center"> Figure 12: MS2 spectra of phloretin, phlorizin and naringenin and molecular network of phloretin, phlorizin and naringenin

2. **p-Coumaric acid**

p-coumaric acid (feature id 847) is a hydroxycinnamic acid and is normally found in the fruits of *Malus domestica* and in the bark of *Prunus serotina* [^7]. Interestingly, we found that the *Malus* genus has this molecule and other similar molecules in common with *Potentilla* and *Prunus*. The enrichment of p-coumaric acid in *Malus* is bigger than in *Potentilla* and *Prunus* (Figure 13). The whole clade of similar structures is distributed over all genera. Some of the nodes are exclusively for one genus and others are shared between all three or between two of the genera. In general, the clade of p-Coumaric acid shows similarities in the metabolome of all three genera. Looking closer to the relative distribution of the nodes, there are some sub-clades that are exclusive for one genus and can be distinguished from the other nodes.  

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/p_coumaric_acid.png)

<p align="center"> Figure 13: MS2 spectra of p-coumaric acid and molecular network of p-coumaric acid

#### *Prunus* discriming features

Only few features found in this analysis discriminate the *Prunus* genus from the *Malus* and *Potentilla* genera and one will be present below.

1. **Arecatannin A2**

Arecatannin A2 (feature id 2027, 3790) is found mainly in the *Prunus* genus along with procyanidin B2 (feature id 549, 2885) and procyanidin C1(feature id 1879, 2806) (Figure 14). These molecules are all proanthocyanidins and procyanidin oligomers.
 
Arecatannin A2 is a tetramer mostly known for its presence in *Areca catechu* L. (betel nut or areca nut)[^8], a type of fruit often chewed in southern Asia as part of its cultural and medicinal tradition. While betel nut utilization has been linked with oral forms of cancer, some epicatechin oligomers (such as arecatannin A3 but not A2) have been highlighted as possible anti-cancer agents [^9].
Procyanidin B2 is a dimer also coming from betel nuts [^8]. It is an antioxidant that is present in other species as well, such as *Cinchona pubescens, Cinnamomum verum, Vitis vinifera* and plenty more. Most notably for this study perhaps, it is also found in apples [^10]. 
Procyanidin C1 is a trimer that has been shown to have senotherapeutic activity and chemotherapy enhancing properties in preclinical studies conducted in mice models [^11]. Like procyanidin B2, it can be found in cinnamon [^12] and apples [^13]. 

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/arecatannin_a2_figure.png)
![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/procyanidin.png)

<p align="center"> Figure 14: MS2 spectra of Arecatannin A2, Procyanidin B2, Procyanidin C1 and their molecular network 

The major features of the network are overwhelmingly abundant in at least two species of *Prunus* (Figure 14), while research papers state that at least two of them are notably found in apples (*Malus*). This surprising result could be explained by the fact that the samples used in this study come from plant leaves and not fruits, on which previous research has been done. Minor features, meanwhile, show differences in their provenance. With proanthocyanidins being regarded as functional and health improving ingredients in beverages, food, and herbal remedies [^14], their proportional abundance in the leaves of the Prunus genus could be an interesting starting point to investigate their presence in other parts of the plants and how they compare with other species known to contain these metabolites.

## Conclusion

This study aimed at verifying the proximity on the phylogenetic tree for the three different generea, *Potentilla*, *Malus* and *Prunus* through their metabolome. The study was performed in triplicates, indeed three species for each genus were taken for the study. After performing an untargetted LC-MS analysis on the nine samples and extracting interesting MS features a molecular network was created along with statistical analyses. Our hypothesis could not be verified through the statistical analyses, indeed mixed results were obtained from them. Some reasons might be that the three genera are too close to each other and their metabolome is not different enough to discriminate the *Potentilla*. Another reason could be that chosing three species in each genus is to few replicas to encapsulate the metabolome of the corresponding genus. 

The PCA discriminates the *Prunus* genus although the PCoA does not and the heatmap clearly shows that the *Prunus* genus has many commonalities to the two others and very few discrimining features. Arecatannin A2, Procyanidin B2 and C1 compounds are the features that are overly represented in the *Prunus* genus. In the litterature Arecatannin A2 presence is reported in the *Malus* genus and no information is found on *Prunus* species. In this study we report the presence of Arecatannin A2 and its spectrally related compounds. 

The heatmap places the *Malus* genus more distant to the *Potentilla* and the *Prunus* genera. By analyzing the molecular network it was found that the *Malus* genus is enriched in Falvonoid compounds such as Phloretin, Phlorizin and Naringenin. Because these features are abundant and present in higher levels in the *Malus* it is not impossible that this makes the *Malus* genus deviate from the two other genera in the statistical analysis. 

The PLS-DA analysis successfully discriminate the *Potentilla* genus from the *Malus* and *Prunus* genera, but giving all the other statistical analyses and the fact that PLS-DA is a directed analysis this result does not seem to hold much weight. Interestingly, in the molecular networks it seems that the *Potentilla* rely on a different photosynthetic product than *Malus* and *Prunus*. Indeed sucrose was enriched in *Potentilla* whereas d-sorbitol was exclusively found in *Malus* and *Prunus*. Also we speculate that the some defense mechanisms of *Potentilla* are slightly different compared to those of *Malus* and *Prunus* because of the difference in sialic acid and imidurea levels.  

# References

[^1]: I. Pleyerová, J. Hamet, H. Konrádová, and H. Lipavská, “Versatile roles of sorbitol in higher plants: luxury resource, effective defender or something else?,” Planta, vol. 256, no. 1. Springer Science and Business Media Deutschland GmbH, Jul. 01, 2022. doi: 10.1007/s00425-022-03925-z.
[^2]: L. Li, M. Li, J. Wu, H. Yin, J. M. Dunwell, and S. Zhang, “Genome-wide identification and comparative evolutionary analysis of sorbitol metabolism pathway genes in four Rosaceae species and three model plants,” BMC Plant Biol, vol. 22, no. 1, Dec. 2022, doi: 10.1186/s12870-022-03729-z.
[^3]: C. Kaya, F. Ugurlar, M. Ashraf, and P. Ahmad, “Salicylic acid interacts with other plant growth regulators and signal molecules in response to stressful environments in plants,” Plant Physiology and Biochemistry, vol. 196. Elsevier Masson s.r.l., pp. 431–443, Mar. 01, 2023. doi: 10.1016/j.plaphy.2023.02.006.
[^4]: G. Loake and M. Grant, “Salicylic acid in plant defence-the players and protagonists,” Current Opinion in Plant Biology, vol. 10, no. 5. pp. 466–472, Oct. 2007. doi: 10.1016/j.pbi.2007.08.008.
[^5]: J. Gao, D. Che, X. Du, Y. Zheng, H. Jing, and N. Wang, “Imidazolidinyl urea activates mast cells via MRGPRX2 to induce non-histaminergic allergy,” Toxicol Res (Camb), vol. 10, no. 3, pp. 467–475, May 2021, doi: 10.1093/toxres/tfab035.
[^6]: Panche AN, Diwan AD, Chandra SR. Flavonoids: an overview. J Nutr Sci. 2016 Dec 29;5:e47. doi: 10.1017/jns.2016.41. PMID: 28620474; PMCID: PMC5465813.
[^7]: Tehami W, Nani A, Khan NA, Hichami A. New Insights Into the Anticancer Effects of p-Coumaric Acid: Focus on Colorectal Cancer. Dose Response. 2023 Jan 4;21(1):15593258221150704. doi: 10.1177/15593258221150704. PMID: 36636631; PMCID: PMC9830577.
[^8]: Gen-ichiro Nonaka, B., Hsu, F., & Nishioka, I. (1981). Structures of Dimeric, Trimeric, and Tetrarneric Procyanidins from Areca catechu L.
[^9]: Patel, A., Patel, M., Tshering, P., Koyyala, V. P. B., & Ghadyalpatil, N. (2023). Chewing Doma (Fermented Betel Nut): Culture versus Cancer? In South Asian Journal of Cancer. Georg Thieme Verlag. https://doi.org/10.1055/s-0043-1764216
[^10]: National Center for Biotechnology Information. (2024). PubChem Compound Summary for CID 122738, Procyanidin B2, (+)-. PubChem. https://pubchem.ncbi.nlm.nih.gov/compound/Procyanidin-B2
[^11]: Xu, Q., & Fu, Q. ✉. (2021). The flavonoid procyanidin C1 has senotherapeutic activity and increases lifespan in mice. Nature Metabolism, 3. https://doi.org/10.1038/s42255-021-00491-8
[^12]: Sun, P., Li, K., Wang, T., Ji, J., Wang, Y., Chen, K.-X., Jia, Q., Li, Y.-M., & Wang, H.-Y. (2019). Procyanidin C1, a Component of Cinnamon Extracts, Is a Potential Insulin Sensitizer That Targets Adipocytes. https://doi.org/10.1021/acs.jafc.9b02932
[^13]: Nakano, N., Nishiyama, C., Tokura, T., Nagasako-Akazome, Y., Ohtake, Y., Okumura, K., & Ogawa, H. (2008). Procyanidin C1 from Apple Extracts Inhibits Fc RI-Mediated Mast Cell Activation. Int Arch Allergy Immunol, 147, 213–221. https://doi.org/10.1159/000142044
[^14]: Aron, P. M., & Kennedy, J. A. (2008). Review Flavan-3-ols: Nature, occurrence and biological activity. Mol. Nutr. Food Res, 52, 79–104. https://doi.org/10.1002/mnfr.200700137
[^15]: Plumb, R. S., Granger, J. H., & Stumpf, C. L. (2004). AN EXPLANATION OF PRINCIPAL COMPONENTS ANALYSIS (PCA) FOR METABONOMICS.
[^16]: Ruiz-Perez, D., Guan, H., Madhivanan, P., Mathee, K., & Narasimhan, G. (2020). So you think you can PLS-DA? BMC Bioinformatics, 21. https://doi.org/10.1186/s12859-019-3310-7
