HW 4, CS 625, Spring 2023
================
Sai Soujanya Ivaturi
Mar 2, 2023

Part 1

For dataset 1, I have downloaded it from the link ”
<https://data.virginia.gov/dataset/VDH-COVID-19-PublicUseDataset-Cases-by-Vaccination/vsrk-d6hx>
” which is the data sorted by the Vaccination Status.

For cleaning the data, I have used the below steps

    Step 1: I have selected the column 'Infections' 

    Infection -> Edit column -> Add column based on this column

![](Screenshot1.png)

    I have given the expression 
    ' round(((cells['Infections'].value + cells['Deaths'].value 
    + cells['Hospitalizations'].value)
    /(cells['Population Denominator'].value * 1.0))
    * 100000) '

    In the field 'New column name', I have named it as 'case rate' -> OK

![](Screenshot2.png)

    Step 2: To change it into date, 

    Report Date -> Edit cells -> Common transforms -> To date

![](Screenshot3.png)

    After cleaning the raw dataset by following the above processes, I have downloaded the cleaned dataset 
    and named it as 'CleanedDataSetPart1.csv'

    After downloading this, I have loaded the data set into tableau.

    I have used line chart to display the data and its trends. 

    The first chart contains 
    x- axis : Week ending date
    y-axis : Case rate

    I have displayed this to show the trend in cases of all unvaccinated, partially vaccinated and fully vaccinated by the week ending date.

![](Part1-A(image).png)

    I have used line chart to display the data and its trends. 

    The second chart contains 
    x- axis : Month of Report Date
    y-axis : Case rate

    In the line chart, we can clearly see that the rate of cases are decreasing for people who are fully vaccinated.

    The case rate of unvaccinated people is more and is increasing dramatically.(Red)

    Similarly, the case rate of partially vaccinated people is decreasing but still more. (Yellow)

    The case rate of people who are fully vaccinated has come down drastically and is rate is lower than the both (Unvaccinated and Partially vaccniated). (Blue)

    I have used color and labels in Marks. 
    Colors - To clearly show the difference 
    Labels - To show the actual number for better understanding.

![](Part1-B(image).png)

Part 2

For dataset 2, I have downloaded it from the link ”
<https://data.virginia.gov/dataset/VDH-COVID-19-PublicUseDataset-Vaccines-DosesAdmini/28k2-x2rj>
” which is the data sorted by the Doses administered.

For cleaning the data, I have used the below steps

    Step 1: To remove the rest of the dose numbers, except 1

    Dose Number -> Facet -> Text facet -> 2

![](Screenshot4.png)

    2 -> All -> Edit rows -> Remove matching rows

![](Screenshot5.png)

    I have followed the same procesess for deleting all the dose numbers (2, 3, 4, 5, 6) leave only Dose 1.

    Step 2: To check if we have all the Pfizer together, I have followed the below steps

    Vaccine Manufacturer -> Facet -> Text facet

      I have renamed the following as 'Pfizer'
      Pfizer 12+
      Pfizer 5- 11
      Pfizer BV 0-4
      

![](Screenshot6.png)

    Step 3: To delete 'Not Reported' and 'Out of State', I have followed the below steps

    Health District -> Not Reported -> All -> Edit row -> Remove matching rows

![](Screenshot7.png)

    I have followed the same steps to remove the rows of 'Out of State'

     Health District -> Out of State -> All -> Edit row -> Remove matching rows
     
     Step 4: To change it into date, 

    Administration Date -> Edit cells -> Common transforms -> To date
     

![](Screenshot8.png)

    After cleaning the raw dataset by following the above processes, I have downloaded the cleaned dataset 
    and named it as 'CleanedDataSetPart2.csv'

    Later, to code, I have loaded the dataset into GoogleColab and executed the following commands.

    import pandas as pd
    vaccineData = pd.read_csv("CleanedDataSetPart2.csv")
    allGroupData = vaccineData.groupby(['Health District']).agg(all_manufacturer=('Vaccine Doses Administered Count', 'sum')).reset_index()
    print(allGroupData)

    pfizerData = vaccineData[vaccineData['Vaccine Manufacturer'] == 'Pfizer']
    pfizerGroupData = pfizerData.groupby(['Health District']).agg(pfizer_manufacturer=('Vaccine Doses Administered Count', 'sum')).reset_index()
    print(pfizerGroupData)

    finalMergedData = pd.merge(allGroupData, pfizerGroupData)
    finalMergedData['pfizer_vaccines'] = (finalMergedData['pfizer_manufacturer'].astype(int) / finalMergedData['all_manufacturer'].astype(int)) * 100
    finalMergedData['other_vaccines'] = 100 - finalMergedData['pfizer_vaccines']
    print(finalMergedData)
    finalMergedData.to_csv('MergedDataSet2.csv')

    I have downloaded the merged csv file and saved it as 'MergedDataSet2.csv'

    I have used side-by-side bar chart to display the data and its trends. 

    The chart contains 
    x- axis : Measure values
    y-axis : Health District and Measure Names

    This indicates the difference in other vaccines and Pfizer vaccine in different states. 

    I have used color and labels in Marks. 
    Colors - To clearly show the difference 
    Labels - To show the actual number for better understanding

![](Part2(image).png)

    I have represented it in another way shown below.

    Pfer Vaccines : Yellow
    Other Vaccines : Green

![](Part2-B.png)

Part 3

    Proposed 1:

    To check the if there is a trend change in cases of the individual if they have taken a vaccine, 
    we need to know the report date of the cases (dataset1) and administration date of the vaccine (dataset2).

    Proposed 2:

    To check how many individuals are admitted in the hospitals, we need to know 
    the count of Hospitalizations(dataset1) and Facility type i.e., Hospitals.(dataset2)

–Python Notebook–

<https://colab.research.google.com/drive/1eRgLbLzuSi300BgAry5gvSlIhrZZR1aU?usp=sharing>

–Tableau–

Part 1:

A:
<https://public.tableau.com/app/profile/sai.soujanya.ivaturi/viz/Part1_16778059860040/Part1-A>

B:
<https://public.tableau.com/app/profile/sai.soujanya.ivaturi/viz/Part1-B_16778062405350/Part1-B>

Part 2:

A:
<https://public.tableau.com/app/profile/sai.soujanya.ivaturi/viz/Part2_16778064882870/Sheet1>

B:
<https://public.tableau.com/app/profile/sai.soujanya.ivaturi/viz/Part2-B/Sheet1>

–References–

<https://help.tableau.com/current/pro/desktop/en-us/publish_workbooks_share.htm>

<https://help.tableau.com/current/pro/desktop/en-us/publish_workbooks_permissions_add.htm>

<https://www.youtube.com/watch?v=Z_-_GDkPeic>

<https://www.youtube.com/watch?v=csXmVBw8cdo>
