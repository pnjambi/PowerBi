# PWC Power Bi Virtual Experience - Call Center Data Set Analysis
## Problem Statement 
### KPI’S Requirement
Total number of calls over a specified period
Total call duration in hours
Total call duration in minutes
Average call duration in minutes
Response time percentage
### Data Source
The data used was obtained from PWC Power Bi virtual case experience 
### Data preparation
The data cleaning and transformation was done in Excel using advanced power query editor and also Power Bi transform capabilities.
-Handling missing values
-Removal of duplicates
-Removal of unnecessary columns and rows
-Data type; Changed date type with locale
### Creating New Measures using DAX
Date table; DateDim = CALENDAR(MIN('Call Center_Call Center'[Call Timestamp]),MAX('Call Center_Call Center'[Call Timestamp]))

Day of the week; Day =FORMAT(DateDim[Date],"ddd")

Day No = WEEKDAY(DateDim[Date],2)
### Data Modelling 
<img width="595" alt="image" src="https://github.com/pnjambi/PowerBi/assets/113362256/5c12837e-ccf9-47df-9f77-137739a2e56a">

### Dashboard
<img width="643" alt="image" src="https://github.com/pnjambi/PowerBi/assets/113362256/a1e50e1f-ec10-4734-be1c-ac0f401f61af">
