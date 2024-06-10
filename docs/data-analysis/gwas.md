# **Genome-wide association studies (GWAS) in Gen3**

Genome-wide association studies (GWAS) help scientists identify genes associated with a particular disease (or another trait). This method studies the entire set of DNA (the genome) of a large group of people, searching for small variations called single nucleotide polymorphisms or SNPs (pronounced “snips”).

Use the GWAS App to perform GWAS on MVP data using the University of Washington GENESIS pipeline. For more information about the GENESIS pipeline, please refer to the publication ["Genetic association testing using the GENESIS R/Bioconductor package"](https://doi.org/10.1093/bioinformatics/btz567).

The GWAS App includes several steps. To navigate between the steps, click the Next or Previous box in the lower corners of the screen.

Each step displays the Attrition table at the top of the page. The Attrition table contains information about the total population size and sample size by ancestry for your selected cohorts and variables.

For more information about the web functionality of each step, please refer to the button “New to GWAS? Get started here”. This tool will offer highlighted explanations on different parts of the page.

## **GWAS Steps**

>**Tip**: On each step of the workflow, there is a tutorial button called `"New to GWAS? Get started here"`; please click the button to navigate through the tutorial.  

### **Step 1: Select Study Population**

In this step, you will determine the study population. To begin, select the cohort that you would like to define your study population with. By default, the first cohort displayed is the "CATCH ALL," which is available to all projects. Subsequent cohorts are those created for your specific project. You may only see cohorts that you have access to. You may only select one cohort. The size of the cohort population is indicated on the right-hand side of the table. To browse the table, please scroll down to the bottom. To search for a cohort by name, you may use the search box.

Once a cohort has been chosen, it will populate the attrition table above.

You may also see the button “Add a new cohort”. This button will open a new tab in your browser outside of the Gen3 GWAS App and send you to the OHDSI Atlas App, where you may create a new cohort.

### **Step 2: Select Outcome Phenotype**

In this step, you will determine your outcome phenotype.

There are two options available: Continuous Outcome Phenotype and Dichotomous Outcome Phenotype.

**Continuous Outcome**

Here, you may choose your continuous phenotype. GWAS App provides over 500 variables for your selection (for example, height, weight, blood pressure, white blood cell, and other clinical observations). Please select the outcome phenotype you wish to use in your model. All data are harmonized from different projects through the collaborative development of a data dictionary. To browse the table, please scroll down to the bottom. To search the table, please enter free text in the search box to search by phenotype name. In the plot near the table, you can learn more about the selected outcome distribution in the study population. After you select your outcome, click “Submit” to apply it for your model. After clicking "Submit", you will see the selection in your attrition table.

**Dichotomous Outcome**

Here, you may choose your dichotomous outcome phenotype. You can define your outcome by intersecting your study population with two other cohorts. Please enter the name for your outcome variable in the field “Phenotype name”. You can select your control (or No, 0) cohort in the field “Get Value 0”, and your case cohort (or Yes, 1) in the field “Get Value 1”. The Euler diagram on the right-hand side of the page shows the overlap between your chosen cohorts and study population, with numbers indicating the size of the overlap. After you define your outcome phenotype, click “Submit” to apply it to your model. It will then populate the attrition table and take you to the next step.

### **Step 3: Select Covariate Phenotype**

This step is optional. In this step, you can add the harmonized continuous covariates or dichotomous covariates by clicking on the corresponding button.

**Add Continuous Covariate**

GWAS App provides over 500 variables for your selection (for example, height, weight, blood pressure, white blood cell, and other clinical observations). Please select all covariates you wish to use in your model. You may choose as many covariates as you wish in this step. To browse the table, please scroll down to the bottom. To search the table, please enter free text in the search box to search by the covariate name. You can learn more about the selected covariate distribution in the study population in the plot near the table. After you select your covariate, click “Add” to apply it to your model. The covariate will then appear on the right-hand side of the screen and populate the attrition table. You can delete previously chosen covariates by clicking on the Delete icon.

**Add Dichotomous Covariate**

You may add custom dichotomous covariates by selecting two cohorts. Please enter the name for your covariate variable in the field “Covariate name”. You can select your control (or No, 0) cohort in the field “Get Value 0” and your case cohort (or Yes, 1) in the field “Get Value 1”. The Euler diagram on the right-hand side of the page shows the overlap between your chosen cohorts and study population with numbers indicating the size of the overlap. After you define your covariate, click “Add” to apply it to your model. The covariate will then appear on the right-hand side of the screen and populate the attrition table. You can delete previously created covariates by clicking on the Delete icon.

### **Step 4: Configure GWAS workflow parameters**

In this step, you will determine workflow parameters. Please adjust the number of population principal components (PCs) to control for population structure, minor allele frequency cutoff, and imputation score cutoff. Please also choose at least one one ancestry population on which you would like to perform your study.

**Number of PCs** - Population Principal components (PCs) refer to linear combinations of genome-wide genotyping data to control for population structure/stratification (select up to 10 PCs).

**Harmonized Ancestry and Race/Ethnicity (HARE) dropdown menu** - Please choose the ancestry population on which you would like to perform your study. The numbers appearing in the dropdown represent the population size of your study, considering all of your previous selections. You may not proceed with the analysis without a selection.

**MAF Cutoff - Minor allele frequency (MAF)** is the frequency at which the second most common allele occurs in a given population and can be used to filter out rare markers (scale of 0-0.5).

**Imputation Score Cutoff** - This value reflects the quality of imputed SNPs and can be used to remove low-quality imputed markers (scale of 0-1).
Once you have selected your values please press Next.

### **Submission Modal and Additional Options**

Once step 4 is concluded, you may review your details in a modal. This will present to you the configurable selections made in every step of the GWAS setup.

- **Configurable values** - May be changed in step 4.

- **Covariates** - Please review the chosen covariates. To remove unwanted covariates, or change them, please go back (at the bottom of the page) to step 3.

- **Outcome Phenotype** - Here you see the outcome phenotype chosen in step 2. To update the selection, please go back (at the bottom of the page) to step 2.

- **Cohort** - This represents the study population you selected. To change your selection, please go back to step 1.

Once you have reviewed your selections, you must give a name to your analysis. You can then start the GWAS workflow by pressing ‘Submit’.

Once the job is submitted, a success message will then appear on the screen with the given job name and GWAS job id. There are 3 different options available to you at this point:

1. **See status** - This option will send you to a different page where you may review the status of your job.  
2. **Submit new workflow** - This option will send you to the beginning of the GWAS App where you may submit a different GWAS for analysis.  
3. **Submit similar** (stay here) - This option will keep you at this page, where you are able to make some changes to the GWAS parameters you already used and submit a similar job.  

### **Check Submission Status and Review Results**

Once your GWAS analysis is submitted, you can check the Submission Status and Review the Results in the “GWAS Results” App.
