# Power Query Easter (Good Friday, Pentecost) Calculator
Power Query function, which calculates the date of Easter for the year received as a parameter, and is able to determine other moving holidays related to Easter (Good Friday, Pentecost).

## Syntax
```
EasterDate(yearNumOrDateOrDateTime as any, optional holidayName as nullable any, optional julianCalendar as nullable any) as date
```

## About
Possible parameters, their types and accepted values.
+ **yearNumOrDateOrDateTime** - number, text, date, datetime
+ **holidayName** (optional) - text, number - allowed values: Easter, EasterSunday, EasterMonday, GoodFriday, Pentecost, PentecostSunday, PentecostMonday or day modifier -2, 0, 1, 49, 50
+ **julianCalendar** (optional) - logical

## Example 

| yearNumOrDateOrDateTime | holidayName | julianCalendar | Result |
| ------------- | ------------- | ------------- | ------------- |
| 2024 | | | 2024-03-31|
| 2024-01-01 | | | 2024-03-31 |
| 2024-12-31 12:34:56  | | | 2024-03-31 |
| "2024" | | | 2024-03-31 |
| "2024-01-01" | | | 2024-03-31 |
| "2024-12-31 12:34:56" | | | 2024-03-31 |
| 2024 | "Easter" | | 2024-03-31 |
| 2024 | "Good Friday" | | 2024-03-29 |
| 2024 | "EasterMonday" | | 2024-04-01 |
| 2024 | "Pentecost" | | 2024-05-19 |
| 2024 | "PentecostMonday" | | 2024-05-20 |
| 2024 | "-2" | | 2024-03-29 |
| 2024 | -2 | | 2024-03-29 |
| 2024 | | false | 2024-03-31 |
| 2024 | | true | 2024-04-22 |
| 2024 | "Easter" | true | 2024-04-22 |
| 2024 | "GoodFriday" | true | 2024-04-20 |

## Get Started
* Download the example or start a new Power BI project or open a blank Excel workbook. 
* **PowerBI** Open Transform data under the Home tab, Queries group.
![Relationship](/docs/images/PBIOpenPowerQueryEditor.png)
* **Excel** Launch Power Query Editor under the Data tab, Get and Transform group, Get Data dropdown menu.
![Relationship](/docs/images/ExcelOpenPowerQueryEditor.png)
* Add a new Blank Query
  **PowerBI** Click on the Blank Query under the Home tab, New Query group, New Source dropdown menu. <br />
  ![Relationship](/docs/images/AddNewBlankQuery.png)
  **Excel** Click on the Blank Query under the Home tab, New Query group, New Source dropdown menu, Other Sources submenu. <br />
  ![Relationship](/docs/images/AddNewBlankQueryExcel.png)
* Open Advanced Editor under the Home tab, Query group.
![Relationship](/docs/images/OpeninAdvancedEditor.png)
* Copy and paste the EasterCalculatorFunc file contents
![Relationship](/docs/images/PasteToAdvancedEditorWindow.png)
* Rename the function to whatever you want (Ex: EasterDateCalculator)
  Press the right mouse button on the function name in the left panel and choose rename! <br />
  ![Relationship](/docs/images/RenameFunction.png)
* Click on the function to invoke to itself <br />
  ![Relationship](/docs/images/InvokeCustomFunctionSettings.png)
* Or add it to your table as a new column.
   Click on the Invoke Custom Functino under the Add column tab, General group. <br />
![Relationship](/docs/images/AddColumnInvokeCustomFunction.png)
