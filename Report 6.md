HW 6, CS 625, Spring 2023
================
Sai Soujanya Ivaturi
Apr 2, 2023

### Initial Dataset Exploration

#### Step 1: Choosing a dataset

I’ve decided on the COVID Tracking Project. This data set contains daily
live tracking information for all 56 US states and territories in three
major areas: total tests, patient outcomes, and demographic information,
all of which have a data quality rating. This live tracking stopped at a
point in 2021, so we have the information till 2021.

This data collection contains approximately 20781 observations with 41
columns and a mix of categorical and numeric values.

Here is the link to my dataset:

<https://covidtracking.com/data/download>

This is how the data looks.

![](data.png)

#### Step 2 : EDA Process (Exploratory Data Analysis)

Exploratory Data Analysis is a method of analyzing datasets in order to
summarize and discover the relationships between each variable in the
data collection. When we speak about COVID, the very first question that
anyone has is, “How many current positive cases are there?”

We can determine this by comparing the number of positive cases to the
overall number of tests administered. I intend to demonstrate a quick
analysis of the total number of tests given and the number of positive
cases, recovered cases, and the people who died due to COVID until now.

I have loaded the dataset into OpenRefine to check for any anomalies.

![](InitialOpenRefine.png)

I have used Text Facet to check for any duplicates.

I have used Numeric Facet on numeric columns if there are any
non-numeric values.

![](FinalOpenRefine.png)

As I have not found any kind of anomalies in the data, I have loaded the
dataset into Tableau which will help in the EDA process.

![](TableauData.png)

I went through the references listed below and checked the different
dashboards which helped me in deciding on a few questions to propose for
my project.

I intend to work on the data only in the year 2020. Therefore, in the
questions below, I have focused only on 2020.

#### Proposed Questions:

##### Question 1

Which states had the highest number of COVID-19 cases and deaths during
the pandemic?

Answer:

I have used horizontal bars for this visualization because it would be
easy for us to read without any difficulty.

    I have put a filter on years so that it shows only the results of 2020.

    x-axis contains 
    Total Test Results - To display the total number of tests done in each state.
    Positive - To display the total number of positive results.
    Death - To display the total number of deaths due to COVID.

    y-axis contains 56 states in an alphabetic order.

    I have used the color channel
    Orange to display Positive cases.
    Red to display Deaths.

![](Question1.png)  
As we can clearly see that the number of cases are more in the state CA
(California) which is exceeding 150 million and the same applies to
deaths as well which is almost 3 million.

##### Question 2

Does the probability of death vary with the increase in positive cases.

Answer :

I was curious about the relationship between the number of positive
cases and the overall number of deaths. What effect do positive cases
have on the death trend? I chose a Scatter plot to discover this
relationship because it allows us to see how much one element affects
another.

    I have put a filter on years so that it shows only the results of 2020.

    x-axis contains 56 states in an alphabetic order.

    y-axis contains Death Probability and Positive increase (Increase in the number of COVID positive cases).

    I have used the color channel 
    Orange to display Positive increase.
    Red to display Death probable.

![](Question2.png)

We can conclude from the above image that the likelihood of death is
lower when individuals have positive cases. It demonstrates that the
majority of individuals are recovering from the virus. When compared to
the other states in the United States, Connecticut is the only one where
the death probability rate is nearly equivalent to the number of
positive cases.

### References:

<https://www.vdh.virginia.gov/coronavirus/>

<https://covidtracking.com/analysis-updates/federal-covid-data-101-how-to-find-data>

<https://github.com/nytimes/covid-19-data>

<https://github.com/COVID19StatePolicy/SocialDistancing>

<https://www.youtube.com/watch?v=4pymfPHQ6SA>
