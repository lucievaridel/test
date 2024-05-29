# Metabolomics analysis report
SBL.20004 

31.05.2024

----
Group X
- Thuerler Elias
- Zenuni Bujar
- Varidel Lucie 
----


## Introduction

Some words on the backgorund of your projects.
Which plants did you select and why ?

## Material & Methods

### Sample collection

Nine samples chosen from the Rosaceae family were collected from the Botanical Garden of the University of Fribourg: *[Malus pumila](https://www.inaturalist.org/observations/208861725), [Malus sylvestris](https://www.inaturalist.org/observations/208861749), [Malus floribunda](https://www.inaturalist.org/observations/208861702), [Prunus cerasifera](https://www.inaturalist.org/observations/208861819), [Prunus padus](https://www.inaturalist.org/observations/208861835), [Prunus tomentosa](https://www.inaturalist.org/observations/208861852), [Potentilla sterilis](https://www.inaturalist.org/observations/208861803), [Potentilla rupestris](https://www.inaturalist.org/observations/208861779), [Potentilla recta](https://www.inaturalist.org/observations/208861763)*. These samples were collected for the DBGI project and were registered accordingly on iNaturalist. More details for the nine samples are available [here](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/observations-441128.csv). 

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

### Molecular Network

The GNPS work produced a molecular network (Figure 1) and some interesting features will be discussed in the sections below 
**Add GNPS job and identification table**

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/molecular_network_figure.png)

<p align="center"> Figure 1: Molecular network 

#### Potentilla discriming features
Some features found in this analysis discriminate the *Potentilla* family and three will be presented below.

1. **D-sorbitol**


According to the molecular network that was build, D-sorbitol (feature id 11, 182.17 m/z) is found in both the *Malus* and *Prunus* family but not in the *Potentilla* family (Figure 1). D-sorbitol accumulation occurs when plants encounter stress conditions and serve as carbon and energy source [^1]. It has been shown that plants rely either on sorbitol or sucrose as the predominant photosynthetic product [^2]. This is the case in the *Malus* and *Prunus* families [^2]. From the molecular network is seems therefore that the *Potentilla* family rely more on sucrose (Figure 2) and its related compounds than on sorbitol. Indeed sucrose compounds are found mostly in the *Potentilla* family and less in the *Malus* and *Prunus* families Another study performed in *Prunus armeniaca* relates the sorbitol synthesis and therefore accumulation linked to aging of the leaves [^1].

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/d-sorbitol_figure.png)

<p align="center"> Figure 1: MS2 spectra of D-sorbitol and molecular network of D-sorbitol 

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/sucrose_figure.png)

<p align="center"> Figure 2: Molecular network of sucrose and its related compounds

2. **Salicylic acid**

On the molecular network, salicylic acid (feature id 1229, 139.04 m/z) is mostly found in the *Potentilla* family and not in the *Malus* or *Prunus* family (Figure 3). Salicylic acid is a phenolic acid involved in plant defense against pathogens and plant growth regulation upon stress [^3]. Salicylic acid is also involved in stress responses such as heat and drought. Reduced levels of salicylic acid show an enhanced susceptibility to pathogens [^4]. 

*Note: The full molecular network were the salicylic acid is located is displayed in Figure ???? (Bujar). In Figure 3 a closer screenshot was taken to better vizualise the closely related features of salicylic acid*

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/salicylic_acid_figure.png)

<p align="center"> Figure 3: MS2 spectra of salicylic acid and molecular network of salicylic acid 

3. **Imidurea (Imidazolidinyl urea)**

On the molecular network, imidurea (feature id 1942, 411.09 m/z) is mostly in found in the *Potentilla* family and less present in both the *Malus* and *Prunus* families (Figure 4).  Imidurea is known to exhibit antimicrobial agent properties against various microorganisms and is used in pharmaceutical and cosmetic products [^5]. It is therefore speculated that imidurea might be linked to a plant defense mechanism. 

![image](https://github.com/commons-teaching/SBL.20004.2024/blob/main/docs/mapp_project_00050/mapp_batch_00111/report/figures_report/imidurea_figure.png)

<p align="center"> Figure 4: MS2 spectra of imidurea (imidazolidinyl urea) and molecular network of imidurea (imidazolidinyl urea)



Screenshots of your molecular network and of some clusters of interest.
Link to the GNPS job.
Link to the GNPS identification table.

## Conclusion

Some conclusion that you could get out of this preliminary study.

# References

[^1]: I. Pleyerová, J. Hamet, H. Konrádová, and H. Lipavská, “Versatile roles of sorbitol in higher plants: luxury resource, effective defender or something else?,” Planta, vol. 256, no. 1. Springer Science and Business Media Deutschland GmbH, Jul. 01, 2022. doi: 10.1007/s00425-022-03925-z.
[^2]: L. Li, M. Li, J. Wu, H. Yin, J. M. Dunwell, and S. Zhang, “Genome-wide identification and comparative evolutionary analysis of sorbitol metabolism pathway genes in four Rosaceae species and three model plants,” BMC Plant Biol, vol. 22, no. 1, Dec. 2022, doi: 10.1186/s12870-022-03729-z.
[^3]: C. Kaya, F. Ugurlar, M. Ashraf, and P. Ahmad, “Salicylic acid interacts with other plant growth regulators and signal molecules in response to stressful environments in plants,” Plant Physiology and Biochemistry, vol. 196. Elsevier Masson s.r.l., pp. 431–443, Mar. 01, 2023. doi: 10.1016/j.plaphy.2023.02.006.
[^4]: G. Loake and M. Grant, “Salicylic acid in plant defence-the players and protagonists,” Current Opinion in Plant Biology, vol. 10, no. 5. pp. 466–472, Oct. 2007. doi: 10.1016/j.pbi.2007.08.008.
[^5]: J. Gao, D. Che, X. Du, Y. Zheng, H. Jing, and N. Wang, “Imidazolidinyl urea activates mast cells via MRGPRX2 to induce non-histaminergic allergy,” Toxicol Res (Camb), vol. 10, no. 3, pp. 467–475, May 2021, doi: 10.1093/toxres/tfab035.

