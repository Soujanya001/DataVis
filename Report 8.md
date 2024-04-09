HW 8, CS 625, Spring 2023
================
Sai Soujanya Ivaturi
Apr 20, 2023

#### Dataset 1

All states History dataset:

This data set contains daily live tracking information for all 56 US
states and territories in three major areas: total tests, patient
outcomes, and demographic information, all of which have a data quality
rating. This live tracking stopped at a point in 2021, so we have the
information till 2021.

This data collection contains approximately 20781 observations with 41
columns and a mix of categorical and numeric values.

Here is the link to my dataset:

<https://covidtracking.com/data/download/all-states-history.csv>

#### Dataset 2

National History dataset:

This data set has all the combined 56 states of information with around
370 observations with 17 columns and it is a mix between categorical and
numeric values.

Here is the link to my second dataset:

<https://covidtracking.com/data/download/national-history.csv>

------------------------------------------------------------------------

In HW6, the questions that I came up were

*Question 1* : Which states had the highest number of COVID-19 cases and
deaths during the pandemic

As we can clearly see that the number of cases are more in the state CA
(California) which is exceeding 150 million and to deaths NY which is
around 7 million.

![](hw6-1.png)

I have used horizontal bars for this visualization because it would be
easy for us to read without any difficulty.

*Question 2* : Does the probability of death vary with the increase in
positive cases

I was curious about the relationship between the number of positive
cases and the overall number of deaths. What effect do positive cases
have on the death trend? I chose a Scatter plot to discover this
relationship because it allows us to see how much one element affects
another.

![](hw6-2.png)

We can conclude from the above image that the likelihood of death is
lower when individuals have positive cases. It demonstrates that the
majority of individuals are recovering from the virus. When compared to
the other states in the United States, Connecticut is the only one where
the death probability rate is nearly equivalent to the number of
positive cases.

### Exploratory Data Analysis

Exploratory Data Analysis is a method of analyzing datasets in order to
summarize and discover the relationships between each variable in the
data collection. When we speak about COVID, the very first question that
anyone has is, “How many current positive cases are there?”

We can determine this by comparing the number of positive cases to the
overall number of tests administered. I intend to demonstrate a quick
analysis of the total number of tests given and the number of positive
cases, recovered cases, and the people who died due to COVID until now.

I have loaded the datasets (all-states-history.csv and
national-history.csv) into OpenRefine to check for any anomalies. I have
used Text Facet to check for any duplicates.

I have used Numeric Facet on numeric columns if there are any
non-numeric values.

As I have not found any kind of anomalies in the data, I have loaded the
dataset into Tableau which will help in the EDA process.

I went through the references listed below and checked the different
dashboards which helped me in deciding on a few questions to propose for
my project.

I intend to work on the data only in the year 2020. Therefore, in the
questions below, I have focused only on 2020.

------------------------------------------------------------------------

### Generating questions

For HW7,

*Question 1*: Finding out the currently hospitalized patients and among
those who are on the ventilator.

Chart 1 : I used a line chart to show the comparison between the people
hospitalized currently and the people on ventilators currently. I showed
this using tableau. There I considered the date, hospitalized currently,
and On ventilator currently columns.

x-axis : Months of 2020

y-axis : Hospitalized currently and On-ventilator currently (including
all the States)

![](hw7-1.png)

I showed the graph with a dual-axis which has the same axis range for
both attributes. But there should only be one axis when we are
representing two quantitative attributes with respect to an ordered
attribute. So I decided to show the refined output for this particular
chart.

------------------------------------------------------------------------

Chart 2 :

I have used the national-history dataset, which has information on the
daily counts for all 56 states. The chart below depicts all of the
current hospitalized and are on ventilator residents in the United
States.

If I consider the all-states-history.csv file, I must pivot the entire
dataset to obtain the current number for each state. So, in order to
answer the question, I considered the national-history.csv file.

![](hw7-2.png)

According to the above figure, more over 100,000 individuals are
hospitalized in the United States, and approximately 7500 people are
currently on a ventilator. This indicates that persons who are
hospitalized are recovering, with only around 10% of them in a critical
condition.

” Hospitalized persons in Critical Condition ”

I chose the above title because when we look at a chart or graph, such
as the one above, we don’t see everything at once, but instead focus on
one important feature, i.e. the title (i.e. storytelling tips). It
piques the viewer’s interest in learning whether the information is
correct or not.

