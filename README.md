# PWC Power Bi Virtual Experience - Call Center Data Set Analysis
![image](https://github.com/pnjambi/PowerBi/assets/113362256/237ef5be-fab3-42a3-b13b-26483d00d062)

## Problem Statement 
### KPI’S Requirement
* Total number of calls over a specified period
* Total call duration in hours
* Total call duration in minutes
* Response time percentage
### Data Source
The data used was obtained from PWC Power Bi virtual case experience 
### Data preparation
The data cleaning and transformation was done in Excel using advanced power query editor and also Power Bi transform capabilities.
* Handling missing values
* Removal of duplicates
* Removal of unnecessary columns and rows
* Data type; Changed date type with locale
### Creating New Measures using DAX
DateDim = $CALENDAR(MIN('Call Center_Call Center'[Call Timestamp]),MAX('Call Center_Call Center'[Call Timestamp]))$

Day of the week; Day = $FORMAT(DateDim[Date],"ddd")$

Day No = $WEEKDAY(DateDim[Date],2)$

TotalCalls = $COUNT('Call Center_Call Center'[Id])$

TotalCallDuration(Min) = $SUM('Call Center_Call Center'[Call Duration In Minutes])$

TotalCallDuration(Hrs) = $[TotalCallDuration(Min)]/60$

AvgCallDuration(Min) = $AVERAGE('Call Center_Call Center'[Call Duration In Minutes])$

Response Time % = $CALCULATE([TotalCalls],'Call Center_Call Center'[Response Time] ="Within SLA"|| 'Call Center_Call Center'[Response Time] = "Above SLA")/[TotalCalls]$

### Data Modelling
*created a relation between the main table and the date dimention table
<img width="595" alt="image" src="https://github.com/pnjambi/PowerBi/assets/113362256/5c12837e-ccf9-47df-9f77-137739a2e56a">

### Home Dashboard 
Uing Charts to Visualize the performance of the call center
<img width="643" alt="image" src="https://github.com/pnjambi/PowerBi/assets/113362256/a1e50e1f-ec10-4734-be1c-ac0f401f61af">
### Grid Dashboard
Displaying a table of all call details
