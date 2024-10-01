# **GWAS Results**  

This app is used to view your team's job statuses and results.  

## **Table of Submitted GWAS Workflows**

The landing page displays a table of submitted jobs which includes the Run ID of team analyses, the Workflow name, Date/Time submitted, and Date/Time Finished. The table may be sorted by any column by clicking on the up or down arrows next to the column name. The "Manage columns" button in the upper right corner can be used to toggle the display of any column.

Three additional columns are displayed by default: Job status, View Details, and Actions.  

The **View Details** columns lists additional information about your submitted job. The Input button links to your GWAS job configuration options and the execution button presents information about the execution of your GWAS job including messages from log files.  

The **Job status** column provides information about the execution status of your job.  The displayed values are:

* **Pending** - Your analysis was placed in the queue to run. Depending on the length of the queue, your analysis could take from several minutes to several hours to start.  
* **In Progress** - Your analysis has started and is running. Depending on your selection of cohort and variables, it could take from a half an hour to three hours to finish.  
* **Failed** - Your analysis returned an error and could not run to completion. Please see **[Troubleshooting GWAS Errors](#troubleshooting-gwas-errors)** below.  
* **Completed** - Your analysis successfully completed, and you may download the results of the GWAS analysis from this menu.  

The **Actions** column....

## **GWAS Results**

 Once your analysis is completed, you may review the output from your submission by clicking on the "Results" button in the details column. The results landing page includes an interactive Manhattan plot, viewable QQ plot, and a searchable table of the Top Loci.  The Manhattan plot may be downloaded separately as a png format fil, and the Top Loci table as a tsv file.  Clicking on the *Download All Results* button at the top of the results page will prompt the creation and download of your workflow results to your computer. Depending on your cohort and variables selection, the file size can vary from 700MB up to 1.3GB. The workflow results file contains the following:

* Manhattan plot (.png)  
* QQ plot (.png)  
* 100 top hits (.csv.gz)  
* per-chromosome GWAS summary statistics (folder of .csv.gz’s)  
* all hits below p-value 5e-8 (.csv.gz)  
* your study’s attrition tables (folder of .csv’s)  
* a metadata file containing all of your selections (gwas_metadata.yaml)  

## **Troubleshooting GWAS Errors**  

In the Results Viewer App, we are beginning to add meaningful error messages. The messages will appear in the execution logs. See this list of selected errors and how to interpret and resolve them:  

### **Failed run-null-model: The error occurred due to small cohort size or unbalanced cohort sizes. Please ensure that the cohorts selected for your analysis are sufficiently large and balanced.**

The selected cohort size did not produce enough statistical power. If the user ran a dichotomous workflow, they should check that both the case and control cohort sizes are large enough, and are not vastly different in size (for example, by two orders of magnitude or more). This can be checked through the attrition table in the GWAS App prior to submission. The cohort size will show in the column where the chosen HARE is presented. A user may also see the choice they made in the GWAS Results by clicking on “Input”.

### **Failed run-single-assoc: The error occurred due to unbalanced cohort sizes. Please ensure that the sizes of the cohorts are as balanced as possible.**

The selected cohort size did not produce enough statistical power. If the user ran a dichotomous workflow, they should check that both the case and control cohort sizes are large enough, and are not vastly different in size (for example, by two orders of magnitude or more). This can be checked through the attrition table in the GWAS App prior to submission. The cohort size will show in the column where the chosen HARE is presented. A user may also see the choice they made in the GWAS Results by clicking on “Input”.

### **Failed run-single-assoc: The error was caused by extreme outliers in the outcome or the covariates. Please try using different outcome/covariates variables.**

This error indicates that there are significant outliers in the outcome or the covariates, so the analysis could not be run. Please try a different combination of outcome and covariate variables. Before submission, users may check the distribution of their continuous variables to see outliers on [Step 2](gwas.md#step-2-select-outcome-phenotype) and [Step 3](gwas.md#step-3-select-covariate-phenotype) of the GWAS app.

### **Failed generate-attrition-csv: A timeout occurred while fetching the attrition table information. Please retry running your workflow.**

An indexd record creation error indicates that something, likely temporary, interfered with the creation of the indexd record. If you wish to re-run your job, you can do so by selecting “retry” from the Actions Menu.

Please read our [Data Update Disclaimer](#data-update-disclaimer) to understand limitations regarding retry.  

### **Failed create-indexd-record: An HTTP error occurred while creating an indexd record. Please retry running your workflow.**

A timeout error indicates that an internal service was temporarily not available while fetching the information presented to the user on the UI. If you wish to re-run your job, you can do so by selecting “retry” from the Actions Menu.

Please read our [Data Update Disclaimer](#data-update-disclaimer) to understand limitations regarding retry.  

### **Step failed with an uncategorized error**

Workflows can fail for many different reasons, and some of them are transient. Please reach out to [vadc@lists.uchicago.edu](mailto:vadc@lists.uchicago.edu) with any further questions. In your message, please provide us with the serial name of your workflow and the step in which your GWAS failed (described in your error message). A response should be expected within 2 business days.  

## **Data Update Disclaimer**

Please note that we are constantly improving the GWAS pipeline. The retry action will re-run your analysis based on the most recent data available in the database and the most recent GWAS pipeline implemented. These may differ from the analysis you ran initially, and these differences might affect the outcome. For these reasons, the retry action is only applicable to failed workflows. If you have any questions, please feel free to contact us via email [vadc@lists.uchicago.edu](mailto:vadc@lists.uchicago.edu).
