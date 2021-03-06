Summary

Based on data published by the Bureau of Transport Statistics I want to share 
the average delay (measured in minutes per flight) of arriving aircraft in the US.

The visualization shows for two chosen airlines the median of the average delay 
for all airports the airline flies to in a period from June 2003 to June 2017.

Alaska Airlines and JetBlue Airways have been picked on purpose as they represent 
the best and worst American Airlines in terms of on-time performance (Status 2016).

I want to enable the viewer to follow the evolution of the performance of the 
two airlines and to understand that Alaska Airlines improved its performance over time.


Design

To allow the viewer to directly see and compare the performance of the two airlines
over time I am showing a lineplot with the median values (for all airports) 
for each airline over time. The average delay is encoded as y and time as x coordinate.

In addition I also wanted to allow the viewer to develop a better understanding 
of how the data is distributed/spread out. To do so I have chosen to a scatter plot. 
This scatterplot will be only shown when the viewer clicks on the details buttons.
I encoded date and average delay via the x-y coordinates as before, but this time 
for every single airport. To show the differences in number of flights for 
each dot I encoded this value as circle diameter (as sqrt of number flights 
and with a small bubble size range only). 
Thus I can visualize a "big" hub with a lot of flights in comparison to a small
less frequented airport.


Find below all feedback I received from the first version (index1.html) to the final 
visualization (index.html).
I included the description of the changes that I managed to implement 
(as I am still far away from being a d3 wizard :-)).


Feedback

Johnny
 Add possibility to change y-axis range in order to remove outliers and to 
 see possible patterns (e.g. yearly osscilations)
 Add possibility to highlight airline & airport for all other time stamps, 
 in order to see evoluton of this airline at this specific airport over time
 Show a ranking e.g best airline
 Add number of flights and total delay in mouseover box

Christian
 No trend visible without clustering the data
 Maybe best show median of average delays
 Compare different airlines
 You could cluster airports (e.g. according to megaregions
  https://en.wikipedia.org/wiki/Megaregions_of_the_United_States )
 
Thomas
 Would like to explore pattern, e.g. see osscilations versus time.
 Allow to filter for dedicated airlines, eg. highlight all circles belonging to an airline
 Maybe show median of all airlines&airports 


Changes implemented

NOTE: index1.html takes long to load - please  check the screenshot index1.png instead.

Index1: started with showing all data (all airlines and all airports). 

Index2:
During the discussions with Johnny, Christian and Thomas I learned that wanted to see 
patterns in the data. Thus I reduced the amount of data shown simulatneously by
addition of buttons which allow to filter for preset airlines.
I chose these airlines based on an article I found on:
https://www.fool.com/investing/2017/03/23/from-first-to-worst-ranking-the-10-major-airlines.aspx
which gives a ranking for On-Time performance. 

In order to allow the viewer to see significant differences I've chosen the best
performing airline (Alaska Air) and the worst on (JetBlue). In between I took 
big airlines (American and Southwest Airlines) which both show a clear periodicity
but differ in the spread of the delay.

The displayed y-range has been reduced to better see the periodicity.

The mouseover infobox now shows not only the average value but also gives the 
total delay (in minutes) and the number of flights for that given data point.

In addition to just show the number of flights in the infobox I encoded sqrt value
as circle radius in order to better pronounce the patterns in the data and clearer
distinguish the "size" of an airline.

Index:
I now implemented direct the comparison of the airlines. For this last version 
I just picked two airlines in the end to better compare their performance evolution.
I switched to a line plot of the medians to compare the two airlines directly.
The line plot is now used as starting point or core visualization.
In addition the viewer can still display all the details (as before on index2) 
when clicking on the airline buttons.

Resources
list of sources I consulted to create my visualization
  
Data Source
- Bureau of Transport Statistics https://www.transtats.bts.gov/OT_Delay/OT_DelayCause1.asp?pn=1
  I downloaded the following file: 973767840_62017_2345_airline_delay_causes.csv
  The header of this file contains the parameter names. Some of the parameter names contained a leading blank, which I deleted in the csv file directly.
- mega region clusters https://en.wikipedia.org/wiki/Megaregions_of_the_United_States
- From first to worst airlines https://www.fool.com/investing/2017/03/23/from-first-to-worst-ranking-the-10-major-airlines.aspx
  
D3 (Find below sources which help me to in my struggle to get familiar with D3 ... and its still a long way to go)
- Convert Nan into 0: https://stackoverflow.com/questions/7540397/convert-nan-to-0-in-javascript
- D3 Tips and Tricks: https://github.com/d3noob/D3-Tips-and-Tricks/blob/master/D3-Tips-and-Tricks-Latest.pdf
- d3.format https://github.com/d3/d3-format/blob/master/README.md#format
- Color circles on mouseover https://stackoverflow.com/questions/23703089/d3-js-change-color-and-size-on-line-graph-dot-on-mouseover
- And of course 23_globe_fixing_buttons.html as given in the Udacity course.
- multi line graph example http://www.d3noob.org/2014/07/d3js-multi-line-graph-with-automatic.html
