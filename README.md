CAFE MOCHA (Clinical Association of Functionally Established MOlecular CHAnges)


Neeraja M Krishnan, Mohanraj I , Janani Hariharan and Binay Panda

Citation: Krishnan NM, Mohanraj I and Panda B*:  CAFE MOCHA: An Integrated Platform for Discovering Clinically Relevant Molecular Changes in Cancer, An Example of Distant Metastasis and Loco-Regional Recurrence-linked Classifiers in Head and Neck Squamous Cell Carcinoma. Journal of Clinical Oncology – Clinical Cancer Informatics; DOI: 10.1200/CCI.17.00045

Revised: 13 Jan 2017

Version 1.0

Minimum Requirements:

1. Netbeans IDE 8.1 with JAVA platform
2. Linux dependent OS.
3. Tested with Java version &quot;1.8.0_91&quot;
4. Java(TM) SE Runtime Environment (build 1.8.0_91-b14)
5. Java HotSpot(TM) 64-Bit Server VM (build 25.91-b14, mixed mode).
6. R version 3.1.2
7. Bash
8. Shell
9. Perl 5, version 22, subversion 1 (v5.22.1)
10. BEDtools version (v2.18.0)
11. R packages: minfi, wateRmelon, IlluminaHumanMethylation450kmanifest, randomForest, varSelRF, ggplot, pheatmap, gplots, reshape2, ggplot2. The user can install these packages manually.

Install dependencies:

Java for linux : https://java.com/en/download/linux_manual.jsp. 
R- required version >= 3.1.2: https://cran.r-project.org/bin/linux/
BEDtools version 2.18.0: http://bedtools.readthedocs.io/en/latest/content/installation.html

Troubleshooting:

1. Problem: JAVA application fails to run.
Solution: The JAVA application canno run on Open JDK. It requires Oracle SE JDK 1.8

2. Problem: Error in installing openssl
Solution: Install libssl:- sudo apt-get install clibcurl4-openssl- dev pkg-config libssl-dev libsslcommon2-dev

3. Problem: Error in installing RCurl:
Solution: Install libcurl:- sudo aptitude install libcurl4-openssl- dev

4. Problem: Error in installing XML:
Solution: Install libxml:- sudo apt-get install libxml2-dev (or) sudo apt-get install r-cran- xml

5. Problem: biocLite url does not work
Solution: Use http instead of https.

6. Problem: R Script error:- Method read.metharray not found.
Solution: This is due to R (version < 3.3.0.) Click on Run Modified script.

7. Problem: R Script error:- Method read.450k is deprecated.
Solution: This is due to R (version >3.1.0.) In this case stop the process and start it again.

8. Problem: R Script error:- Error in matrix(naValue, nrow = nRunInfoBlocks, ncol = 5): invalid 'nrow' value (too large or NA) Calls: read.450k.exp ... readIDAT_nonenc -> lapply -> FUN -> readField -> matrix
Solution: This is due to a problematic idat file. Remove that idat file from the SampleSheet and run the application. Enter the sentrix id and sentrix position of the last idat file identified in the log in the respective text fields and click on Remove from SampleSheet and click Run alternate script to rectify the error. **You can always produce the unmodified SampleSheet, by running the process again, where you will have an option to produce the unmodified.

9. Problem: Loading the splash screen, but the application does not start
Solution: The application was not started from its home directory.


A stepwise guide for using the DEMO data from TCGA HNSC provided along with the  CAFE MOCHA v1.0 application:

Discovery module:

1. Extract CAFE_MOCHA_Application.tar.gz to a preferred location (creates a folder named CAFE_MOCHA_Application in the preferred location, for e.g. ~/) - 
tar -xvzf CAFE_MOCHA_Application.tar.gz 
2. Extract Demo_HNSC_FIles.tar.gz to a preferred location (creates a folder named Demo_HNSC_FIles in the preferred location, for e.g. ~/)
 tar -xvzf Demo_HNSC_FIles.tar.gz
