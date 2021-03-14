---
layout: default
---
# Data Integration
**Original Author: Nic Weber**  
**Editing & Updates: Bree Norlander**  

The next four weeks of our class will focus on "grand challenges" in data curation. A [grand challenge](https://en.wikipedia.org/wiki/Grand_Challenges) in this context is a problem that requires sustained research and development activities through collective action. Data integration, packaging, discovery, and meaningful descriptive documentation (metadata) are longstanding grand challenges that are approached through a community of practitioners and researchers in curation. This module focuses on data integration as it operates at the logical level of tables and data that feed into user interfaces.

## Integration as a Grand Challenge

In the popular imagination, much of curation work is positioned as the activities necessary to prepare data for meaningful analysis and reuse. For example, when data scientists describe curation work they often say something to the effect of "95% of data science is about wrangling / cleaning."

If there are only two things I am trying to actively argue against in this class it is this:

- Curation is not *just* cleaning or wrangling data. It includes the attendant practices of making data contextually meaningful. This includes a good deal of cleaning or wrangling, but is much broader in scope than simply preparing data for analysis.
- Metadata is not just "data about data". It is a complex and important knowledge organization activity that impacts nearly every aspect of data use. Every time someone says "metadata is just data about data" a tautology angel gets its wings.

In future weeks we will discuss practical ways to approach metadata and documentation that are in line with curation as an activity that goes beyond simply preparing data for analysis. This week, however, we are focused on conceptualizing and approaching the topic of data integration. The combining of datasets is a grand challenge for curation in part because of our expectations for how seemingly obvious this activity *should* be. Take a moment to consider this at a high level of abstraction: One of the spillover effects of increased openness in government, scientific, and private sector data practices is the availability of more and more structured data. The ability to combine and meaningfully incorporate different information, based on these structures, should be possible. For example:

- All municipalities have a fire department.
- All municipal fire departments have a jurisdictional mandate to proactively investigate fire code compliance.
- It follows, logically, that we should be able to use openly published structured data to look across jurisdictions and understand fire code compliance.

But, in practice this proves to be incredibly difficult. Each jurisdiction has a slightly different fire code, and each municipal fire department records their investigation of compliance in appreciably different ways. So when we approach a question like "fire code compliance" we have to not just clean data in order for it be combined, but think conceptually about the structural differences in datasets and how they might be integrated with one another.

## Enumerating data integration challenges

So, if structured data integration is intuitive conceptually, but in practice the ability to combine one or more data sources is incredibly difficult, then we should be able to generalize some of the problems that are encountered in this activity. Difficulties in data integration break down into, at least, the following:

1. **Content Semantics:** Different sectors, jurisdictions, or even domains of inquiry may refer to the same concept differently. In data tidying we discussed ways that data values and structures can be made consistent, but we didn't discuss the ways in which different tables might be combined when they represent the same concept differently.
2. **Data Structures or Encodings:** Even if the same concepts are present in a dataset, the data may be practically arranged or encoded in different ways. This may be as simple as variables being listed in a different order, but it may also mean that one dataset is published in `CSV` another in `JSON` and yet another in an `SQL` table export.
3. **Data Granularity:** The same concept may be present in a dataset, but it may have finer or coarser levels of granularity (e.g. One dataset may have monthly aggregates and another contains daily aggregates).

The curation tradeoff that we've discussed throughout both DC 1 and DC 2 in terms of "expressivity and tractability" is again rearing its head. In deciding how any one difficulty should be overcome we have to balance a need for retaining conceptual representations that are accurate and meaningful. In data integration, we have to be careful not go overboard in retaining an accurate representation of the same concept such that it fails to be meaningfully combined with another dataset.

Data Integration, as you might have inferred, is always a downstream curation activity. But, understanding challenges in data integration can also help with decisions that happen upstream in providing recommendations for how data can be initially recorded and documented such that it will be *amenable* to future integration. (A small plug here for our introductory module - when I described a curator's need to "infrastructurally imagine" how data will be used and reused within a broader information system, upstream curation activities that forecast data integration challenges are very much what I meant.)

## Integration Precursors 

To overcome difficulties in combining different data tables we can engage with curation activities that I think of as "integration precursors" - ways to conceptualize and investigate differences in two datasets before we begin restructuring, normalizing, or cleaning. These integration precursors are related to 1. Modeling; 2. Observational depth; and, 3. Variable Homogeneity.

### Modeling Table Content

The first activity in data integration is to informally or formally model the structure of a data table. In DC 1 we created data dictionaries which were focused on providing users of data a quick and precise overview of their contents. Data dictionaries are also a method for informally modeling the content of a dataset so that we, as curators, can make informed decisions about restructuring and cleaning.

Here is an example of two data dictionaries for the same conceptual information: 311 service requests to the city of [Chicago, IL](https://data.cityofchicago.org/Service-Requests/311-Service-Requests/v6vf-nfxy) and [Austin, TX](https://data.austintexas.gov/City-Government/311-Unified-Data-Test-Site-2019/i26j-ai4z). Intuitively, we would expect that data from these two cities are similar enough in  content that they can be meaningfully combined. 

Before even before looking at the content of either data table we can assume there will be: 

1. A date
2. A report of some service outage or complaint
3. A location of the report or complaint, and 
4. The responsible city service that should respond.

The reality is much messier. 

![Data Dictionaries from Chicago and Austin 311 Data](https://raw.githubusercontent.com/norlab/LIS-546-SPR2021/master/_images/dataintegration-model.png)

Even though these two cities record the same information about the same concept using the same data infrastructure (each city publishes data using a Socrata-based data repository) there are appreciable differences and challenges in integrating these two datasets. The annotations above point out some of these slight but appreciable differences: 

- Granularity - We can see that the Chicago dataset contains a variable `SR_Status` that includes information about whether or not the request is open, as well as whether or not the request is a duplicate. The Austin dataset contains a similar variable `Status` but instead of also recording a duplicate here, there is a second variable `Duplicate` that contains this information. That is, the Austin dataset is more granular. If duplicate information were important to retain in our integrated dataset we would need to determine a way to tidy these variables or values.

- Semantics - Both datasets include information about the most recent update (response) to the request, but these are variables are labeled in slightly different ways - `Last_Update_Date` and `Last_Modified_Date`. This should be a simple to tidy by renaming the data variable (but as we will see, this proves to be more more challenging than just renaming the variable).

- Structure - Both datasets also include location information about the report. However, there is both different granularity as well as a different ordering of these variables. To tidy this location information, we would need to determine which variables to retain and which to discard.

The process of modeling our data tables before integration facilitates making accurate decisions, but also enables us to record those decisions and communicate them to end-users. A data dictionary, or a loose description of the contents of both tables, is often our first step in deciding which data cleaning activities we need to undertake for integrating data.

### Determine the Observation Depth  

In integrating two data tables there will likely be a difference in granularity of values. That is, even if the same variable is present in both datasets this does not necessarily mean that the same unit of measurement is used between the two data tables. 

As curators, value granularity prompts a decision about what specificity is necessary to retain or discard in the new integrated table. 

A simple example will make this clear. Imagine we have three tables `A`, `B`, and `C`. Each table contains the same variable `X`, but the values for `X` in each table have a different observational depth. In comparing the values for this variable we might observe different units of measurement. 

<img src="https://raw.githubusercontent.com/norlab/LIS-546-SPR2021/master/_images/3_tables.png" alt="Three tables with one variable called X. X has different values" width="300"/>

(Keep in mind - A, B and C represent the three different tables, and X represents the same variable found in all three tables.)

This example looks simple at face value, but will require an important decision for integration. Tables `A` and `B` both represent observational values of `X` as [integers](https://en.wikipedia.org/wiki/Integer). Table `C` represents the observational values of `X` as a decimal number.

Once we recognize this difference, our decision is simple - we can either convert the values in `A` and `B` to be decimals (1.0, 2.0, etc) or we can round the values in `C` to create integers. 

Regardless of our decision it is important to note that we are not just changing the values, but we are also changing their `encoding` - that is whether they represent integers or decimal numbers. (And we would need to document this change in our documentation). This may also affect their data type, for example [Python](https://www.w3schools.com/python/python_datatypes.asp) has both integer and float (for decimal values) data types.

Let's look at differences in observational depth from two variables in the 311 data described above.

<img src="https://raw.githubusercontent.com/norlab/LIS-546-SPR2021/master/_images/CreatedDate_2tables.png" alt="Two tables of Created Dates with different levels of granularity" width="300"/>

Chicago represents time of a 311 report following a `MM-DD-YY HH:MM` form, while Austin represents this same information with `YYYY-MMM-DD HH:MM:SS 12HRM`

The observational depth is greater (has more granularity) in the Austin table. But, we also have some untidy representations of `date` in both datasets. 

If we want to integrate these two tables then we have to decide 

1. How to normalize the values; and, 
2. Which depth of granularity to retain.

Regardless of how we decide to normalize this data, what we have to try to retain is a reliable reporting of the date such that the two sets of observations are homogenous. For example, the Chicago data doesn't include seconds for a 311 request. So, we can either add these seconds as `00` values in the Chicago table, or we can remove the seconds from the Austin table. In either decision, we are changing the depth of granularity in our integrated table. (Note, we also need to transform the hours so that they either represent a 24 hour cycle, or are marked by a 12HR marking such as `AM` or `PM`).

### Determine Variable Homogeneity

The last integration precursor that we'll discuss has to do with the homogeneity of a variable. In modeling two or more tables for potential integration we will seek to define and describe which variables are present, but we've not yet identified whether or not two variables can be reliably combined. To make this decision we need to first determine the goals of the integration. Some general criteria to consider when thinkng about the goals of integration are as follows:

- Analysis and Computation - If we are optimizing data integration for easing analysis then we want high amount of homogeneity in the variables we will combine.
- Synthesis - If we are optimizing for a more general purpose, such as the ability to synthesize results from two different datasets, then we can likely afford to combine variables that may have less homogeneity
- Statistical Significance - If we expect to create statistical summaries that require significant results (that is we will make some decision, forecast, or generalization based on our statistical analysis) then it is of the utmost importance that the combined variables have high homogeneity. But, if all that we require is a rough sense of when or where an observation occurs then low homogeneity is acceptable.

An example of variable homogeneity will help make these points clear. The Austin and Chicago tables each contain a variable that roughly corresponds with the "type" of 311 request or report being made. In the Austin table this information is more granularly reported - there is code that is used internally `SR_Type_Code`, and a `Description` variable that provides a plain text explanation of the code. In the Chicago table there is simply a variable called `SR_Type`. If we pay attention closely to the values in these two tables we can determine that the `Description` and `SR_Type` are homogeneous. That is, the Austin table and the Chicago table have similar information but use slightly different semantic values to control the variable.

<img src="https://raw.githubusercontent.com/norlab/LIS-546-SPR2021/master/_images/SR_Type_and_Description_2tables.png" alt="Homogeneous Tables Description Variable and SR Type Variable" width="500"/>

Integrating these two variables in the same table seems possible, but we have a decision to make: We can either combine the two variables and leave the semantic value with low homogeneity, or we can create something like a controlled vocabulary for describing the type of 311 request being made and then normalize the data so that each value is transformed to be compliant with our vocabulary. For example, `Street Light Issue - Address` in the Austin table, and `Sign Repair Request` in the Chicago table both have to do with a report being made about public signage. We could create a broad category like `Public Signage` and then transform (that is, change the values) accordingly. But, we have only determined this step is possible by comparing the two variables directly. 

When we determine there is a variable homogeneity that matches our intended integration goal we can then take a curation action. But, it is only through modeling, exploring observational depth, and investigating variable homogeneity that we can arrive at any one proper curation decision. It's worth noting that the first two precursors - modeling and observational depth - don't require us to necessarily have a goal in mind. We can start to engage in these activities before we quite know exactly what, or why we are going to integrate two tables. It is at the final step, variable homogeneity, that we start to formalize our goals and optimize our decisions as a result.   

## Horizontal and Vertical Table Integration
Thus far we've described precursors to making decisions and preparing data for integration. Once we've taken these steps we're left with the practical task of combining the two tables. Generally, there are two types of table combinations that can be made: Horizontal and Vertical Integration. 

### Horizontal data integration 

Horizontal data integration is necessary when we have the same set of observations, but multiple variables *scattered* across two tables. By performing a horizontal data integration we make a table *wider* by adding new variables for each observation. If you have any experience with databases this is also referred to as a **join** (for more information about SQL joins see [this software carpentry lesson](https://swcarpentry.github.io/sql-novice-survey/07-join/index.html)). To horizontally integrate data we perform `left_joins` or `right_joins`. 

To accurately perform a horizontal data integration manually - that is copying and pasting between two datasets - it is necessary to make sure that each dataset has a shared variable. When we copy and paste one table into another, we can then simply align, or match, the two shared variables to complete the integration.

I am also going to show you how how to perform a horizontal data integration using `R`. You do not have to follow these steps unless you are interested. To follow along you should download and install the programming language [R](https://www.r-project.org/) and the integrated development environment (IDE) [RStudio](https://rstudio.com/products/rstudio/download/) (select the RStudio Desktop free installation). These example comes from friends running the [Lost Stats](https://lost-stats.github.io/) project.

```
# Install dplyr - a package in the tidyverse for restructuring data
install.packages('dplyr')

# Load the library by calling it in your terminal.
library(dplyr)

# The data we will use contains information on GDP in local currency
GDP2018 <- data.frame(Country = c("UK", "USA", "France"),
                  Currency = c("Pound", "Dollar", "Euro"),
                  GDPTrillions = c(2.1, 20.58, 2.78))

#To view the data we have just created follow the next step
View(GDP2018)

# Now we will create a second data set that contains dollar exchange rates
DollarValue2018 <- data.frame(Currency = c("Euro", "Pound", "Yen", "Dollar"),
                              InDollars = c(1.104, 1.256, .00926, 1))
```

You will now have two tables that look something like this:

<img src="https://raw.githubusercontent.com/norlab/LIS-546-SPR2021/master/_images/GDP2018_Data.png" alt="GDP 2018 Table" width="200"/><img src="https://raw.githubusercontent.com/norlab/LIS-546-SPR2021/master/_images/DollarValue2018_Data.png" alt="Exchange Rate 2018 Table" width="200"/>

In the initial steps above we have created two data tables and assigned these tables to the name `GDP2018` and `DollarValue2018`. 

To horizontally integrate these two tables we want to **join** or combine `GDP2018` and `DollarValue2018`. 

Use `help(join)` to see the types of joins that we can make in R (and specifically look for the join help in the library `dplyr`).

To complete our horizontal data integration we simply do the following:

```
GDPandExchange <- left_join(GDP2018, DollarValue2018)

#We have now horizontally integrated our two datasets. To view this integrated dataset do the following
View(GDPandExchange)
```

One helpful note about the package `dplyr` that will clarify some of the magic that just happened... the `join` function will automatically detect that the `Currency` variable is shared in both data tables. In recognizing this shared variable `dplyr` will use this, automatically, as the place to perform the left join. And helpfully, when `dplyr` detects this similarity, it simply retains just one example of the `Currency` variables and its values. Voila - a single tidy data table through horizontal data integration !

### Vertical data integration
Vertical data integration, which is much more common in curation, is when we have two tables with the same variables, but different observations. To perform a vertical integration we simply add new observations to one of our existing datasets. This makes our integrated data table *longer* because it contains more observations.  

In `R` we first will subset a native data table (one that is included as an example) and then recombine it to see how vertical integration works in practice.

```
# Load the dplyr library so we can use its magic 
library(dplyr)

# Load in mtcars data - a dataset that is native to R
data(mtcars)

# Take a look at the dataset and see what we will be first splitting and then recombining
View(mtcars)

# Split the dataset in two, so we can combine these back together
mtcars1 <- mtcars[1:10,]
mtcars2 <- mtcars[11:32,]

#Our comptuer is now holding the two tables in its memory - mtcars 1 and mtcars2. If you want to check this try 

View(mtcars1)

# Use bind_rows to vertically combine the data tables 
mtcarswhole <- bind_rows(mtcars1, mtcars2)

# The bind_rows command is simply concatenating or combing the two datsets one on top of the other.
# Now check to see the horizontally combined data tables
View(mtcarswhole)
```

These are the two most common integration tasks we will perform - integrating datasets with complimentary variables, and integrating datasets with new observations. 

The hard part about data integration, as should be obvious by now, is in evaluating and preparing data to be combined. Once we have thoroughly completed each of the different integration precursors our task for actually integrating tables is relatively simple.

## Summary
In this introduction to grand challenges in data curation we explored ways to prepare for and execute data integration at the table level. We first articulated a set of things that makes all data integration challenging:

1. Differences in semantic content
2. Differences in data structure and encoding
3. Differences in data granularity

To overcome these challenges I proposed a set of `integration precursors` that included:

1. Modeling data content
2. Determining Observation Depth
3. Determining Variable Homogeneity (its at this stage we start to formalize our integration goals)

Once these tasks were complete we looked at practical ways to combine two tables, including horizontal and vertical integration. We also were introduced to the magic of `dplyr` in performing simple data integrations. 

# Lecture

<iframe width=853 height=476 frameborder="0" scrolling="no" src="https://screencast-o-matic.com/embed?sc=cYf3oHAIEB&v=6&ff=1&title=0&controls=1" allowfullscreen="true"></iframe>

# Readings
Data integration is a topic that can be incredibly complex, and much of the published literature fails to make this an approachable or even realistic read for a course like DC II. So, you get somewhat of a pass on readings this week. 

A very helpful overview of the state of current integration challenges for the open web of data: 

- Stonebraker, M., & Ilyas, I. F. (2018). Data Integration: The Current Status and the Way Forward. IEEE Data Eng. Bull., 41(2), 3-9. [PDF](https://cs.uwaterloo.ca/~ilyas/papers/StonebrakerIEEE2018.pdf)

Please read this blog post for discussion (if you chose) on the Canvas forum: 

- Whong, Chris (2020) "Taming the MTA’s Unruly Turnstile Data" [Medium]( https://medium.com/qri-io/taming-the-mtas-unruly-turnstile-data-c945f5f96ba0)

Let me also make a plug for the Wikipedia article on [data integration](https://en.wikipedia.org/wiki/Data_integration) - this is a phenomenal overview that should compliment my writing above.

If you are interested in the history of this topic from the perspective of databases I also highly recommend the following:

- Halevy, A., Rajaraman, A., & Ordille, J. (2006, September). Data integration: The teenage years. In Proceedings of the 32nd international conference on Very large data bases (pp. 9-16). [PDF](https://www.cin.ufpe.br/~if696/referencias/integracao/_Data_Integration-The_Teenage_Years.pdf)

For a bit of historical background, Ch 1 of this book (pages 1-13) provides an excellent overview of how data were originally made compliant with web standards:

- Abiteboul, S., Buneman, P., & Suciu, D. (2000). Data on the Web: from relations to semistructured data and XML. Morgan Kaufmann. [PDF](https://homepages.dcc.ufmg.br/~laender/material/Data-on-the-Web-Skeleton.pdf)

<h2><a id="Exercise">Exercise</a></h2>
The exercise this week comes from an interesting analysis of New York City 311 data by [Chris Whong](https://t.co/J7X3FMUvQc?amp=1). What he observes is a 1000% increase in "Consumer Complaint" 311 requests since the first recorded case of Covid-19 infection in NYC. This is not without some important external conditions - After this recorded infection there was a more concerted effort by NYC residents to stockpile supplies. Having heard numerous informal complaints of price-gouging the city recommended that consumers report businesses using a 311 hotline.

A simple graph makes this more compelling than the narrative description - we see a huge spike in complaints beginning March 1st.
![](https://pbs.twimg.com/media/ETapolDX0AAt9Ye?format=png&name=900x900)

As savvy data curators, we might ask whether or not this trend holds across cities throughout the USA.  And at its core, this is a data integration challenge. If we can find other city's 311 data we should be able to reliably compare rates of 311 complaints over time. The challenge will be finding data that has the same kinds of variables, and normalizing values to have a one to one comparison between cities.

Lucky for us, there is an existing repository of [311 city data](https://andrew-friedman.github.io/jkan/datasets/).

Your exercise this week is to choose two cities from this repository and attempt to integrate a subset of their data. This will be challenging. 

**Here are some helpful pointers:**

- Choose cities that have "up-to-date" data (marked by "current" in the title)
- Subset this data so that it only includes 311 complains from March 1, 2020 forward. You can often subset data in a repository by choosing to view and filter the data first. Here is an example from [Chicago's open data portal](https://data.cityofchicago.org/Service-Requests/311-Service-Requests/v6vf-nfxy/data) (note just select filter in this interface)
- Once you have subsetted the tables for your two cities, try to eliminate any unnecessary variables from your dataset. That is - we don't need all of the information about the data - we only need a record of, for example, the complaint and the date.

**What to turn in:**

- Provide us a table of your data from two cities (a Google Sheet or Excel document is fine). If you are able to integrate the data, provide just one sheet. If you cannot - give us two separate sheets. Note - this will be challenging to do. If you spend an hour trying to integrate the two datasets and up hating me (and this class) that is completely acceptable, but make an attempt and then follow the next step. 
- Provide an explanation (~1 paragraph) of which cities you selected, what you tried to integrate the data, and why this was or was not challenging.
- You do not need to create a graph or any form of analysis - but if you do it would be very interesting to see your results!

