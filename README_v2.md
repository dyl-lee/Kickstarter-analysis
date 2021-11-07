# Kickstarter Analysis

## Overview of Project
Initial [dataset](data-1-1-3-StarterBook.xlsx) was used to provide a better understanding of the extent that initial fundraising goals and launch dates have on the outcome of Kickstarter campaigns. 

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
Plotting the outcomes of theater kickstarters over time shows several things: 1) In every month, theater kickstarters are generally more successful than they fail, 2) there are certain months that consistently see more robust launches than others (May, June, July, August) which suggests seasonality around those months. That being said, the chart suggests the best time to launch kickstarters would be May as it had the highest number of successful campaigns and that the worst time would be December. Indeed, if we also account for the ratio of successful:failed and cancelled projects within each month (see below), May launches (2.02) are twice as likely to succeed compared to December's success ratio of 0.97. 

(insert chart of ratios)

### Analysis of Outcomes Based on Goals
Project success is negatively correlated with increasing fundraising goal amounts. Specifically, the data suggests campaigns are more likely to succeed with a budget of under $15,000 with the highest percent success in those projects with goals less than $1000. Some descriptive statistics was generated to compare the goals successful and failed projects, which revealed high variance for both outcomes within the dataset. That being said, the averages (mean, median) for successful projects are consistently lower than that of failed projects.

(insert desc stats table)

To add context to these numbers, Louise's initial goal amount of $10,000 (which is higher than 85% of all successful projects) is more than 3 times higher than the median for successful projects indicating that high goal amount may set up Fever for failure.


### Challenges and Difficulties Encountered
A recurring difficulty encountered was finding the optimal visualization. For example, to create the chart for Outcomes based on Goals, my first attempt was to create a histogram, pre-filtered on Kickstarter worksheet for the desired outcome, with the x-axis displaying bins of individual goals. Obviously, this isn't useful as there are way too many bins to cover such a large range of Goal values (up to $100,000,000) and isn't useful as the outcomes cannot be compared against each other. A more concise solution is to provide a range of goals in fewer bins and to visualize by line chart.

## Other Comments

### What are some limitations of this dataset?
Firstly, the dataset only covers kickstarters from 2009 to 2017, if the intention is to inform Louise of current trends, our analyses would benefit from including recent data. Secondly, an important question to consider is: does this dataset fully capture the process 

### What are some other possible tables and/or graphs that we could create?
With this dataset, other important figures could be generated to answer some other interesting questions:
- How does campaign duration affect outcome? In other words, the duration of the campaign itself. This is something campaigners have control over and, intuitively, the longer the campaign completion, the more likely donors lose interest therefore lowering the threshold for success.
- What effect does the number of backers have on projects with various goal amounts?
- How does origin of the campaign (country) affect outcome? Does percent success differ from total projects per country?
