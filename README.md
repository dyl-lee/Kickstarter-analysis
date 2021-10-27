# Kickstarter Analysis

## Overview of Project
Kickstarter_Challenge.xlsx dataset will be used to determine what Kickstarter outcomes were achieved based on when they launched their campaigns and what their initial fundraising goals were. 
### Purpose
Up-and-comer playwright Louise was able to earn close to her initial fundraising goal. She has asked us now to determine from our dataset how various kickstarters were affected by 1) when they were launched and 2) their funding goals.
## Analysis and Challenges
Initial work on the .xlsx was performed to prepare the data for the above objectives including:
* Split category and subcategory into separate columns
* Converted unix timestamps for campaign launch and deadline into short dates (number formatting) 
* Obtaining the year based (via =year() function)

Other editions made, not directly related to answering the above questions:
* Determined percent funded.
* Determined mean donations.
* Conditional formatting for visual feedback.

To answer Louise's questions, two tables were generated from the Kickstarter worksheet and visualized. The first is a Pivot Table which tabulated the count of outcomes according to the launch date of campaigns by month and filtered to show only Theater categories of kickstarters. 
![Pivot_Table_Launch_Dates](https://user-images.githubusercontent.com/90335218/138988148-8eb58e6b-3025-4110-ac76-7402e3f110fa.png) 

And then visualized as a line chart.
![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/90335218/138991560-22db7a43-b095-4b5e-a553-78eace6a7daa.png)

The second table utilizes =COUNTIFS() functions calling the counts for the following outcomes from the Kickstarter worksheet: Successful, Failed and Canceled projects. These counts were organized into certain bins or ranges of funds goals. The number of kickstarter campaigns were summed for each bin (=sum()) and the percentage of campaigns for each outcome was determined.
![Table_Goals](https://user-images.githubusercontent.com/90335218/138993638-db609e43-cc28-43ba-bdaf-3b4fd0093b0d.png)

These percentages were then plotted in a line chart against the different bins of funds goal. 
![Outcomes_vs_goals](https://user-images.githubusercontent.com/90335218/138993730-662cd434-af06-45ad-83ca-1637a265a29f.png)

### Analysis of Outcomes Based on Launch Date

### Analysis of Outcomes Based on Goals

### Challenges and Difficulties Encountered
One of the recurring difficulties encountered was being able to execute the visualized data in my head into the necessary formulae in excel. 
## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
- How does campaign duration affect outcome, would that be a better metric than launch date for example?
- Does number of backers have an effect on outcome?
- How does origin of the campaign (country) affect outcome? If Louise isn't tied down to a particular country, perhaps she could have better chance of a successful campaign in another country.
