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

Nine samples chosen from the Rosaceae family were collected from the Botanical Garden of the University of Fribourg (link): *[Malus pumila](https://www.inaturalist.org/observations/208861725), [Malus sylvestris](https://www.inaturalist.org/observations/208861749), [Malus floribunda](https://www.inaturalist.org/observations/208861702), [Prunus cerasifera](https://www.inaturalist.org/observations/208861819), [Prunus padus](https://www.inaturalist.org/observations/208861835), [Prunus tomentosa](https://www.inaturalist.org/observations/208861852), [Potentilla sterilis](https://www.inaturalist.org/observations/208861803), [Potentilla rupestris](https://www.inaturalist.org/observations/208861779), [Potentilla recta](https://www.inaturalist.org/observations/208861763)*. These samples were collected for the DBGI project and were registered accordingly on iNaturalist. More details for the nine samples are available here (link observations files). 
Leaves were collected using a sterilized scalpel and placed into coffee filters. The coffee filters were individually placed in a 50mL Falcon tube prior to drying of the leaves in a freeze dryer for one week. 


- Link to the iNaturalist entries of your species.

You can link a csv that you upload on github.
Go to the export link of the DBGI project on inaturalist https://www.inaturalist.org/observations/export?projects=digital-botanical-gardens-initiative
Apply eventual filters (fo rexample by username)
Save the csv and upload to github.


Example see [table X](https://github.com/commons-teaching/SBL.20004.2022/blob/main/data/observations-238383.csv) 

### Sample preparation

For each specie ~50mg (**Table 1**) of the dried leaves were weighted in a 2mL Eppendorf and grinded using metallic beads in a Retsch grinder (2.5min, 25 Hz). 1.7mL of a solvent mixture of 80% methanol, 20% water and 0.1% formic acid were then added. The sample was then centrifugated (2 min, 13’000 rpm). The cleared supernatant was then collected for storage at -80°C. 120µL aliquots were taken to inject in the LC-MS. A quality control (QC) was prepared with a mixture of all the nine samples in equal parts. A blank was prepared with the extraction solvent mixture. 

**Table 1**: Dried leaf weight for each sample

|Specie                     |Weight [mg]|
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
The raw data were converted to mzML format using Proteowizard software (link). *This step was performed by the lecture supervisor*. The .mzML files were treated using the MzMine 2.53 software (link). The following steps were performed for each sample: 
1.	Centroid mass peak detection from the total ion chromatogram (MS1 noise level=2.0E4, MS2 noise level=0)
2.	Chromatogram building using the ADAP chromatogram builder (group intensity threshold=2.0E4, minimum highest intensity=6.0E4, m/z tolerance=0.001 m/z, min group size in number of scan=5,)
3.	Chromatogram deconvolution with the ADAP wavelelets algorithm (m/z range for MS2 pairing=0.025 Da, RT range for MS2 pairing=0.15 min, minimum feature height=2.0E4, minimum signal to noise ratio (S/N)=15, RT wavelet range= 0.02-0.09) 
4.	Isotope grouping to remove redundancy using the isotopic peak grouper function (m/z tolerance=0.001 m/z, maximum charge=4, RT tolerance=0.09 min)
5.	Feature alignment using the join aligner function (m/z tolerance = 0.001, RT tolerance = 0.1 min, weight for m/z=75, weight for RT =25)
6.	Gap filling using the peak finder (multithreaded) function (intensity tolerance=10.0%, m/z tolerance = 0.001, retention time tolerance = 0.2 min)
7.	Filtering of the gap-filled features with New Average filter mode (m/z tolerance=0.001 m/z)

The final feature list was exported as both .CSV and .MGF files. Both files with the metadata were uploaded to GNPS to create a molecular network. *This step was performed by the lecture supervisor*. The molecular network was visualized using the Cytoscape software 3.82 (link). Statistical analyses were also performed on the dataset. *This step was performed by the lecture supervisor*. 

## Results


### MS1

How many features could you clean in your final peak list ?
A link to the final feature list (uploaded to github).

### Molecular Network

Screenshots of your molecular network and of some clusters of interest.
Link to the GNPS job.
Link to the GNPS identification table.

## Conclusion

Some conclusion that you could get out of this preliminary study.

# References

Note that you can make a footnote like this [^1]

[^1]: Ref X
