# Kickstarting with Excel

## Overview of Project

### Purpose

Purpose and background

The purpose of this project is to help Louise understand how different campaigns fared in relation to 
their respective launch dates and their funding goals. Using info from all fundraising campaigns we will
help louise visualize percentage of successful, failed, and canceled campaigns to guide her for the next
fundraising campaign and also understand if her play Fever could have fared better or worse depending
on launch date and funding goal factors. We may also find that further analysis is required if we are not
able to pinpoint exact reasons for why a fundraising campaign is succesful, failed, or canceled.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

A pivot table and graph is required to perform analysis on Theater campaign outcomes. Pivot table is created after highlighting every column 
in the below Kickstarter Tab, clicking insert, selecting Pivot Table dropdown option "from table/range", and inserting into new sheet.

Pivot table then requires two filters to be added: 

- Parent Category filtered to "Theater"
- Years filtered to all

Pivot table also requires outcomes to be mapped to Column section in Pivot table, Date Created Conversion mapped to Rows(Row Labels column 
may need to be grouped to show the months of a year), and Count of outcomes mapped to Values. See below:

SNAPSHOT

PIVOT TABLE

After pivot table is complete we then need to create a line graph that maps all info to better visualize what specific month is best to Launch a 
Theater Kickstarter Fundraising Campaign. This is accomplished by highlighting the pivot table, clicking insert tab, clicking the
line graph chart button and selecting Line Graph under 2-D Line. Graph is generated below:

LINE GRAPH

### Analysis of Outcomes Based on Goals

A graph is required to perform analysis on Outcomes Based on Goals. To create graph, info was required to be pulled from Kickstarter
tab. Following columns are required:

- Goal - each row made up of varying goals set
- Number Successful
- Number Failed
- Number Canceled
- Total Projects
- Percentage Successful
- Percentage Failed
- Percentage Canceled

Number Successful, Failed, and Canceled columns all require a COUNTIFS formula using three criterias:

- outcome of campaign(Successful, Failed, or Canceled), 
- Goal range
- "Play" Subcategory

Example formula below for Subcategory Play, Successful, and within 10000 to 14999 fundraising goal:

> =COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,">=10000", Kickstarter!$D:$D, "<=14999", Kickstarter!$R:$R, "plays")

Total Project column requires a Sum formula below:

> =SUM(B:D)

Percentage Successful, Failed, or Canceled columns uses a division formula of specific outcome column divided by Total Project # and
formatted to display percentage found under home tab 

### Challenges and Difficulties Encountered

Challenging aspect of the Outcomes Based on Goals was creating the COUNTIFS formula from scratch. Once the formula was created,
I used the copy/paste function but formula kept shifting columns used to find info. I realized the formula required absolute cells
so it would not change after copy/pasting. I used F4 key to change every formula under the Number Succesful Column, then copy/pasted the
entire column formulas over to the Number Failed Column. I then had to change multiple formulas at once so highlighted
the entire row using the Find and Replace tool to find every "successful" in each formula and replace with "failed" was
the fastest way to update each column and again to replace with "canceled" in the Canceled column. This could be challenging 
and time consuming to those unaware of these shortcuts because each formula would have to be rewritten using the new criterias.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

First conclusion regarding Theater campaign outcomes are most succesful when launched in May and in June. Second conclusion
is failed outcomes are highest when fundraising campaigns are launched in May, July, and October.

- What can you conclude about the Outcomes based on Goals?

We can conclude outcomes are most succesful when campaign goal is below 1000 and also have second highest chance of success when 
between 35000 to 44999.

- What are some limitations of this dataset?

Limitations of Outcomes based on Launch Date show that although successful campaigns are most likely during the month of May, the failed
campaigns are also most likely to happen within the same month. This demonstrates that there could be other underlying factors that affect
whether a campaign fails or succeeds besides month it was launched in.

Another limitation of this dataset is that it does not show who exactly launched these campaigns. For example if a campaign had a celebrity
that endorses it or assists with the fundraising then that would have an outsized effect on success/fail/cancel rate. Of course it would be difficult 
to quantify the effect of specific people or groups that start each fundraising campaign. We could quantify by the # of followers they have on
social media but that would require pulling data from outside sources.

- What are some other possible tables and/or graphs that we could create?

We can create another table for Outcomes based on the Number of Backers a campaign project has. This would require a simple update to our
Outcomes Based on Goals tab to switch formula to pull instead from Backers column using COUNTIFS formula. This could help us by 
creating a Line graph as well to chart percentage successful, failed, and canceled with X-axis as Number of Backers and Y-axis as percentage.

We can also create a Mean/average time column of when a fundraiser campaign starts and ends for each successful, failed, and canceled
fundraiser campaigns. This will help us visualize length of time required for a succesful fundraising campaign.