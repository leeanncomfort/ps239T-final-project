# ps239T-final-project

## Short Description
___
The purpose of this project is to examine whether there are differences in the ways medical staff at high and low performing organizations speak about their working environment. A total of 52 interview transcripts were included; the langugage analysis was conducted using the 2015 Linguistic Inquiry and Word Count (LIWC 2015) software, which provides 82 measures in dimensions such as:  

* Functional words (e.g., "I" statements and "We" statements)  
* Affect  (e.g., use of words with positive connotations)  
* Social Words (e.g., focus on family and friends)  
* Core Drives (e.g., achievement-driven)  
* Time Orientation (e.g., past focus)  


The project first processes interview transcripts, from `.docx` documents to `.csv` format, using the `textreadr` package. This package saves as individual observations each question (if the interviewer is speaking) or response (in the respondent is speaking). This response-level of analysis allowed LIWC to score each response separately for each of the 82 measures.  

The next step of the project creates a master de-identified dataset from the 52 LIWC results files. Using this master file (`liwc_one_2018-04-28.csv`), the final portion of the project conducts several high-level, exploratory data visualizations. Seeing no trends in the posted visualizations and intraclass correlation coefficients averaging below 0.025 (where values below 0.50 indicate poor reliability), no further statistical analyses were conducted (or are planned) for this unit of analysis. Future work may include reconducting the LIWC analyses at the sentence-level, though these analysis are not a high priority given the lack of promising trends in these early analyses.  


## Dependencies
___
Linguistic	Inquiry	and	Word	 Count:	LIWC2015 <sup>1</sup>  
R <sup>2</sup>, version 3.4.3 (accessed via RStudio, Version 1.1.442 for Windows and Version 1.1.419 for Mac) with the following packages:  

  * digest <sup>3</sup>  
  * anonymizer<sup>4</sup>  
  * purrr <sup>5</sup>  
  * textreadr <sup>6</sup>    
  * ggplot2 <sup>7</sup>  
  * reshape <sup>8</sup>  
  * tidyr <sup>9</sup>   
  * dplyr <sup>10</sup>   
  * ICC <sup>11</sup>  





## Files
___
### Data
**liwc_one_2018-04-28.csv**  
De-identified results of the LIWC analysis for all wave 1 interviews, where each observation is a question/response that was analyzed independently. Created from the `01_Create_LIWC_data_Redacted` file. 

### Code
**00_Prepare Transcripts.Rmd**  
Transforms Word document files into csv files, where each observation is an entire question or response.  Because the underlying data on which the code depends cannot be made available to individuals not listed on the IRB protocol (ID 2015-04-75512), an HTML file compiled using `knitr` is also presented. Note that the final line of the code, which lists the filenames with identifiable information, is commented-out. 

**01_Create_LIWC_data_Redacted.html**  
After the transcripts are analyzed using the LIWC2015 software, this code is used to combine all individual result files into one master dataset. The code also uses an anonymizing function to replace the interviewee names with random alphanumeric codes (individuals keep the same code throughout the document). Because the code contains identifiable information, an HTML file compiled using `knitr` is presented in lieu of the `rmd` file. The identifiying information has been redacted from the posted HTML file. 

**02_Exploratory_LIWC_Analysis.Rmd**  
This file conducts the exploratory data visualizations. The first step compares the LIWC scores by: the 2 high/low performing organizations, the 16 practice sites, staff roles (doctor, nurse, and medical assistant), and interviewer/interviewee status. The second step calculates and summarizes the intraclass correlation coefficient for measures across each interviewees' responses (examining the extent to which an individual is consistenct in her/his/their language use across each of their responses). 


### Results
The four "summary" variables are presented separately because they tend to alter the shared scale when included with the other variables. The result files are organized by comparison group and variables. 

| *Comparison* |  *Variables*  | *Filename*   |
|---|---|---|
| High or Low Performing Organization |   Summary   | HL_Summary.png        |
|                           | Non-Summary | HL_NonSummaryVars.png |
| Practice Sites (16) |   Summary   | Site_Summary.png      |
|                           | Non-Summary | Site_NonSummary.png    |
| Interviewers, Respondents |   Summary   | IR_Summary.png        |
|                           | Non-Summary | IR_NonSummary.png     |
| ICC Scores (range)    | All, Individuals Variables |ICC_ind.png     |
|    | All, Site |ICC_site.png     |



## More Information
___
Creator: Leeann Comfort, leeann.comfort@berkeley.edu  
Course Instructor (Spring 2018): Rachel Bernhard, rbernhard@berkeley.edu

  
### Citations  

  <sup>1</sup> J.W. Pennebaker,	R.J.Booth, R.L.	Boyd,	& M.E. Francis (2015). Linguistic	Inquiry	and	Word	 Count:	LIWC2015.		Austin,	TX:	Pennebaker	Conglomerates	(www.LIWC.net).

  <sup>2</sup> R Core Team (2017). R: A language and environment for statistical computing. R Foundation for Statistical Computing, Vienna, Austria. URL
  https://www.R-project.org/.


  <sup>3</sup> D. Eddelbuettel (2018). digest: Create Compact Hash Digests of R Objects. R package version 0.6.15. https://CRAN.R-project.org/package=digest

  <sup>4</sup> P. Hendricks (2015). anonymizer: Anonymize Data Containing Personally Identifiable Information. R package version 0.2.0.
  https://CRAN.R-project.org/package=anonymizer
  
  <sup>5</sup> L. Henry and H. Wickham (2017). purrr: Functional Programming Tools. R package version 0.2.4. https://CRAN.R-project.org/package=purrr]


  <sup>6</sup> T. W. Rinker (2017). textreadr: Read Text Documents into R version 0.7.0. Buffalo, New York. http://github.com/trinker/textreadr]

  <sup>7</sup> H. Wickham. ggplot2: Elegant Graphics for Data Analysis. Springer-Verlag New York, 2009.

  <sup>8</sup> H. Wickham. Reshaping data with the reshape package. Journal of Statistical Software, 21(12), 2007.

  <sup>9</sup> H. Wickham and L. Henry (2018). tidyr: Easily Tidy Data with 'spread()' and 'gather()' Functions. R package version 0.8.0.
  https://CRAN.R-project.org/package=tidyr
 
  <sup>10</sup> H. Wickham, R. Francois, L. Henry and K. Müller (2017). dplyr: A Grammar of Data Manipulation. R package version 0.7.4.
  https://CRAN.R-project.org/package=dplyr]
  
  <sup>11</sup> M.E. Wolak (2016) ICC: Facilitating Estimation of the Intraclass Correlation Coefficient. R package version 2.3.0.
 
