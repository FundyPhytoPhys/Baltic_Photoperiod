# Code

Information about documents added to this folder.


- Import_JazEmData.Rmd imports Jaz radiospectrometer files from Data/RawData/JazEmData.zip folder and stored in Data/ImportedData/ImportedJazEmData folder as: 
Baltic_Photoperiod_Imported_JazEmData.Rds

- Import_MetaData.Rmd imports culture Meta Data catalog from a google sheet and stored in Data folder as:  
CultureCatalog.Rds

- Import_MultiCultiData.Rmd imports MultiCultivator files from Data/RawData/MultiCultiData.zip folder and stored in Data/ImportedData/ImportedMCData folder as: 
20211214_PICO_MC247_RUN39_TargetDataMetaFilter.Rds
20211223_PICO_MC257_RUN40_TargetDataMetaFilter.Rds
20211229_PICO_MC247_RUN43_TargetDataMetaFilter.Rds
20220107_PICO_MC257_RUN44_TargetDataMetaFilter.Rds
20220113_PICO_MC247_RUN45_TargetDataMetaFilter.Rds
20220122_PICO_MC257_RUN46_TargetDataMetaFilter.Rds
20220405_PICO_MC247_RUN60_TargetDataMetaFilter.Rds
20220410_PICO_MC257_RUN62_TargetDataMetaFilter.Rds
20220420_PICO_MC257_RUN65_TargetDataMetaFilter.Rds
20220507_PICO_MC257_RUN71_TargetDataMetaFilter.Rds
20220607_PICO_MC257_RUN74_TargetDataMetaFilter.Rds
20220615_PICO_MC257_RUN77_TargetDataMetaFilter.Rds
20230816_PICO_MC257_RUN121_TargetDataMetaFilter.Rds

- Import_OlisData.Rmd imports OLIS OLIS CLARiTY spectrophotometer files from Data/RawData/OlisData.zip folder and stored in Data/ImportedData/ImportedOlisData folder as: 
Baltic_Photoperiod_Imported_OlisData.Rds

- Import_SolisenseData.Rmd imports and tidies fit data from the Solisense FRR kinetic fluorometer software from Data/RawData/SolisenseNSData.zip and SolisenseOSData.zip folders and stored them in Data/ImportedData/ImportedSolisenseData folder as: 
Baltic_Photoperiod_Imported_SolisenseDarkafterLight.Rds 
Baltic_Photoperiod_Imported_SolisenseLight.Rda 

Baltic_Photoperiod_Imported_SolisenseDarkafterLight.Rds contained data taken from corresponding light. Baltic_Photoperiod_Imported_SolisenseLight.Rda contained data taken from 1s of darkness after corresponding light. Data from old software (OS) and new software (NS) are merged here. This .Rmd does not perform the underlying fits of the induction/relaxation profiles from FRRf protocols.


- Process_GrowthCurveData.Rmd separately process and merge all .Rds from Data/ImportedData/ImportedMCData folder. This .Rmd generate Baltic_Photoperiod_Processed_GrowthCurve.Rds (stored in Data/ProcessedData/ProcessedGrowthCurveData folder) and GrowthCurve_SupPlot.png (stored in Output/Plots folder).

- Process_GrowthRateData.Rmd process and merge PICO_NestedFitsData.Rds from Data/CleanData/CleanedMCData folder and Baltic_Photoperiod_Processed_OlisSpectraTidy.Rds from Data/ProcessedData/ProcessedOlisJazData. This .Rmd generate Baltic_Photoperiod_Processed_GrowthRate.Rds (stored in Data/ProcessedData/ProcessesGrowthRateData folder) and GrowthRate_Plot.png (stored in Output/Plots folder).

- Process_GrowthRateSolisenseData.Rmd process and merge Baltic_Photoperiod_Processed_GrowthRate.Rds from  Data/ProcessedData/ProcessedGrowthRateData folder and Baltic_Photoperiod_Processed_SolisensePigmentsExp.Rds from Data/ProcessedData/ProcessedSolisenseData folder. This .Rmd generate xxx.Rds (stored in xxxa folder) and xxx_Plot.png (stored in Output/Plots folder).


