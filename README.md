# Applications rating calculating & analysis
 Calculating the rating and analysis of credit applications.
## Tools
Python libraries:
* Pandas
* Mathplotlib
* Seaborn
## Data
### 'applications(2).csv' - application data with columns:
* Applied at - time of sending an application.
* Amount - how much money (UAH) applicant have requested for funding. 
* Age - age of applicant.
* Gender - gender of applicant.
* Industry - industry of organisation, where applicant works.
* Marital status - if applicant is married or not.
* External Rating - credit rating of applicant.
* Education level - degree of applicant.
* Location - region, where applicant live.
* applicant_id - unique id of each applicant.
### 'industries(2.0).csv' - table with score of each industry, used for calculating application rating.
## Purpose
1. To optimize the process of selecting loan applicants.
2. Minimize risks when agreeing credits.
3. Find patterns in the situation of loan applicants.
## Calculating of application rating
This rating must be from 0 to 100 and based on 8 conditions:
1. If external rating is 0 or candidate have not added amount of money in credit application, rating is 0.
2. If age is between 35 and 55 years, 20 points are added to the rating.
3. If the application was not submitted on a weekend, 20 points are added to the rating.
4. If the applicant is married, 20 points are added to the rating.
5. If the applicant is located in Kyiv or the region, 10 points are added to the rating.
6. Score of the industry is also added to the rating (and ranges from 0 to 20 points).
7. If external rating is greater than or equal to 7, 20 points are added to the rating.
8. If external rating is less or equal to 2, 20 points are added to the rating.
### Applications are accepted, if application rating is more then 0.
As a result, out of 13 278 applications, 12 558 were approved.
## Accepted applications analysis
Applications was observed to find relationships across amount of requested money, age, degree, location, gender, marital status and industry
All analysis is in 'appplications(2.0).ipynb'
## Insights from analysis
### About amount of money requested
* Smallest amount is only 150 UAH (about 3,5$)!
* Median = 8250 UAH;
* 25% applicants requested less than 4500 UAH, 75% - less then 13350 UAH;
* Maximum amount - 58500 UAH.
### About gender
3/4 of applicants is men (76.86%)
### About marital status
Married is 56.03% of applicants
### About age of applicants
* 14 - the youngest applicant; 25 - mode in age; 29 - median in age; 63 - the oldest applicant.
* The distribution is close to normal.
### About industries where applicants work
Top-5 is:

| Industry             | Number of applicants |
|----------------------|----------------------|
| E-commerce           | 2389                 |
| Fintech / Banking    | 1251                 |
| Medtech / Healthcare | 628                  |
| GameDev               | 527                  |
| Big Data              | 485                  |

The most uncommon:
| Industry            | Number of Applicants |
|---------------------|-----------------------|
| Legal               | 72                   |
| Machine Learning    | 66                   |
| Geospatial          | 35                   |
| Uberfication        | 17                   |
| Robotics            | 8                    |

### About degree of applicants
88% have received higher education.
| Education Level                                               | % of Applicants |
|---------------------------------------------------------------|-----------------|
| Higher education (Bachelor degree, Master's degree, Specialist Diploma) | 80.43%          |
| Two higher education degrees (Дві вищі)                       | 7.62%           |
| Lower secondary education                                     | 3.66%           |
| Secondary Specialized Education                               | 2.98%           |
| Currently pursuing higher education                           | 5.31%           |

### About location of applicants
The most common locations:
1. Kyiv or Kyiv region - 4209
2. Lviv or Lviv region - 2229

The unexpectedly large number of applicants in Lviv region and Lviv is caused by the large number of refugees from the war-torn eastern regions of Ukraine
