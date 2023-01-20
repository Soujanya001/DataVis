HW 1, CS 625, Spring 2023
================
Sai Soujanya Ivaturi
Jan 19, 2023

## Git, GitHub

1.  *What is your GitHub username?*

Soujanya001

2.  *What is the URL of your remote GitHub repo (created through
    Mr. Kennedy’s exercises)?*

<https://github.com/Soujanya001/DataVis>

## R

The command below will load the tidyverse package. If you have installed
R, RStudio, and the tidyverse package, it should display a list of
loaded packages and their versions.

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.2 ──
    ## ✔ ggplot2 3.4.0      ✔ purrr   1.0.1 
    ## ✔ tibble  3.1.8      ✔ dplyr   1.0.10
    ## ✔ tidyr   1.2.1      ✔ stringr 1.5.0 
    ## ✔ readr   2.1.3      ✔ forcats 0.5.2 
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

## R Markdown

1.  *Create a bulleted list with at least 3 items*

- Purple
- Black
- Pink

2.  *Write a single paragraph that demonstrates the use of italics,
    bold, bold italics, code, and includes a link. The paragraph does
    not have to make sense.*

Hi my name is **Sai Soujanya Ivaturi** .

I am a student of *ODU* .

I am a Master’s student with ***Computer Science*** major.

My favorite search engine is [Duck Duck Go](https://duckduckgo.com).

    <html>
      <head>
      </head>
    </html>

3.  *Create a level 3 heading*

### Heading Level 3

## R

#### Data Visualization Exercises

1.  (Q2) *How many rows are in mpg? How many columns?*

There are 224 rows and 11 coloumns.

1.  (Q4) *Make a scatterplot of hwy vs cyl.*

ggplot(data = mpg) + geom_point(mapping = aes(x = cyl, y = hwy))

#### Workflow: basics Exercises

1.  (Q2) *Tweak each of the following R commands so that they run
    correctly (`library(tidyverse)` is correct):*

``` r
library(tidyverse)
ggplot(dota = mpg) + 
  geom_point(mapping = aes(x = displ, y = hwy))

fliter(mpg, cyl = 8)

filter(diamond, carat > 3)
```

ggplot(dota = mpg) + geom_point(mapping = aes(x = displ, y = hwy))

fliter(mpg, cyl = 8)

filter(diamond, carat \> 3)

## Google Colab

1.  *What are the URLs of your Google Colab notebooks (both Python and
    R)?*

Python :

<https://colab.research.google.com/drive/1y8MZVuvcicPpZFiQe5IGg5UcZLB7cm5X?usp=sharing>

R :

<https://colab.research.google.com/drive/1gMxi5tKlnvaR6G_59QdH5Jzd_j4iXeR_?usp=sharing>

## Tableau

*Insert your the image of your final bar chart here*

![SalesByWest!](/Users/saisoujanyaivaturi/Desktop/DataVis/DataVis/Tableau/SalesByWest.png)

1.  *What conclusions can you draw from the chart?*

From the bar graph,

In 2019, The sales in technology was high and the sales in Office
supplies was low.

In 2020, The sales in furniture was high and the sales in Office
supplies was low.

In 2021, The sales in furniture was high and the sales in Office
supplies was low.

In 2022, The sales in technology was high and the sales in Office
supplies was low.

## Observable and Vega-Lite

### A Taste of Observable

1.  *In the “New York City weather forecast” section, try replacing
    `Forecast: detailedForecast` with `Forecast: shortForecast`. Then
    press the blue play button or use Shift-Return to run your change.
    What happens?*

Let us try replacing ‘Forecast: deailedForecast’ with ‘Forecast:
shortForecast’ and run the change. When we click Shift-Return to run the
change, then it will show very few minor details.

1.  *Under the scatterplot of temperature vs. name, try replacing
    `markCircle()` with `markSquare()`. Then press the blue play button
    or use Shift-Return to run your change. What happens? How about
    `markPoint()`?*

Let us try replacing ‘marckCircle()’ with ‘markSquare()’ under the
scatterplot of temperature vs. name. This results in the plot of circles
changing to plot of squares and if we change it into ‘markPoint()’ then
the plot of squares will turn into points.

1.  *Under “Pick a location, see the weather forecast”, pick a location
    on the map. Where was the point you picked near?*

The point that I have picked is located at longitude :-82.29 latitude:
34.3

1.  *The last visualization on this page is a “fancy” weather chart
    embedded from another notebook. Click on the 3 dots next to that
    chart and choose ‘Download PNG’. Insert the PNG into your report.*

![Chart!](/Users/saisoujanyaivaturi/Desktop/DataVis/DataVis/Chart.png)

### Charting with Vega-Lite

`markCircle()`

1.  *Pass an option of `{ size: 200 }` to `markCircle()`.*

![Image1!](/Users/saisoujanyaivaturi/Desktop/DataVis/DataVis/Vegalite/Image1.png)

1.  *Try `markSquare` instead of `markCircle`.*

![Image2!](/Users/saisoujanyaivaturi/Desktop/DataVis/DataVis/Vegalite/Image2.png)

1.  *Try `markPoint({ shape: 'diamond' })`.*

![Image3!](/Users/saisoujanyaivaturi/Desktop/DataVis/DataVis/Vegalite/Image3.png)

`vl.x().fieldQ("Horsepower")`, …

1.  *Change `Horsepower` to `Acceleration`*

![Image4!](/Users/saisoujanyaivaturi/Desktop/DataVis/DataVis/Vegalite/Image4.png)

1.  *Swap what fields are displayed on the x- and y-axis*

![Image5!](/Users/saisoujanyaivaturi/Desktop/DataVis/DataVis/Vegalite/Image5.png)

`vl.tooltip().fieldN("Name")`

1.  *Change `Name` to `Origin`.*

![Image6!](/Users/saisoujanyaivaturi/Desktop/DataVis/DataVis/Vegalite/Image6.png)

Another example, `count()`

1.  *Remove the `vl.y().fieldN("Origin")` line.*

![Image7!](/Users/saisoujanyaivaturi/Desktop/DataVis/DataVis/Vegalite/Image7.png)

1.  *Replace `count()` with `average("Miles_per_Gallon")`.*

![Image8!](/Users/saisoujanyaivaturi/Desktop/DataVis/DataVis/Vegalite/Image8.png)

## References

*Every report must list the references that you consulted while
completing the assignment. If you consulted a webpage, you must include
the URL.*

- Reference 1, <https://r4ds.had.co.nz/workflow-basics.html#practice>
- Reference 2,
  <https://colab.research.google.com/drive/165dTuQy5P7cgG8QqZMuLWP02LD9fLpLJ#scrollTo=qJAKN6380cJc>
- Reference 3, <https://observablehq.com/@tomb/a-taste-of-observable>
- Reference 4, <https://www.tableau.com/academic/students>
- Reference 5, <https://r4ds.had.co.nz/workflow-basics.html#practice>
- Reference 6,
  <https://colab.research.google.com/drive/165dTuQy5P7cgG8QqZMuLWP02LD9fLpLJ#scrollTo=s8aeChJ4_pgz>
