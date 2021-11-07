# Kickstarter Analysis

## Note
This is version 2 of files for assessment. An early filtering/unfiltering user error was made in version 1 Kickstarter workbook which carried forward errors in the dataset into analysis and data presentation. All files have been kept in this same branch for full transparency.

## Overview of Project
Initial [dataset](data-1-1-3-StarterBook.xlsx) was used to provide a better understanding of the extent initial fundraising goals and launch dates determined the outcome Kickstarter campaigns. 

### Purpose
Up-and-comer playwright Louise was able to earn close to her initial fundraising goal. She has asked us now to determine from our dataset how various kickstarters were affected by 1) when they were launched and 2) their funding goals. The following analyses aimed to provide her with the information she can use at a glance.

## Analysis and Challenges
Initial work on the .xlsx was performed to prepare the data for the above objectives including:
* Split category and subcategory into separate columns
* Converted unix timestamps for campaign launch and deadline into short dates 
* Obtaining the year based (via `=year()` function)

Other editions made, not directly related to answering the above questions:
* Determined percent funded.
* Determined mean donations.
* Conditional formatting for visual feedback.

To answer Louise's questions, two tables were generated from the Kickstarter worksheet and visualized. The first is a Pivot Table which tabulated the count of outcomes according to the launch date of campaigns by month and filtered to show only Theater categories of kickstarters: 

(insert Pivot table for launch dates)

And then visualized as a line chart to best view trends over time:
(insert theater outcomes vs launch)

The second table utilizes `COUNTIFS()` functions calling the counts for the following outcomes from the Kickstarter worksheet: Successful, Failed and Canceled projects. These counts were organized into certain bins or ranges of funds goals. The number of kickstarter campaigns were summed for each bin (`=sum()`) and the percentage of campaigns for each outcome was determined:
(insert table for goals)

These percentages were then plotted in a line chart against bins of goal ranges to view trends between the different outcomes:
(insert outcomes vs goals chart)

### Analysis of Outcomes Based on Launch Date
Plotting the outcomes of theater kickstarters over time shows several things: 1) In every month, theater kickstarters are generally more successful than they fail, 2) there are certain months that consistently see more robust launches than others (May, June, July, August) which suggests seasonality around those months. That being said, the chart suggests the best time to launch kickstarters would be May as it had the highest number of successful campaigns and that the worst time would be December. Indeed, if we also account for the ratio of successful:failed projects within each month (see below), May launches (2.02) are twice as likely to succeed compared to December's 0.97 success ratio. Louise should 

### Analysis of Outcomes Based on Goals
What are the kickstarters that are in the 35000 to 50000 bins?


### Challenges and Difficulties Encountered
One of the recurring difficulties encountered was being able to execute visualized plots in my head into the necessary formulae in Excel. Typically what ends up happening is a longwinded solution when a more elegant solution can be derived if the approach to presenting the data was slightly different or even if it was just simpler. For example, to create the chart for Outcomes based on Goals, my first attempt was a histogram, pre-filtered on Kickstarter worksheet for the desired outcome, with the x-axis displaying bins of individual goals. Obviously, this isn't useful as there are way too many bins to cover such a large range of Goal values and isn't useful as the outcomes cannot be compared against each other. A more concise and elegant solution, as suggested by the deliverable instructions, is to provide a range of goals in fewer bins and to visualize by line chart.

## Other Comments

### What are some limitations of this dataset?

### What are some other possible tables and/or graphs that we could create?