This data reveals that the relationship between current hospitalizations
and persons on ventilator instructs us on how to explore the chart.

------------------------------------------------------------------------

*Question 2* : Finding out the currently hospitalized patients and the
death rate.

Chart 1 :

I have used Tableau to recreate the chart. I used a line chart to show
the comparison between the people hospitalized currently and rate of
increase in deaths. I showed this using tableau. There I considered the
date, hospitalized currently, and death rate columns.

To include only 3 states (CA, TX & FL), I have added the filter.

Tables -\> State -\> Show Filter -\> Select CA TX FL

x-axis : Months of 2020

y-axis : Hospitalized currently and Death rate currently (CA, TX & FL)

![](hw7-3.png)

------------------------------------------------------------------------

Chart 2 :

To figure this out, I looked at all-states-history data and filtered it
for CA, TX, and FL. According to the world meter, these three states
have a high number of cases. I was curious about the current
hospitalizations in relation to total deaths. However, the column death
in the CSV file shows the total number of deaths since January 2020. The
patients hospitalized on that day are listed in the currently
hospitalized column. It would be incorrect to compare and build a graph
for current hospitalizations with the total death rate.

![](hw7-4.png)

------------------------------------------------------------------------

For HW 8,

I intend to refine the chart as below.

Here, I’ve considered the current hospitalizations with the daily death
rate increase. It provides information on persons who are currently
hospitalized, as well as the death rate. I analyzed the number of people
currently hospitalized on the y axis and the growth in mortality rates
on the x axis for three states. According to the graph, current
hospitalizations are higher, whereas death increases are lower.

![](hw8-1.png)

#### STORY-TELLING

The below are the visualization guiding principles that I have referred
to complete this visualization.

- One of the basic principles is to be clear on our intent. What are we
  going to show the audience? Here I wanted to show the relation for
  both currently hospitalized and increase in death rate.
- Data cleaning is required for some datasets to show the exploratory
  data analysis.
- Choosing the correct graph, we should have a clear idea on idioms
  which idiom is suitable for what analysis. Here is my case, I have
  considered the scatter plot to show the relation.
- Make sure where the audience pays their attention, one is the title
  should attract and the other is the colors that we are using to depict
  the graph.
- Don’t over complicate the graphs with different designs and patterns.

I have given the title

**“How the death rate increase on current hospitalizations??”**

because I feel the title increases the viewer’s curiosity to know
whether there is an increase in the death rate with the current
hospitalizations.

I have given the subtitle

**“Data shows the death increase count for current hospitalizations in
three states”**

which gives the information about the count in the chart.

**Description of all design decisions made in transforming from the
draft to the refined chart:**

*scatter plots* are ideal for visualizing the relationship between two
quantitative variables. Here I have used the scatter plot to figure out
how the currently hospitalized and death rate varies.

The *marks* are basic geometric elements that depict items or links.
Here for the scatter plots, points are the marks.

The *channels* control the appearance of a mark.

- Vertical position - hospitalizedCurrently,
- Horizontal position - deathIncrease,
- color represents the three states i.e CA, TX, and FL.
- shape is square and size as default.

------------------------------------------------------------------------

Below is my Observable link :

<https://observablehq.com/d/c022556cce14bb6a>

------------------------------------------------------------------------

**Final Thoughts**

I have spent ample time for creating the visualizations. I had to do
around 7 visualizations from 2 different datasets. So deciding on the
questions was a little tough. I had to check both the datasets and find
the connection between them. Then come up with the questions. Dealing
with vegalite, r and writing code took much time.

Splitting this project into 3 different assignments was helpful because
I could spend much time on a single question. If it was as one
assignment it would have been really hard to concentrate on details. I
had much time to research and be precise with my visualizations.

Despite of being little complicated, the visualization process is really
interesting and informative.

------------------------------------------------------------------------

References :

<https://covidtracking.com/data/download>

<https://www.crazyegg.com/blog/data-storytelling-5-steps-charts/>

<https://visme.co/blog/data-storytelling-tips/>

<https://github.com/nytimes/covid-19-data>

<https://github.com/COVID19StatePolicy/SocialDistancing>

<https://vega.github.io/vega/docs/>
