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

![relational](https://user-images.githubusercontent.com/64282818/96377412-3dda7300-11a3-11eb-9cbc-9c8d85df24d5.png)


Before any analysis or statistical modelling its important to look at the data understanding what they represent, to look for outliers, and to examine whether they contain any obvious effects or relationships. It is required for designing the model. This is done by visualizing the data in Tableau.

![4](https://user-images.githubusercontent.com/64282818/96377549-f6a0b200-11a3-11eb-83b6-890d8b4a2695.png)

![5](https://user-images.githubusercontent.com/64282818/96377547-f56f8500-11a3-11eb-807a-218978137008.png)

![6](https://user-images.githubusercontent.com/64282818/96377546-f30d2b00-11a3-11eb-8707-01010f22fbd1.png)


## 3.	Implementation of data analysis in Excel:
In order to determine the best rent level for each property, we need to be able to forecast how the occupancy rate for that particular property varies as we change the rent. For that the data should be plotted and finding the parameters such as R-squared, slope etc.   


![4](https://user-images.githubusercontent.com/64282818/96377633-762e8100-11a4-11eb-9869-1d1e8986ca6e.JPG)


The above best fit line doesn’t give any relationship between occupancy rate and the rent because simply using these raw values cannot predict the relationship due to effect of other factors such as location. The standard deviation of the occupancy rates in the data is 16.3%, and the standard error of forecasts using our linear regression is 16.1% which is very high. So, for increasing the accuracy of the model ‘Normalization’ of the data is required. In this case, each comparable property is considered nightly rent in terms of how it compares to the rents of other properties of the same type in the same location. The data is used are the 10th percentile (low) and 90th percentile (high) rents for each of the 244 combinations of comparable property type and location. Following relationship (best-fit line) is obtained.

![5](https://user-images.githubusercontent.com/64282818/96377652-9bbb8a80-11a4-11eb-8764-4bd62b1e36ac.JPG)


Now using model's parameters (the line's slope and y-intercept), along with given constraints, the optimal nightly rent (in dollars) that should be charged for the Watershed client's properties are predicted. The optimal rent is of course the rent level that would maximize total annual revenues, (the product of rent and occupancy rate multiplied by 365).

### Optimization of Forecast ST Annual Revenues Before Transaction Costs:

The optimization of forecast short-term annual revenues done by using the Microsoft solver in the excel in such a way that the optimized value of ST annual revenue is obtained. This is done by using no occupancy data with rents of less than 10th percentile or greater than 90th percentile to build the model, the constrains are used to limit the answers to rent values between the 10th and 90th percentile. But for doing this, the same thing is repeated for 244 times for each row. So, the alternate method is used for calculating the optimized forecast ST annual revenues. 

## Final Calculations And Visualization:

The calculation of following measures are carried out using excel spreadsheet and also by using Tableau calculated fields. 

Yearly'Cash'Flow'(Conversion'Year)

Yearly'Cash'Flow'(After'Conversion'Year)

Yearly'Profits"(Conversion"Year)

Yearly'Profits'(After'Conversion'Year)

These are calculated by using the formulaes provided in Guided Spreadsheets of the course. The parameters are created in Tableau for fixed and dynamic variables which are assumed as instucted by the Watershed people. Also, the calculated fields ae created for obtaining the above measures. The interactive dashboard is created by which we can determine the behaviour of model by changing the dynamic parameters. The "Jittered" map is created for getting clear insight. Also, the total amount required for conversion of property from long term rental to short term is calculated. Sensitivity analysis is performed by chnaging the dynamic parameters.

![Screenshot (144)](https://user-images.githubusercontent.com/64282818/96378248-471a0e80-11a8-11eb-8127-e1f962792ea7.png)

From observing the values got from calculated fields, by assuming the provided values of parameters, the 41 properties are profitable out of 244. For this business model the combination of short and long term rentals can be applied i.e. changing profitable properties to short term rentals and non-profitable should not convert to short terms. Implimenting this the profit can be maximized.


[http://www.modernanalyst.com/Resources/Articles/tabid/115/ID/1427/An-Overview-of-Requirements-Elicitation.aspx](url)
[https://public.tableau.com/profile/sanjeevani1970#!/vizhome/project1_16015867104710/Dashboard12](url)

# Excel to MySQL: Analytic Techniques for Business
Offered by
Duke University
