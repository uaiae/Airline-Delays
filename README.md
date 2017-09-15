--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
Summary

in no more than 4 sentences, briefly introduce your data visualization and add 
any context that can help readers understand it
1
2
3
4

--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
Design

Find below all feedback I received from the first version to the final 
visualization. 
I also included the description of the changes that I managed to implement 
(as I am still far away from being a d3 wizard :-)).

--------------------------------------------------------------------------------
Feedback index_v01.html

Johnny H.
01 Add possibility to change y-axis range in order to remove outliers and to 
   see possible patterns (e.g. yearly osscilations)
02 Add possibility to highlight airline & airport for all other time stamps, 
  in order to see evoluton of this airline at this specific airport over time
03 Show a ranking e.g best airline
04 Add number of flights and total delay in mouseover box
05 Ignore NaNs - don't just set them to 0

Christian A.
06 no trend visible without clustering the data
07 AA biggest airline of the world 
08 best show median of average delays
09 compare median of different airlines
10 cluster airports 
 (according tofor example megaregions
  https://en.wikipedia.org/wiki/Megaregions_of_the_United_States )
 
Thomas B.
11 Would like to explore pattern, e.g. see osscilations versus time.
12 Allow to filter for dedicated airlines, eg. high-light all circles 
  belonging to an airline
13 Show median of all airlines&airports 
14 Show median of a selected airline

Changes implemented
Christian A. 
5 Allow clustering: I decided to us as selection the major airports 
 (definition as given on
  https://www.transtats.bts.gov/OT_Delay/ot_delaycause1.asp?display=data&pn=1)
  major airports: ATL, BWI, BOS, CLT, MDW, ORD, DAL, DFW, DEN, DTW, FLL, IAH, 
  LAS, LAX, MIA, MSP, JFK, LGA, EWR, MCO, PHL, PHX, PDX, SLC, SAN, SFO, SEA, 
  TPA, DCA, IAD  (30 airports))
  
Thomas B. 
2 Highlight airline circles

--------------------------------------------------------------------------------
Feedback index_v02.html

Michael W.

Changes implemented

--------------------------------------------------------------------------------
index_v03.html Final version delivered


--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
Resources
list of sources I consulted to create my visualization

Data Source
- Bureau of Transport Statistics https://www.transtats.bts.gov/OT_Delay/OT_DelayCause1.asp?pn=1
  I downloaded the following file: 973767840_62017_2345_airline_delay_causes.csv (all airports and all airlines from June 2003 unitl June 2017).
  The header of this file contains the parameter names. Some of the parameter names contained a leading blank, which I deleted in the csv file directly.
