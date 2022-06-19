# Kickstarting with Excel


## Overview  of Project: 
Perfoming analysis on Kickstarter data to uncover trends for Louice's project campaign. As Louise's play Fever came close to its fundraising goal in a short amount of time. Now, she wants to know how different campaigns fared in relation to their launch dates and their funding goals. Therefore, this analysis would help Louice see the outcomes and determine the trends with data visualizaitons, so she can better prepare for her Kickstarter campaign.


## Analysis and Challenges: 
The analysis consists of two technical analysis deliverables: Outcomes Based on Launch Date Chart and Outcomes Based on Goals Chart. 
* Deliverable 1: Outcomes Based on Launch Date Chart
  * A new column labeled "Years" was created by extracting the year from the "Date Created Conversion" column of the Kickstarter worksheet.
  * A pivot table was created in a new worksheet labeled "Theater Outcomes by Launch Date" from the Kickstarter worksheet filtering by "Parent Category"
    and "Years", with Columns value "outcomes", Rows value "Date Created Conversion", and Values "Count of outcomes". 
  * Then the "Parent Category" was fllled by "theater".
  * The row lables were changed to display the months of the year, and the campaign outcomes were sorted in descending order.
  * Lastly, a line with markers chart was inserted showing the number of successful, failed, aor canceled projects by months, with a title "Theater 
    Outcomes based on Launch Date".
  * Challenges and difficulties encounted: 
    * To set a filter on theater category for Louise's campaign project, but the original Kickstarer worksheet only consists a combined "Category and
      Subcategory" column. Therefore, splitting the Kickstarter "Category and Subcategory" column into two distinct columns "Parent Category" and
      "Subcategory" is the key to solve the issue. In order to accomplish the task, I used the "Convert Text to Columns Wizard" under the Data
      tab to break down the data into two categories.  
     
    For more information, See [the line with markers chart visualizing the relationship between outcomes and launch month.](/Theater_Outcomes_vs_Launch.png)
    
* Deliverable 2: Outcomes Based on Goals Chart
  * A new worksheet was created and labled "Outcomes Based on Goals", with eight columns: Goal, Number Successful, Number Failed, Number Canceled, Total
    Projects, Percentage Successful, Percentage Failed, Percentage Canceled. 
  * In the "Goal" column, twelve dollar-amount ranges from less than $1,000 to over $50,000 with a $5,000 increment were grouped. 
  * Then the "Number Successful", "Number Failed", and "Number Canceled" columns were populated by using the COUNTIFS() funcations, with filters on the 
    Kickstarter worksheet "outcome" column, on the "goal" amount colunmn using the range groups, and on the "Subcategory" column using "plays" as the
    criteria. 
  * The "Total Projects" column was populated by using the SUM() function, and the percentage of successful, failed, and canceled projects for each row
    was calculated with formula and populated.
  * Lastly, a line chart was inserted showing the pecentage of successful, failed, or canceled projects by the goal-amount ranges, with a title 
    "Outcomes Based on Goal".
  * Challenges and difficulties encounted: 
    * While filtering the "Subcategory" column by "plays", I only used the filter on the Kickstarter worksheet "Subcategory" column. However, when
      populating the "Number Successful", "Number Failed", "Number Canceled" columns, the other subcategories were still be counted. After 
      troubleshooting this issue, I added the criteria "plays" to all the COUNTIFS() arguments, and the problem was solved. 
    * While creating the line chart, at first I selected the whole table to create the line chart, and I was given a chart with Y-values of number of
      campaigns. This chart was difficult to determine the trend. To overcome the difficulty, I filtered the table Y-values to percentage of successful
      failed, and canceled. Finally, the filtered chart provides a better view of the relationship between the outcomes and the goal-amount ranges. 
      
    For more information, see [the line chart visualizing the relationship between outcomes and launch goals.](/Outcomes_vs_Goals.png)
  
## Results:
#### 1. What are two conclusions you can draw about the Theater Outcomes by Launch Date?  
* The month that launched the most successful Kickstarter campaign in the theater category was May. 
* January, March, September, November and December all had roughly the same lowest number of failed campaigns launched, while May and October had roughly the same highest number of failed campaigns launched.
* The only month that lanuched theatre campaign without cancellation was October. 

#### 2.  What can you conclude about the Outcomes based on Goals?
* There was no cancellation on the plays campaign. The campaigns whose goals were less than $1,000 were the most successful, followed by the goals in the range of $1,000-$4,999 and $35,000-$44,999；while the most failed campaigns whose goal were in the range of $45,000-$49,999. 

#### 3. What are some limitations of this dataset?
* This dataset range from 2011 to 2017. There're no any recent data after 2017, which may not reflect the most recent situation and trend. 
* When looking at the "Deadline" and "Launched_at" columns in the original Kickstarter worksheet, the data in these columns contains Unix timestamps, which is not easy to read. We have to convert these timestamps into a regular month-day-year format for data analysis. 

#### 4.  What are some other possbile tables and/or graphs that we could create?
* We could create a pivot table and a bar graph to show if using spotlight would help with the outcome of the campaigns. 
* Similarly, We could create a pivot table and a bar graph to show how the staff_picked campaigns correlate to the outcomes. 
* We could also create [a bar chart to compare the outcome values in different goal-amount ranges.](/Outcomes_vs_Goals_barchart.png)

