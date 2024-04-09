HW 3, CS 625, Spring 2023
================
Sai Soujanya Ivaturi
Feb 16, 2023

Part 1 Small Multiples Line chart \#1

    For Part 1, I have chosen to re-create the Small Multiples Line chart #1. 
    I have done this using Microsoft excel. 

Article: Remake: Paired Column Chart from WSJ
(<https://policyviz.com/2018/03/01/remake-paired-column-chart-from-wsj/>)
Excel data file: PolicyViz_WSJ_Remake.xlsx

![](Screen1.png)

    After downloading the dataset,
    Step 1 : I have changed the years format for example, 2004 to '04, to match the given chart.
    Step 2 : I have selected the year and 'white' cells (To create each chart individulally) 
    -> Line -> Line with Markers.
    Step 3 : To have the same y-axis for all the individual charts, 
    I have selected y-axis and clicked on format cells -> Axis options -> Maximum value = 20.0.
    Step 4 : Line -> Solid line -> Color = Blue
    Step 5 : Marker -> No fill -> Color = Blue

    I have implemented the same method for Black, Asian and Hispanic in the similar way.

    For Black
    Line -> Solid line -> Color = Red
    Marker -> No fill -> Color = Red

    For Asian
    Line -> Solid line -> Color = Green
    Marker -> No fill -> Color = Green

    For Hispanic
    Line -> Solid line -> Color = Yellow
    Marker -> No fill -> Color = Yellow

    Step 6 : I have added initial and last values at the beginning and ending of the lines.

    Step 7 : I had removed the y-axis from Black, Asian and Hispanic because,
    all of the charts share the same y - axis.

    Step 8 : Insert -> Text -> 
    "Out of Work"
    "Percent of families with at least one member unemployed"

![](Part%201.png)

    I assume I was able to re-create the chart as shown for Part 1

Part 2 Line chart \#3

    For Part 2, I have chosen to re-create the Line chart #3. 
    I have done this using Tableau. 

Article: Remake: Time Series Column Chart
(<https://policyviz.com/2018/06/07/remake-time-series-column-chart/>)
Excel data file: PolicyViz_BarTimeChart.xlsx

![](Screen2.png)

    After loading the dataset in to Tableau,

    Step 1 : F1 -> Columns
    Step 2 : Measure Names -> Color (Marks)
    Step 3 : Measure Names -> Filters (Unselect Count of Cycle and Scatter)
    Step 4 : Measure Values -> Rows -> Sort ascending by measure values
    Step 5 : I have changed the colors of the measure names

    Cotton - Orange
    Wheat - Green
    Rice - Grey
    Corn - Blue
    Soybeans - Yellow

    I have noticed that the data and the graph were contradicting. 
    So, I had to swap the values of Wheat -> Corn, Corn -> Soybeans to match the given chart.

    Step 6 : I have renamed the chart to "Midpoint acreage for major field crops, 1987-2012" to display it a the top.

![](Part%202.png)

    I couldn't add the label names at the top of the lines in the line chart for Part 2.

References :

    https://www.youtube.com/watch?v=9EwmF2p2VsA
    https://www.youtube.com/watch?v=KnV5RczOuOE
    https://policyviz.com/2018/06/07/remake-time-series-column-chart/
    https://policyviz.com/2018/03/01/remake-paired-column-chart-from-wsj/
