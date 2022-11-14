# Lab 3 - Command Line Options (find)

## Table of Contents
1. [-name](#1-name)
2. [-type](#2-type)
3. [-size](#3-size)

## -name

### Example 1
```
ashishjayamohan@Ashishs-MacBook-Pro docsearch % find ./technical -name chapter-1.txt
./technical/911report/chapter-1.txt
```
In this example, we are able to find a nested file in a sub-folder (`911report/`) called `chapter-1.txt` simply using the `-name` function. This is useful because the find function works recursively and allows us to check all the available sub directories for a particular file name.

### Example 2
```
ashishjayamohan@Ashishs-MacBook-Pro docsearch % find ./technical -name biomed           
./technical/biomed
```
In this example, we were able to find the `biomed/` directory using the `-name` function. This might be useful when trying to find directories that have a partiular name within the searching directory.

### Example 3
```
ashishjayamohan@Ashishs-MacBook-Pro docsearch % find ./technical -name Alcohol_Problems 
./technical/government/Alcohol_Problems
```
In this example, we were able to find the `Alcohol_Problems/` directory that is nested within the `government/` directory using the `-name` function. This might be useful when trying to find directories that have a partiular name that may also be nested within a subdirectory.

## -type

### Example 1
```
ashishjayamohan@Ashishs-MacBook-Pro docsearch % find ./technical -type f
./technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
./technical/government/About_LSC/Progress_report.txt
./technical/government/About_LSC/Strategic_report.txt
./technical/government/About_LSC/Comments_on_semiannual.txt
./technical/government/About_LSC/Special_report_to_congress.txt
./technical/government/About_LSC/CONFIG_STANDARDS.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
...
[Many more lines]
```
In this example, we used the `-type` function with `f` to find all the items within `technical/` that are files. This is useful for isolating just the files in a particular directory and its subdirectories.

### Example 2
```
ashishjayamohan@Ashishs-MacBook-Pro docsearch % find ./technical -type d
./technical
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/government/Media
./technical/plos
./technical/biomed
./technical/911report
```
In this example, we used the `-type` function with `d` to find all the items within `technical/` that are directories. This is useful for isolating just the directories and subdirectories in a particular directory.

### Example 3
```
ashishjayamohan@Ashishs-MacBook-Pro docsearch % find ./technical/government -type f 
./technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
./technical/government/About_LSC/Progress_report.txt
./technical/government/About_LSC/Strategic_report.txt
./technical/government/About_LSC/Comments_on_semiannual.txt
./technical/government/About_LSC/Special_report_to_congress.txt
./technical/government/About_LSC/CONFIG_STANDARDS.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
./technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
./technical/government/About_LSC/diversity_priorities.txt
./technical/government/About_LSC/reporting_system.txt
./technical/government/About_LSC/State_Planning_Report.txt
./technical/government/About_LSC/Protocol_Regarding_Access.txt
./technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
./technical/government/About_LSC/conference_highlights.txt
./technical/government/About_LSC/State_Planning_Special_Report.txt
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/section-by-section_summary.txt
...
[Many more lines]
```
In this example, we used the `-type` function with `f` on the `technical/government/` subdirectory to just find all the items within `technical/government/` that are files. This is useful for isolating just the files in a particular directory.

## -size

### Example 1
```
ashishjayamohan@Ashishs-MacBook-Pro docsearch % find ./technical -size +0c
./technical
./technical/government
./technical/government/About_LSC
./technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
./technical/government/About_LSC/Progress_report.txt
./technical/government/About_LSC/Strategic_report.txt
./technical/government/About_LSC/Comments_on_semiannual.txt
./technical/government/About_LSC/Special_report_to_congress.txt
./technical/government/About_LSC/CONFIG_STANDARDS.txt
./technical/government/About_LSC/commission_report.txt
...
[Many more lines]
```
In this example, we used the `-size` function with `+0c` to find all the files and directories within `technical/` that are larger than 0 characters. The plus denotes that the files in question must be larger than the specified length. This is useful for isolating non-empty files and directories in a specific directory.

### Example 2
```
ashishjayamohan@Ashishs-MacBook-Pro docsearch % find ./technical -size +1k
./technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
./technical/government/About_LSC/Progress_report.txt
./technical/government/About_LSC/Strategic_report.txt
./technical/government/About_LSC/Comments_on_semiannual.txt
./technical/government/About_LSC/Special_report_to_congress.txt
./technical/government/About_LSC/CONFIG_STANDARDS.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
./technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
./technical/government/About_LSC/diversity_priorities.txt
./technical/government/About_LSC/reporting_system.txt
./technical/government/About_LSC/State_Planning_Report.txt
./technical/government/About_LSC/Protocol_Regarding_Access.txt
./technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
./technical/government/About_LSC/conference_highlights.txt
./technical/government/About_LSC/State_Planning_Special_Report.txt
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/section-by-section_summary.txt
./technical/government/Env_Prot_Agen/jeffordslieberm.txt
./technical/government/Env_Prot_Agen/final.txt
./technical/government/Env_Prot_Agen/ctf7-10.txt
...
[Many more lines]
```
In this example, we used the `-size` function with `+1k` to find all the files and directories within `technical/` that are larger than 1 kibibyte (1024 bytes). This is useful for isolating non-empty files and directories in a specific directory that are higher than a certain threshhold in size.

### Example 3
```
ashishjayamohan@Ashishs-MacBook-Pro docsearch % find ./technical -size -1k
./technical
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Post_Rate_Comm
./technical/plos/pmed.0020191.txt
./technical/plos/pmed.0020226.txt
./technical/911report
```
In this example, we used the `-size` function with `-1k` to find all the files and directories within `technical/` that are smaller than 1 kibibyte (1024 bytes). This is useful for finding empty files and files directories that are below a certain size.