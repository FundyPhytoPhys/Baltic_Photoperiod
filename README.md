# Baltic_Photoperiod

## Summary

Analyses of the responses of Baltic picocyanobacteria, of distinct pigment compositions, to changes in photoperiod and growth light level.

## Highly Qualified Personnel

- Douglas A. Campbell, Mount Allison University, dcampbel@mta.ca, ORCID 0000-0001-8996-5463

## Principle Investigators

- Sylwia Sliwinska-Wilczewska, Mount Allison University, ssliwinskawilczews@mta.ca, ORCID 0000-0002-3147-6605

## Primary Contact  

- Douglas A. Campbell, Mount Allison University, dcampbel@mta.ca, ORCID 0000-0001-8996-5463

## Data sources

- Provide links to any data used from external providers.

## Funding sources

- List your funding sources, grant names, and grant numbers as applicable.

## Keywords

Light intensity, PAR, PC-rich strain, PE-rich strain, Photic regime, Photoperiod, picocyanobacteria, PUR

## Additional information and support

- Sensitive Data Flag - Human Participants:  NO
- Sensitive Data Flag - Indigenous Partnerships: NO
- Sensitive Data Flag - Government Partnerships: NO
- Sensitive Data Flag - Industry Partnerships: NO
- Access Restrictions

## Software  

The software (and version) used to create the dataset:

R version 4.2.2 (2022-10-31 ucrt) -- "Innocent and Trusting"
Copyright (C) 2022 The R Foundation for Statistical Computing
Platform: x86_64-w64-mingw32/x64 (64-bit)

## Repo content information

This chapter summarize the structure of the repository with a decription of each folder, as applicable.

### Code

Code folder contains scripts for processing raw data into cleaned data, outside derived code, and user derived code. A folder OldR is used to store outdated code. Typically organize .Rmd in modules; Import and Process saving .Rds out of each step.

Code folder contains 15 .Rmd: Assess_MultiCultiData.Rmd, Import_JazEmData.Rmd, Import_MetaData.Rmd, Import_MultiCultiData.Rmd, Import_OlisData.Rmd, Import_SolisenseData.Rmd, Process_GrowthCurveData.Rmd, Process_GrowthRateData.Rmd, Process_GrowthRateSolisenseData.Rmd, Process_GrowthSymmetryData.Rmd, Process_MultiCultiData.Rmd, Process_OlisSpectraJazEmData.Rmd, Process_PigmentsData.Rmd, Process_SolisensePigmentsData.Rmd, and SynechococcusPhotoperiod_MS.Rmd.

- Assess_MultiCultiData.Rmd processes and combines all .Rds from Data/ProcessedData/ProcessedMCData folder.
This .Rmd generates PICO_NestedFitsData.Rds and PICO_LongerFitsData.Rds (both stored in Data/CleanData/CleanedMCData folder). 

- Import_JazEmData.Rmd imports Jaz radiospectrometer files from Data/RawData/JazEmData.zip folder and stored in Data/ImportedData/ImportedJazEmData folder as: Baltic_Photoperiod_Imported_JazEmData.Rds

- Import_MetaData.Rmd imports culture Meta Data catalog from a google sheet and stored in Data folder as: CultureCatalog.Rds

- Import_MultiCultiData.Rmd imports Multi-Cultivator MC247 and MC257 files from Data/RawData/MultiCultiData.zip folder and stored in Data/ImportedData/ImportedMCData folder as: 
20211214_PICO_MC247_RUN39_TargetDataMetaFilter.Rds, 
20211223_PICO_MC257_RUN40_TargetDataMetaFilter.Rds, 
20211229_PICO_MC247_RUN43_TargetDataMetaFilter.Rds, 
20220107_PICO_MC257_RUN44_TargetDataMetaFilter.Rds, 
20220113_PICO_MC247_RUN45_TargetDataMetaFilter.Rds, 
20220122_PICO_MC257_RUN46_TargetDataMetaFilter.Rds, 
20220405_PICO_MC247_RUN60_TargetDataMetaFilter.Rds, 
20220410_PICO_MC257_RUN62_TargetDataMetaFilter.Rds, 
20220420_PICO_MC257_RUN65_TargetDataMetaFilter.Rds, 
20220507_PICO_MC257_RUN71_TargetDataMetaFilter.Rds, 
20220607_PICO_MC257_RUN74_TargetDataMetaFilter.Rds, 
20220615_PICO_MC257_RUN77_TargetDataMetaFilter.Rds, and
20230816_PICO_MC257_RUN121_TargetDataMetaFilter.Rds

