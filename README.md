# JoBSS Ice Seal Survey Data Management

This repository stores the code associated with managing JoBSS survey data. Code numbered 0+ are intended to be run sequentially as the data are available for processing. Code numbered 99 are stored for longetivity, but are intended to only be run once to address a specific issue or run as needed, depending on the intent of the code.

The Datasheets folder contains the KAMERA-specific datasheets for JoBSS surveys.

The data management processing code is as follows:
* **JoBSS_01_Import2DB.R** - code to import data from the network into the DB
* **JoBSS_01_ProcessFootprints2DB.R** - code to import footprints (from post-processing) into the DB
* **JoBSS_02a_MarkNUCedIRimages.R** - code to mark IR images as NUC (after they have been run through BXH processing)
* **JoBSS_02b_AssignFinalIRNUC.txt** - code to make final NUC call based on the processing approach
* **JoBSS_03_ProcessEffortReconciled.txt** - code to create/update effort_reconciled field based on review of data (to correct any incorrect assignments)
* **JobSS_03b_CreateFlightLines.txt** - code to create flight lines from point records
* **JoBSS_04a_PrepareManualReviewImages.R** - code to generate list of images for manual review
* **JoBSS_05_ProcessDetectionShp2DB.R** - code to import seal detection locations into the DB

Other code in the repository includes:
* Code for copying images collected while surveying on BEAR effort
	* JoBSS_99_CopyBearEffortImages.R
* Code for supporting disturbance analysis:
	* JoBSS_99_DisturbanceAnalysis_ExtractCovariates4Trials.R
	* JoBSS_99_DisturbanceAnalysis_FLIR_ProcessImages.R
* Code for handling NUC images:
	* JoBSS_99_NUCreview_Images.txt
	* JoBSS_99_NUCreview_ProcessResults.R
* SQL code for QA/QC of duplicate animals:
	* JoBSS_99_QA_DuplicateAnimals.txt
* Code for evaluation of roll during survey to help inform limits for inclusion in analysis:
	* JoBSS_99_RollEvaluation.Rmd
