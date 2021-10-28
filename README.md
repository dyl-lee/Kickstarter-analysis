# Kickstarter Analysis

## Overview of Project
[Kickstarter_Challenge.xlsx](data-1-1-3-StarterBook.xlsx) dataset will be used to determine what Kickstarter outcomes were achieved based on when they launched their campaigns and what their initial fundraising goals were. 
### Purpose
Up-and-comer playwright Louise was able to earn close to her initial fundraising goal. She has asked us now to determine from our dataset how various kickstarters were affected by 1) when they were launched and 2) their funding goals.
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
![Pivot_Table_Launch_Dates](https://user-images.githubusercontent.com/90335218/138988148-8eb58e6b-3025-4110-ac76-7402e3f110fa.png) 

And then visualized as a line chart to best view trends over time:
![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/90335218/138991560-22db7a43-b095-4b5e-a553-78eace6a7daa.png)

The second table utilizes `COUNTIFS()` functions calling the counts for the following outcomes from the Kickstarter worksheet: Successful, Failed and Canceled projects. These counts were organized into certain bins or ranges of funds goals. The number of kickstarter campaigns were summed for each bin (`=sum()`) and the percentage of campaigns for each outcome was determined:
![Table_Goals](https://user-images.githubusercontent.com/90335218/138993638-db609e43-cc28-43ba-bdaf-3b4fd0093b0d.png)

These percentages were then plotted in a line chart against bins of goal ranges to view trends between the different outcomes:
![Outcomes_vs_goals](https://user-images.githubusercontent.com/90335218/139169724-edb1854f-4f95-4bd9-b483-4809c39e0535.png)


### Analysis of Outcomes Based on Launch Date
The Outcomes by Launch Date line chart shows several things: 1) In almost every month, Theater kickstarters are generally more successful than they fail, 2) there are certain months that consistently see more robust launches (May, June, July, August) which could indicate a seasonality surrounding those months. It also means more competition for Louise. The line chart also suggests that the best time to launch kickstarters would be May as it had the highest number of successful campaigns (99) and that the worst time is September (40). For a more in-depth analysis, we can use these figures to calculate the ratio of Successful:Failed projects, which relates an abstract number to the rest of the data. May only holds the sixth highest ratio of 1.80 of all the months. In fact, December, which had the least total kickstarters in 8 years, held the highest success:failure ratio of 2.38. It has the lowest rate of failure and cancellation for kickstarters and has the highest success rate. With the fewest kickstarters to compete with, Louise should consider launching her kickstarter in December.


### Analysis of Outcomes Based on Goals
Visualizing percentage outcomes as a function of all Theater campaign funds goal shows an important trend, Theater Kickstarters appear more likely to succeed with a lower campaign goal (negative correlation of the blue line) while the inverse relation is seen as well (positive correlation of the orange). According to these trends, goals should be set less than $5000, although anything more than $15000 has seen failure rates higher than success rates. To bring in context, Louise's initial $10,000 goal historically had a 47% success rate. 


### Challenges and Difficulties Encountered
One of the recurring difficulties encountered was being able to execute the visualized data in my head into the necessary formulae in Excel. Typically what ends up happening is a longwinded solution when a more elegant solution can be derived if the approach to presenting the data was slightly different. For example, to create the chart for Outcomes based on Goals, my first attempt was a histogram, pre-filtered on Kickstarter worksheet for the desired outcome, with the x-axis displaying bins of individual goals. Obviously, this isn't useful as there are way too many bins to cover such a large range of Goal values and isn't useful as the outcomes cannot be compared against each other. A more concise and elegant solution, as suggested by the deliverable instructions, is to provide a range of goals in fewer bins and to visualize by line chart.


## Other Comments

### What are some limitations of this dataset? 
A quick perusal over the Kickstarter worksheet there are inconsistencies with the data set leading to inaccurate analyses. Firstly, certain categories appear to be misclassed leading to , for example when sorting through the "_Food_" category. There may also be missing data, for example "_The Mathare Project_" (ID271) has 311 backers but none of them have pledged any money towards the goal. It is unlikely that the kickstarter model has changed to allow for pledge-less backers, this may be an indication that there could be more missing data in this and other fields. Regardless of its issues, it is clear the dataset requires more robust validation.

### What are some other possible tables and/or graphs that we could create?
- How does campaign duration affect outcome, would that be more informative than launch date for example? This is something the campaigner (in this case Louise) has control over and, intuitively, the longer the campaign completion, the more donors lose interest. 
- Does number of backers have an effect on outcome?
- How does origin of the campaign (country) affect outcome? If Louise isn't tied down to a particular country, perhaps she could have better chance of a successful campaign in another country.