- Import_OlisData.Rmd imports OLIS CLARiTY spectrophotometer files from Data/RawData/OlisData.zip folder and stored in Data/ImportedData/ImportedOlisData folder as: Baltic_Photoperiod_Imported_OlisData.Rds

- Import_SolisenseData.Rmd imports and tidies fit data from the Solisense FRR kinetic fluorometer software from Data/RawData/SolisenseNSData.zip and SolisenseOSData.zip folders and stored them in Data/ImportedData/ImportedSolisenseData folder as: Baltic_Photoperiod_Imported_SolisenseDarkafterLight.Rds and Baltic_Photoperiod_Imported_SolisenseLight.Rds 

Baltic_Photoperiod_Imported_SolisenseDarkafterLight.Rds contained data taken from corresponding light. Baltic_Photoperiod_Imported_SolisenseLight.Rda contained data taken from 1s of darkness after corresponding light. Data from old software (OS) and new software (NS) are merged here. This .Rmd does not perform the underlying fits of the induction/relaxation profiles from FRRf protocols.

- Process_GrowthCurveData.Rmd separately processes and combines all .Rds from Data/ImportedData/ImportedMCData folder. This .Rmd generates Baltic_Photoperiod_Processed_GrowthCurve.Rds (stored in Data/ProcessedData/ProcessedGrowthCurveData folder) and GrowthCurve_SupPlot.png (stored in Output/Plots folder).

- Process_GrowthRateData.Rmd processes and combines PICO_NestedFitsData.Rds from Data/CleanData/CleanedMCData folder and Baltic_Photoperiod_Processed_OlisSpectraTidy.Rds from Data/ProcessedData/ProcessedOlisJazData. This .Rmd generates Baltic_Photoperiod_Processed_GrowthRate.Rds (stored in Data/ProcessedData/ProcessesGrowthRateData folder) and GrowthRate_Plot.png (stored in Output/Plots folder).

- Process_GrowthRateSolisenseData.Rmd processes and combines Baltic_Photoperiod_Processed_GrowthRate.Rds from  Data/ProcessedData/ProcessedGrowthRateData folder and Baltic_Photoperiod_Processed_SolisensePigmentsExp.Rds from Data/ProcessedData/ProcessedSolisenseData folder. This .Rmd generates xxx.Rds (stored in xxxa folder) and xxx_Plot.png (stored in Output/Plots folder).

- Process_GrowthSymmetryData.Rmd processes Growth Symmetry (GS) catalog from a google sheet. This .Rmd generates Baltic_Photoperiod_Processed_GrowthSymmetryData.Rds (stored in Data/ProcessedData/ProcessedGrowthSymmetryData folder) and four plots: AccLen_Plot_Plot.png, AccLen_SupPlot_Plot.png, GS_Plot.png, and TDG_SupPlot.png (stored in Output/Plots folder).

- Process_MultiCultiData.Rmd processes and combines all .Rds from Data/ImportedData/ImportedMCData folder and creates: 
20211214_PICO_MC247_RUN39_ProcessDataNestGrowth.Rds, 
20211223_PICO_MC257_RUN40_ProcessDataNestGrowth.Rds, 
20211229_PICO_MC247_RUN43_ProcessDataNestGrowth.Rds, 
20220107_PICO_MC257_RUN44_ProcessDataNestGrowth.Rds, 
20220113_PICO_MC247_RUN45_ProcessDataNestGrowth.Rds, 
20220122_PICO_MC257_RUN46_ProcessDataNestGrowth.Rds, 
20220405_PICO_MC247_RUN60_ProcessDataNestGrowth.Rds, 
20220410_PICO_MC257_RUN62_ProcessDataNestGrowth.Rds, 
20220420_PICO_MC257_RUN65_ProcessDataNestGrowth.Rds, 
20220507_PICO_MC257_RUN71_ProcessDataNestGrowth.Rds, 
20220607_PICO_MC257_RUN74_ProcessDataNestGrowth.Rds, 
20220615_PICO_MC257_RUN77_ProcessDataNestGrowth.Rds, and
20230816_PICO_MC257_RUN121_ProcessDataNestGrowth.Rds

This .Rmd implements logistic growth curve fits to MultiCulti growth trajectories.