3. cd ~/ CAFE_MOCHA_Application
4. java -jar CAFE_MOCHA.jar &
5. Select Cancer Type as TCGA head & neck squamous cell carcinoma
6. The default workspace is displayed as ~/CAFE_MOCHA/hnsc
7. Click on Discover
8. Click on Browse button in the CAFE MOCHA - Discover Panel dialog box.
9. An Upload molecular data - Discover dialog box appears with options to upload files
10.  Upload molecular data:
1. Methylation: Select the processed option. Click on Upload and browse to ~/Demo_HNSC_FIles/TCGA_HNSC_hMethyl450-2015-02-24/genomicMatrix
2. Expression: Click on Upload and browse to ~/Demo_HNSC_Files/TCGA_HNSC_exp_HiSeqV2-2015-02-24/genomicMatrix
3. CNV: Click on Upload and browse to ~/Demo_HNSC_Files/TCGA_HNSC_gistic2thd-2015-02-24/genomicMatrix
4. Mutation: Click on Upload and browse to ~/Demo_HNSC_Files/TCGA_HNSC_mutation_broad_gene-2015-02-24/genomicMatrix
11.  Upload Clinical data: 
Click on Upload and browse to ~/Demo_HNSC_Files/clinical_data
12.  Click OK
13.  Click on Link Clinical Relevance.
14.  Under Select Clinical Relevance, select '_RFS_IND' and click on Create Clinical file
15.  From the Select Clinical variable dropdown, select '_RFS_IND' and click on View Sub-Categories
16.  A dialog box View subtypes appears with the numbers of samples conforming to tumor recrrence status (0 indicating not recurrent, 1 indicating recurrent, and neither 0 nor 1, indicating unknown).  The numbers next to these stand for the number of samples conforming to these attributes. Click on OK.
17.  A dialog box CAFE MOCHA - Discover – Clinical_Relevance opens. 
18.  Select no. of groups as 2
19.  Select sub-category 
1. Select N and Click on A>>
2. Select Y and Click on B>>
20.  Click on Save grouping
21.  Click on Continue
22.  A Success pop up appears. Process Complete. Click on OK.
23.  Under Choose an event to associate with clinical variable, select the Expression changes option
24.  From the Select gene sub-regions drop-down, select Island, Promoter, TS200 & TSS1500 (by Ctrl-clicking)
25.  Click on Link Event to the Clinical Variable
26.  A Success pop up appears. Process Complete. Click on OK.
27.  A dialog Box Process Completion Status - CAFE MOCHA appears.
28.  Click on >> corresponding to Expression changes with respect to Group A
29.  Click on >> corresponding to Expression changes with respect to Group B
30.  Click on Link Another Event
31.  Select the Methylation changes option under Choose an event to associate with clinical variable
32.  From the Select gene sub-regions drop-down, select Island, Promoter, TS200 & TSS1500 (by Ctrl-clicking)
33.  Click on Link Event to the Clinical Variable
34.  A Success pop up appears. Process Complete. Click on OK.
35.  A dialog Box Process Completion Status - CAFE MOCHA appears.
36.  Click on >> corresponding to Methylation changes with respect to Group A.
37.  Click on >> corresponding to Methylation changes with respect to Group B.
38.  Click on Link Another Event
39.  Select the CNVs option under Choose an event to associate with clinical variable
40.  Click on Link Event to the Clinical Variable
41.  A Success pop up appears. Process Complete. Click on OK.
42.  A dialog Box Process Completion Status - CAFE MOCHA appears.
43.  Click on >> button corresponding to CNV changes with respect to Group A.
44.  Click on >> button corresponding to CNV changes with respect to Group B.
45.  Click on Link Another Event
46.  Select the Mutations option under Choose an event to associate with clinical variable label. 
47.  Click on Link Event to the Clinical Variable
48.  A Success pop up appears. Process Complete. Click on OK.
49.  A dialog Box Process Completion Status - CAFE MOCHA appears.
50.  Click on >> button coresponding to Mutation changes with respect to Group A.
51.  Click on >> button corresponding to Mutation changes with respect to Group B.
52.  Click on Link Another Event
53.  Select the fCNVs option under Choose an event to associate with clinical variable
54.  From the Select gene sub-regions drop-down, select Island, Promoter, TS200 & TSS1500 (by Ctrl-clicking)
55.  Click on Link Event to the Clinical Variable
56.  A Success pop up appears. Process Complete. Click on OK.
57.  A dialog Box Process Completion Status - CAFE MOCHA appears.
58.  Click on >> corresponding to fCNV changes with respect to Group A.
59.  Click on >> corresponding to fCNV changes with respect to Group B.
60.  Click on Link Another Event button.
61.  Select the fMeth option under Choose an event to associate with clinical variable
62.  From the Select gene sub-regions drop-down, select Island, Promoter, TS200 & TSS1500 (by Ctrl-clicking)
63.  Click on Link Event to the Clinical Variable
64.  A Success pop up appears. Process Complete. Click on OK.
65.  A dialog Box Process Completion Status - CAFE MOCHA appears.
66.  Click on >> corresponding to fMeth changes with respect to Group A.
67.  Click on >> corresponding to fMeth changes with respect to Group B.
68.  Click on Perform Integrated Discovery
69.  Click on Perform Integrated Discovery again, if required in the CAFE MOCHA - Discover Panel dialog box.
70.  A Success pop up appears. Analysis Complete. Choose a group to view the result. Click on OK.
71.  From the Group drop-down, select A and click on View result
72.  Click on the Integrated Signature Map (A) thumbnail . The image is displayed by the default viewer. View and close.
73.  From the Group drop-down, select B and click on View result
74.  Click on the Integrated Signature Map (B) thumbnail . The image is displayed by the default viewer. View and close.
75.  Close the CAFE MOCHA - Discover Panel dialog box.
76.  A Caution! popup appears. Are you sure to close? This will terminate the application. Continue? Click on Yes.

