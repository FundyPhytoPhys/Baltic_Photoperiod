# Code

Code folder contains 15 .Rmd: Import_JazEmData.Rmd, Import_MetaData.Rmd, Import_MCData.Rmd, Import_OlisData.Rmd, Import_SolisenseData.Rmd, Process_GrowthCurveData.Rmd, Process_GrowthRateData.Rmd, Process_GrowthRateSolisenseData.Rmd, Process_GrowthSymmetryData.Rmd, Process_MCData.Rmd, Process_OlisSpectraJazEmData.Rmd, Process_PigmentsData.Rmd, Process_SolisensePigmentsData.Rmd, Processed_MCData.Rmd, and SynechococcusPhotoperiod_MS.Rmd.

- Import_JazEmData.Rmd imports Jaz radiospectrometer files from Data/RawData/JazEmData.zip folder and stored in Data/ImportedData/ImportedJazEmData folder as: Baltic_Photoperiod_Imported_JazEmData.Rds

- Import_MetaData.Rmd imports culture Meta Data catalog from a google sheet and stored in Data folder as: CultureCatalog.Rds

- Import_MCData.Rmd imports Multi-Cultivator MC247 and MC257 files from Data/RawData/MCData.zip folder and stored in Data/ImportedData/ImportedMCData folder as: 
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

- Process_MCData.Rmd processes and combines all .Rds from Data/ImportedData/ImportedMCData folder and creates: 
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

- Processed_MCData.Rmd processes and combines all .Rds from Data/ProcessedData/ProcessedMCData folder.
This .Rmd generates PICO_NestedFitsData.Rds and PICO_LongerFitsData.Rds (both stored in Data/CleanData/CleanedMCData folder). 

- SynechococcusPhotoperiod_MS.Rmd contains the latest version of the manuscript.
