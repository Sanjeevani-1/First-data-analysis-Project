# First-data-analysis-Project
This project is part of the professional certification course "Excel to MySQL: Analytic Techniques for Business" by Duke University from Coursera Platform


Increasing Real Estate Management Profits: Harnessing Data Analytics

## Project Overview:

•	Elicit information about important variables relevant to the analysis;

•	Draw upon my new MySQL database skills to extract relevant data from a real estate database;

•	Implement data analysis in Excel to identify the best opportunities for Watershed to increase revenue and maximize profits, while managing any new risks;

•	Create a Tableau dashboard to show Watershed executive the results of a sensitivity analysis; and

•	Articulate a significant and innovative business process change for Watershed based on your data analysis, that you will recommend to company executives.

## 1.	Elicitation:

                                       Ask a lot of questions to the stakeholders!!

The first step in requirements elicitation is gleaning a comprehensive and accurate understanding of the project’s business need. During the elicitation process, an analyst’s strong understanding of the business need will help her guard against scope creep and gold plating, as well as select the proper stakeholders and elicitation techniques.

### Elicitation Techniques:
After securing the proper stakeholders, an analyst must determine the best techniques for eliciting requirements.

1.	Brainstorming
2.	Document analysis
3.	Focus Group
4.	Interface Analysis
5.	Interviews
6.	Observation (job shadowing)
7.	Prototyping
8.	Requirements workshops
9.	Survey/questionnaire

Watershed wants to obtain following things and the business recommendation if they should change long term rental to short term

(1) calculate how much it would cost to convert and maintain each of this client’s properties as a short-term rental

(2) determine the nightly rental price that would maximize the profits from each of these properties, if they were converted to short-term rentals. We would then like you to use     this information to, 

(3) calculate which properties would have increased profits as short-term rentals, and 

(4) determine how profitable, overall, it would be if Watershed converted some of this client's properties into short-term rentals. 

(5) need to determine how much cash Watershed would need in order to realize any potential profits from converting the properties.


### From Elicitation following things are extracted:

1.	Things to be assumed for further analysis:

. The analysis should be constrained to the 244 properties owned by the one client.

· The occupancy rate of those 244 properties is 97.3% (or 36/37 months) when they are managed as long-term rentals.

· The initial capital required to convert a long-term rental property to a short-term rental property is $30,000 (for furnishings, linens, etc.). That capital expenditure will depreciate over 5 years.

· $6000 in cash will be needed for each property each year after the first (conversion) year to cover items that wear out quickly. This amount is treated as an expense and is not depreciated.

· Utilities will be $300 a month for each property, or $3600 a year.

· The hospitality fee (variable cost) for each visit (for key service, cleaning, etc.) will be $100, regardless of the actual number of days of a visit.

· The average short-term stay is 3 nights.

· All the properties have the same capital expenditure and fixed costs.

· 10% of the rental fee should be budgeted for potential regulatory and legal fees.

· 20% of the rental fee should be budgeted for the online short-term rental provider (like Airbnb).

· The two fees above are also combined and called the "transaction fee" in some spreadsheets and questions. The total default transaction fee is 30%.

· All clients pay their rent on time.


2.	Things to be ignored:

· weekly or seasonal changes in rent or occupancy rate.

· marketing strategies, like discounts or coupons.

· special events during the year that might affect the rentals in one specific location.

· loss in rent during the time interval when properties are being converted to short-term rental properties.




## 2.	Data Extraction and Visualization:
                                                         Know your Data!!
                                                         
The capstone database is extracted using SQL queries using Jupyter notebook. The contains in the database such as fields in each table are determined by writing the queries and ERD as well as Relational schema is prepared with the help of ERDplus for knowing how the data is organized and get easy access for joining the tables. After that the queries are written for joining the tables and get whole data in csv format, which contains 244 rows. The ERD and Relational schema are given below:

![erd](https://user-images.githubusercontent.com/64282818/96377327-c0aefe00-11a2-11eb-864a-c7d23505d0ab.png)