Prediction module:

1. cd ~/ CAFE_MOCHA_Application
2. java -jar CAFE_MOCHA.jar &
3. Select Cancer Type as TCGA head & neck squamous cell carcinoma
4. The default workspace is displayed as ~/CAFE_MOCHA/hnsc
5. Click on Predict
6. Select the _RFS_IND option from the Discovered Clinical variable drop-down
7. Corresponding to, Upload data for incoming patient sample, select the With_Normal option
8. Click on Upload
9. A dialog box CAFE MOCHA - Predict - Upload Incoming Patient Sample Data appears.
10.  Click on Read Instructions to fill in Incoming Patient Sample Data to understand the format for filling in the data
11.  Enter the values as per these instructions
12.  Click on Save Incoming Patient Sample Data
13.  For demonstation sake, execute the following command:
cp -v ~/Demo_HNSC_Files/Predict/With_Normal/clinical  ~/CAFE_MOCHA/hnsc/_RFS_IND/predict/
14.  Click on Predict
15.  Click on the Integrated Signature Map thumbnail. The image is displayed by the default viewer. View and close.
16.  Corresponding to, Upload data for incoming patient sample, select the Without_Normal option
17.  Click on Upload
18.  A dialog box CAFE MOCHA - Predict - Upload Incoming Patient Sample Data appears.
19.  Click on Read Instructions to fill in Incoming Patient Sample Data to understand the format for filling in the data
20.  Enter the values as per these instructions
21.  Click on Save Incoming Patient Sample Data
22.  For demonstation sake, execute the following command:
cp -v ~/Demo_HNSC_Files/Predict/Without_Normal/clinical  ~/CAFE_MOCHA/hnsc/_RFS_IND/predict/
23.  Click on Predict
24.  A Success pop-up opens. Analysis Complete!. Click on OK.
25.  Click on the Integrated Signature Map thumbnail. The image is displayed by the default viewer. View and close.
26.  Close the CAFE MOCHA - Predict Panel dialog box.
27.  A Caution! popup appears. Are you sure to close? This will terminate the application. Continue? Click on Yes.


As an aid to this guide, we have also provided demo videos for executing the discovery and prediction modules.
