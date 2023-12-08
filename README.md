# REPORT-ON-HOSPITAL-INFORMATION-AND-RATING-WITH-POWER-BI

This Analysis was done for a Hospital I worked for.

The name of the Hospital is withheld for privacy purposes.

## Table of Content
- [Introduction](#introduction)
- [Content](#content)
- [Problem Statement](#problem-statement)
- [Power BI Concepts Applied](#power-bi-concepts-applied)
- [Data Sourcing](#data-sourcing)
- [Data Transformation/Cleaning](#data-transformation-cleaning)
- [Data Analysis and Visuals](#data-analysis-and-visuals)
- [Dashboard](#dashboard)
- [Conclusions and Recommendations](#conclusions-and-recommendations)
- [LImitation](#limitation)
- [Reference](#reference)


### Introduction

There are all sorts of reasons why you'd want to know a hospital's quality rating.

- 	Your mom is having her second hip replacement. Her first one went terribly and you're nervous about how she'll do. Which hospital would you suggest she have her surgery?
- 	You're selecting a health plan on your state's Exchange, but your top two choices partner with different hospitals. How will you decide which plan to pick?
- 	Your brother has Cystic Fibrosis and has to go to the ER frequently. He hates waiting. Which hospitals/states provide care in the timeliest manner?
- 	Your in-laws moved to Florida recently to retire, and have been trying to convince you to move there too. You're looking for any way possible to show them that your state is better. Does your state have better hospitals?

### Content

This file contains general information about all hospitals that have been registered with Medicare, including their addresses, type of hospital, and ownership structure. It also contains information about the quality of each hospital, in the form of an overall rating (1-5, where 5 is the best possible rating & 1 is the worst), and whether the hospital scored above, same as, or below the national average for a variety of measures.

### Problem Statement

- Which hospital types & hospital ownerships are most common?
- Which hospital types & ownerships are associated with better than average ratings/mortality/readmission/etc
- What is the average hospital rating, by state?
- Which hospital types & hospital ownerships are more likely to have not submitted proper data ("Not Available" & "Results are not available for this reporting period")?
- Which parts of the county have the highest & lowest density of religious hospitals?

### Power BI Concepts Applied

DAX Concepts: Calculated column, Custom Column, Data Modelling: Star Schema

### Data Sourcing

Data was given by the Hospital in Excel format. I downloaded the CSV file and extracted it into Power BI for cleaning, analysis, and visualization. 

The data contains a table called Hospitalinfor with 4790 rows and 30 columns with Provider ID, Hospital Name, Address, City, State, County, Hospital Type, Hospital Ownership, etc.

### Data Transformation/Cleaning

-  With the Power Query Editor of Power BI, I cleaned the data efficiently and did some transformations.

![Screenshot_154](https://github.com/Solution92/REPORT-ON-HOSPITAL-INFORMATION-AND-RATING-WITH-POWER-BI/assets/144762124/994dfd47-0af5-416d-94c8-91619ca97e36)

Some other applied steps include

- Replaced values with "Not Available"
- Add conditional Column
- Format or change column type from Text to whole number
  
### Data Analysis and Visuals

I added some measures by creating a DAX table to help in my analysis.

![Screenshot_155](https://github.com/Solution92/REPORT-ON-HOSPITAL-INFORMATION-AND-RATING-WITH-POWER-BI/assets/144762124/bc790309-4458-429a-8644-c2febbfeb9cf)

#### Measures that were added are shown below;

- No. of City = DISTINCTCOUNT(HospInfo[City])
- Average Rating = AVERAGE(HospInfo[Hospital overall rating])
- No. of Hospital = DISTINCTCOUNT(HospInfo[Hospital Name])
- Overall Rating = COUNT(HospInfo[Hospital overall rating])
- Mortality Rate = DIVIDE(COUNTAX(HospInfo,HospInfo[Mortality national comparison_1]),COUNTROWS(HospInfo),0)

### Dashboard

Here is the Dashboard I created to  represent the final story of the table/dataset

![Screenshot_156](https://github.com/Solution92/REPORT-ON-HOSPITAL-INFORMATION-AND-RATING-WITH-POWER-BI/assets/144762124/a53e1dee-febc-4fcb-9672-aec475e2d829)


#### From the dashboard, it is observed that

Which hospital types & hospital ownerships are most common?

![Screenshot_157](https://github.com/Solution92/REPORT-ON-HOSPITAL-INFORMATION-AND-RATING-WITH-POWER-BI/assets/144762124/58d02003-247f-47ab-b684-5f953c383206)

- Acute care hospitals own about 70.1% of the count of Hospital ownership while children own 2.06% to be the last on the list. 


Which hospital types & ownerships are associated with better than average ratings/mortality/readmission/etc

![Screenshot_158](https://github.com/Solution92/REPORT-ON-HOSPITAL-INFORMATION-AND-RATING-WITH-POWER-BI/assets/144762124/586b6751-2f66-4f8a-a9a1-14e81f24b624)

- Hospitals that were rated 5 had about 220.49# out of 4,812 of the overall rating over 10,000% above those that were rated 1% which is 44.10%.


What is the average hospital rating, by state?

![Screenshot_159](https://github.com/Solution92/REPORT-ON-HOSPITAL-INFORMATION-AND-RATING-WITH-POWER-BI/assets/144762124/e5af28de-44d9-41d5-94f9-e8dbe68c5575)

- The average rating was highest for NH at 3, followed by ME and RI.﻿﻿
﻿﻿
- ﻿﻿Across all 56 States, the Average Rating ranged from 0 to 3.
  

Which hospital types & hospital ownerships are more likely to have not submitted proper data ("Not Available" & "Results are not available for this reporting period")?

 ![Screenshot_160](https://github.com/Solution92/REPORT-ON-HOSPITAL-INFORMATION-AND-RATING-WITH-POWER-BI/assets/144762124/df2e7afc-2d5c-4c4f-8136-30f049c24329)

﻿- At 3,414, Not Available had the highest Count of Hospital Ownership and was 8,028.57% higher than Results are not available for this reporting period, which had the lowest Count of Hospital Ownership at 42.﻿﻿
﻿﻿
- Not Available accounted for 70.95% of Count of Hospital Ownership.﻿﻿
﻿﻿
- ﻿﻿Across all 6 Hospitals' overall rating footnote, the Count of Hospital Ownership ranged from 42 to 3,414.
  
﻿﻿
﻿Which parts of the county have the highest & lowest density of religious hospitals?

![Screenshot_161](https://github.com/Solution92/REPORT-ON-HOSPITAL-INFORMATION-AND-RATING-WITH-POWER-BI/assets/144762124/001beadf-9d78-4b64-abd0-599c60a10bf3)

- At 2,052, Voluntary non-profit - Private had the highest Count of County Names and was 22,700.00% higher than Tribal, which had the lowest Count of County Names at 9.﻿﻿
﻿﻿
- ﻿﻿Voluntary non-profit - Private accounted for 42.64% of Count of County Name.﻿﻿
﻿﻿
- ﻿﻿Across all 10 Hospital Ownership, the Count of County names ranged from 9 to 2,052.﻿﻿
﻿﻿
﻿
### Conclusions & Recommendations

- Based on the analyzed findings, it is recommended that hospitals prioritize improving data transparency, especially in areas marked as "Not Available," to provide more comprehensive and reliable information to the public. 
- Efforts should be made to encourage a broader representation of hospital ownership types, with a focus on actively involving Tribal-owned hospitals in reporting. 
- Hospitals with below-average ratings should implement quality improvement initiatives to enhance patient outcomes and satisfaction. 
- More so, a continued emphasis on meeting meaningful use criteria for Electronic Health Records and promoting transparency in reporting can contribute to overall healthcare quality and patient experience. 
- Regional variances should be considered in strategy development to address specific healthcare needs in different areas.

### Limitation

- One limitation of the dataset is the prevalence of "Not Available" entries, which hinders a comprehensive understanding of certain hospital metrics, potentially limiting the accuracy of assessments.
- Additionally, the dataset may not capture nuanced factors influencing hospital performance and quality, providing a broad but potentially oversimplified view of healthcare outcomes.

### Reference

For more information about the timeframes for each measure, see:

- [medicare](https://www.medicare.gov/hospitalcompare/Data/Data-Updated.html#)

For more information about the data itself, APIs, and a variety of formats, see:

- [Hospital-Compare](https://data.medicare.gov/Hospital-Compare)













