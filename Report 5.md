HW 5, CS 625, Spring 2023
================
Sai Soujanya Ivaturi
Mar 23, 2023

### Part 1:Create Distribution Charts

For Part 1, I have used US Census Bureau State Population dataset
(NST-EST2019-alldata).

The dataset can be downloaded using the link below.

<https://www.census.gov/data/datasets/time-series/demo/popest/2010s-counties-total.html#par_textimage_70769902>

I have imported the packages by using the commands below.

    import {vl} from "@vega/vega-lite-api"
    import {fromColumns, printTable} from '@uwdata/data-utilities'

##### Boxplot

To create the boxplot,we require the distributions for the 2019 birth
rates (RBIRTH2019 column) death rates (RDEATH2019 column) migration
rates (RNETMIG2019 column) for all the states in the US.

I have made modifications using excel. I have searched for the columns
mentioned above using vlookup. I copied these values into a new excel
file (Saved as cleaned_nst.csv) and inserted them into my vega-lite
workbook using the line of code below.

    data = FileAttachment("cleaned_nst.csv").csv()

I have put the distributions on the x-axis (RBIRTH2019, RDEATH2019, and
RNETMIG2019) and related values on the y-axis for this boxplot.

I have used the code snippet below for the boxplot.

    vl.markBoxplot()
    .title("Distribution of birth, death and migration rates of all the states in the US")
    .data(data)
    .encode(
    vl.x().fieldN('Distributions'),
    vl.y().fieldQ('Values'),
    vl.color().fieldN('Distributions')
    )
    .width(600)
    .render()

![](boxplot.png)

According to the graph above, there are outliers in the field
RNETIMIG2019, and the distribution of the migration is more. The
birthrate is higher and also there exists more outliers.

The above box plot is optimal because it has organized large amounts of
data and visualizes outlier values. But it is not proper for detailed
analysis of the data as it is dealing with the summary of the data
distribution.

##### Histogram

As we can use any of the mentioned columns (RBIRTH2019 column RDEATH2019
column and RNETMIG2019 column), I have chosen to use RDEATH2019 column.

I have uploaded the file to create histogram using the line of code
below.

    data1 = FileAttachment("nst-est2019-alldata.csv").csv()

I have used the RDEATH2019 column on the x-axis and aggregate count on
the y-axis.

I have used the code snippet below for the histogram.

    vl.markBar()
    .title("Histogram1 : Distribution of the death rate of all the states in the US")
    .data(data1)
    .encode(
    vl.x().fieldQ('RDEATH2019')
    .bin({'maxbins':10}),
    vl.y().aggregate('count'),
    )
    .width(700)
    .render()

![](histogram1.png) According to the graph above, I have observed that,
for around 23 states, the death rate ranges from 8.0 to 9.0. I’ve set
the bin size to 10, and the plot is distributed for all ten bins.

The above histogram is encouraged for its simplicity which offers an
insightful look at frequency distribution. But it is not advisable as it
cannot read exact values because data is grouped into categories.

##### eCDF

As we can use any of the mentioned columns (RBIRTH2019 column RDEATH2019
column and RNETMIG2019 column), I have chosen to use RDEATH2019 column
for eCDF as well.

I have used RDEATH2019 on the x-axis and cumulative count on the y-axis.

I have used the code snippet below for the eCDF.

    vl.markLine()
    .title("eCDF : Distribution of the death rate fof all the states in the US")
    .data(data1)
    .transform({
    "sort": [{"field": "RDEATH2019"}],
    "window": [{"op": "count", "field": "count", "as": "Cumulative Count"}],
    "frame": [null, 0]  })

    .encode(
    vl.x().fieldQ('RDEATH2019'),
      // .bin(true),
    vl.y().fieldQ('Cumulative Count'),
    // vl.color().fieldN('STNAME')
    //   .legend(null),
    // vl.tooltip().fieldN('STNAME')
    )
    .width(700)
    .render()

![](eCDF.png)

According to the above graph, I have noticed that there has been a
gradual increase in the death rate, which has reached up to 12%.

The above eCDF is better than histogram because the main and important
key values and features can be directly read from the diagram. But
analyzing the data is little difficult.

### Further Analysis

Among all charts, I believe histogram and eCDF are the best. The count
of distribution is noted in the histogram, and the ecdf plot shows the
gradual increase of the distribution curve for the death rate.

I also think in the boxplot, it is a little difficult to identify the
findings at one glance.

I was looking for the specific interval with the highest number of
counts registered. I adjusted the size to 30

I have noticed that -16 bins in the plot with correct count values. It
shows the count clearly. -Gaps are formed in the histogram.

I have increased the size by using the line of code below.

    .bin({'maxbins':30})

Below is the histogram made with bin size 30.

![](histogram2.png)

Vega-lite link : <https://observablehq.com/d/9edd8b3ffeaf5b0b>

References:

<https://vega.github.io/vega-lite/docs/boxplot.html>

<https://vega.github.io/vega-lite/docs/bin.html#histogram>

<https://vega.github.io/vega-lite/docs/window.html#cumulative-frequency-distribution>

<https://www.youtube.com/watch?v=ZV_Yjcs5WtM>

<https://www.youtube.com/watch?v=0_GNbNwKB_0>