- Process_OlisSpectraJazEmData.Rmd processes and combines Baltic_Photoperiod_Imported_JazEmData.Rds from Data/ImportedData/ImportedJazEmData folder and Baltic_Photoperiod_Imported_OlisData.Rds from Data/ImportedData/ImportedOlisData folder. This .Rmd generates Baltic_Photoperiod_Processed_OlisSpectraAll.Rds and Baltic_Photoperiod_Processed_OlisSpectraTidy.Rds (both stored in Data/ProcessedData/ProcessedOlisJazData folder) and OlisSpectra_Plot.png (stored in Output/Plots folder).

- Process_PigmentsData.Rmd processes and combines pigment catalog from a google sheet and Baltic_Photoperiod_Processed_OlisSpectraTidy.Rds from Data/ProcessedData/ProcessedOlisJazData folder. This .Rmd generates Baltic_Photoperiod_Processed_PigmentAll.Rds and Baltic_Photoperiod_Processed_PigmentsExp.Rds (both stored in Data/ProcessedData/ProcessedPigmentsData folder) and two plots: Pigments_SupPlot.png and  PigRatioPUR_Plot.png (stored in Output/Plots folder).

- Process_SolisensePigmentsData.Rmd processes and combines Baltic_Photoperiod_Imported_SolisenseDarkafterLight.Rds and Baltic_Photoperiod_Imported_SolisenseLight.Rds from Data/ImportedData/ImportedSolisenseData folder. This .Rmd generates Baltic_Photoperiod_Processed_SolisensePigmentsExp.Rds (stored in Data/ProcessedData/ProcessedSolisenseData folder) and three plots: Sigma_SupPlot.png, SigmavsPigments590_Plot, SigmavsPigments445_SupPlot.png (stored in Output/Plots folder).

- SynechococcusPhotoperiod_MS.Rmd contains the latest version of the manuscript.

### Data/CleanData

Clean data in formats for long-term storage. CleanData folder contains modified data with the appropriate column/row headers and data structure.

CleanData folder contains 1 folder: CleanedMCData.

- Folder CleanedMCData contains PICO_LongerFitsData.Rds and PICO_NestedFitsData.Rds generated from Assess_MultiCultiData.Rmd (stored in Code folder).

### Data/ImportedData

Imported data in formats for long-term storage.

ImportedData folder contains 5 folders: ImportedJazEmData, ImportedMCData, ImportedOlisData, ImportedPigmentsData, ImportedSolisenseData.

- Folder ImportedJazEmData contains Baltic_Photoperiod_Imported_JazEmData.Rds generated from Import_JazEmData.Rmd (stored in Code folder).

- Folder ImportedMCData contains 
20211214_PICO_MC247_RUN39_TargetDataMetaFilter.Rds, 
20211223_PICO_MC257_RUN40_TargetDataMetaFilter.Rds, 
20211229_PICO_MC247_RUN43_TargetDataMetaFilter.Rds, 
20220107_PICO_MC257_RUN44_TargetDataMetaFilter.Rds, 
20220113_PICO_MC247_RUN45_TargetDataMetaFilter.Rds, 
20220122_PICO_MC257_RUN46_TargetDataMetaFilter.Rds, 
20220405_PICO_MC247_RUN60_TargetDataMetaFilter.Rds, 
20220410_PICO_MC257_RUN62_TargetDataMetaFilter.Rds, 
20220420_PICO_MC257_RUN65_TargetDataMetaFilter.Rds, 
20220507_PICO_MC257_RUN71_TargetDataMetaFilter.Rds, 
20220607_PICO_MC257_RUN74_TargetDataMetaFilter.Rds, 
20220615_PICO_MC257_RUN77_TargetDataMetaFilter.Rds, and
20230816_PICO_MC257_RUN121_TargetDataMetaFilter.Rds generated from Import_MultiCultiData.Rmd (stored in Code folder).

- Folder ImportedOlisData contains Baltic_Photoperiod_Imported_OlisData.Rds generated from Import_OlisData.Rmd  (stored in Code folder).

- xxx Folder ImportedPigmentsData contains Baltic_Photoperiod_Imported_Pigments_OtherRepository.Rds generated from different repository (dropbox) for now. I will fix this soon.

- Folder ImportedSolisenseData contains Baltic_Photoperiod_Imported_SolisenseDarkafterLight.Rds and Baltic_Photoperiod_Imported_SolisenseLight.Rds generated from Import_SolisenseData.Rmd (stored in Code folder).

### Data/ProcessedData

Processed data in formats for long-term storage.

