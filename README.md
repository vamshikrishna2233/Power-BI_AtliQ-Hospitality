# REVENUE ANALYSIS - ATLIQ HOSPITALITY

### Live Dashboard:[Click Here](https://app.powerbi.com/view?r=eyJrIjoiZTE5NjE5NTAtZjVhMi00ZjM1LTlmYTYtMDE2M2U3MTJhNGYwIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9)
### Portfolio:[Click Here](https://codebasics.io/portfolio/vamshikrishna-nandi)



# Synopsis

AtliQ Grands is a well-established hospitality company that owns multiple five-star hotels across India. The company has been in the industry for the past 20 years and is known for its luxury and business hotels.

__PROBLEM STATEMENT__

AtliQ Grands owns multiple five-star hotels across India. They have been in the hospitality industry for the past 20 years. Due to strategic moves from other competitors and ineffective decision-making in management, AtliQ Grands are losing its market share revenue in the luxury/business hotels category.

Objective: To provide AtliQ Grands with insights from their historical data to regain their market share and revenue.

__SKILLS DEMONSTRATED__

This project exposed me to learn a lot using Microsoft Power BI.

· Multiple complex DAX formulas and Functions.

· Calculated columns

· Data Extraction, Cleaning, and Transformation (ETL)

· Data Modelling

· Data Visualization


__MOCKUP__- To build this kind of dashboard.
![mock up dashboard_atliq grands](https://github.com/LavanyaVishwakarma/powerbi_1/assets/120155873/2931c68b-e726-4735-9240-421fc2349aa3)


__DATA SOURCING__

The dataset used for this analysis was collected from Code Basics’ website, I have uploaded the CSV files.

1. dim_date
2. dim_hotels
3. dim_rooms
4. fact_aggregated_bookings
5. fact_bookings 


__DATA TRANSFORMATION__

Data Loading and Power Query Documentation

Create a folder in Desktop and store all the csv files related to hospitality challenge.

Open a Power BI file, and In "Get Data", select the option as folder and browse through the folder containing csv files.

Then go to Tranform data to expand each and every dataset.

Now, duplicate the data source 4 times and in each one, expand one dataset by clicking on "Binary" option. also, rename the tables accordingly.

Power Query steps for tables:

dim_date:

remove the column 'day_type'
we are deleting this because, we got a feedback from the mock dashboard review that Friday and Saturday are
considered as weekends in the industry and not sunday. But In our datasets, saturday and sunday are considered
as weekends. So we delete this column and re-create day_type using calculated columns.
dim_rooms

The column names are not captured here. We need to select "Use First Row as Headers" option .


__DATA MODELLING__
![Data_model_Hotel](https://github.com/LavanyaVishwakarma/powerbi_1/assets/120155873/a1403f07-2cbf-49b1-943f-98dd094c259c)


__BUILDING DAX__

Calculated Column

Our first Calculated column is to get number from week_no column of dim_date into week_number and the formula is :
week_number = WEEKNUM(dim_date[date])

Our Second Calculated column to get day_type from dim_date table. So, as we know in hospitality domain weekdays are Sunday to Thursday and weekends are Friday and Saturday. So, the formula to get day_type is : day_type =
var wkd = WEEKDAY(dim_date[date])
return if(wkd>5,"Weekend","Weekday")


__MEASURES__

Revenue : To get the total revenue_realized : formula : Revenue = SUM(fact_bookings[revenue_realized]) : and the table is fact_bookings.

Total Bookings : To get the total number of bookings happened: Formula : Total Bookings = COUNT(fact_bookings[booking_id]): and the table is fact_bookings.

As, there are 26 measures. To check the detail of all measures visit metrics_list.xlxs


__INSIGHTS__

* Mumbai generates the highest revenue (669 M) followed by Bangalore, Hyderabad and Delhi.
* AtliQ Exotica performs better compared to all 7 type of properties with 320 Million revenue, rating 3.62, occupancy percentage 57 and cancellation rate as 24.4%.
* AtliQ Bay has the highest occupancy of 66%.
* Week 24 recorded the highest revenue among all, which is 139.6 Million.
* Delhi tops both in occupancy and rating followed by Hyderabad, Mumbai, Bangalore.
* AtliQ lost around 298 Million in cancellation.
* Elite type rooms has the most booking and as well higher cancellation rate.

## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://codebasics.io/portfolio/vamshikrishna-nandi)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/nandi-vamshi-krishna/)