ProcessedData folder contains 7 folders: ProcessedGrowthCurveData, ProcessedGrowthRateData, ProcessedGrowthSymmetryData, ProcessedMCData, ProcessedOlisJazData, ProcessedPigmentsData, ProcessedSolisenseData.

- Folder ProcessedGrowthCurveData contains Baltic_Photoperiod_Processed_GrowthCurve.Rds generated from Process_GrowthCurveData.Rmd (stored in Code folder).

- Folder ProcessedGrowthRateData contains Baltic_Photoperiod_Processed_GrowthRate.Rds generated from Process_GrowthRateData.Rmd (stored in Code folder).

- Folder ProcessedGrowthSymmetryData contains Baltic_Photoperiod_Processed_GrowthSymmetryData.Rds generated from Process_GrowthSymmetryData.Rmd (stored in Code folder).

- Folder ProcessedMCData contains 20211214_PICO_MC247_RUN39_ProcessDataNestGrowth.Rds, 
20211223_PICO_MC257_RUN40_ProcessDataNestGrowth.Rds, 
20211229_PICO_MC247_RUN43_ProcessDataNestGrowth.Rds, 
20220107_PICO_MC257_RUN44_ProcessDataNestGrowth.Rds, 
20220113_PICO_MC247_RUN45_ProcessDataNestGrowth.Rds, 
20220122_PICO_MC257_RUN46_ProcessDataNestGrowth.Rds, 
20220405_PICO_MC247_RUN60_ProcessDataNestGrowth.Rds, 
20220410_PICO_MC257_RUN62_ProcessDataNestGrowth.Rds, 
20220420_PICO_MC257_RUN65_ProcessDataNestGrowth.Rds, 
20220507_PICO_MC257_RUN71_ProcessDataNestGrowth.Rds, 
20220607_PICO_MC257_RUN74_ProcessDataNestGrowth.Rds, 
20220615_PICO_MC257_RUN77_ProcessDataNestGrowth.Rds, and
20230816_PICO_MC257_RUN121_ProcessDataNestGrowth.Rds generated from Process_MultiCultiData.Rmd (stored in Code folder).

- Folder ProcessedOlisJazData contains Baltic_Photoperiod_Processed_OlisSpectraAll.Rds and Baltic_Photoperiod_Processed_OlisSpectraTidy.Rds generated from Process_OlisSpectraJazEmData.Rmd (stored in Code folder).

- Folder ProcessedPigmentsData contains Baltic_Photoperiod_Processed_PigmentAll.Rds and Baltic_Photoperiod_Processed_PigmentsExp.Rds generated from Process_PigmentsData.Rmd (stored in Code folder).

- Folder ProcessedSolisenseData contains Baltic_Photoperiod_Processed_SolisensePigmentsExp.Rds generated from Process_SolisensePigmentsData.Rmd (stored in Code folder).

### Data/RawData

Raw data files in various formats contains original files generated by analytical equipment, received from a data provider or outside contractor.
Subfolders contain files from a single instrument.

RawData folder contains 5 zipped folders: JazEmData.zip, MultiCultiData.zip, OlisData.zip, SolisenseNSData.zip, and SolisenseOSData.zip.

- Folder JazEmData.zip contains files generated from Jaz radiospectrometer.
- Folder MultiCultiData.zip contains files generated from Multi-Cultivator MC247 and MC257.
- Folder OlisData.zip contains files generated from OLIS CLARiTY spectrophotometer.
- Folder SolisenseNSData.zip contains files generated from Solisense FRR kinetic fluorometer new software (NS).
- Folder SolisenseOSData.zip contains files generated from Solisense FRR kinetic fluorometer old software (OS).

### MetaDataCatalog

URL for MetaDataCatalog:
https://docs.google.com/spreadsheets/d/1ZXpwR7Gfto-uRzVdXzMpQF4frbrvMLH_IyLqonFZRSw/edit#gid=0

### Docs

Docs folder contains 3 fies: BalticPhotoperiod.bib, INSTRUCTIONS.md, and README.md.

### Output

Output from knit .Rmd, Figures and tables produced from analysis.

The Output folder contains two folders: Plots and PlotsRDS. 
- Folder Plots contains all plots that will be used in the final manuscript.
- Folder PlotsRDS contains all .Rds needed to generate these plots.

### Data Dictionary

URL for Data Dictionary:
https://docs.google.com/spreadsheets/d/1hduAE5hZWdkxe7IJNJswQthYpaWIuwpBJBoXRqgDZss/edit#gid=0
