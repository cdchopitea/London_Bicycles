<div align='center'>
<h1><b> Executive Summary: London Bicycles Stations and System Health Analysis </b></h1>
 </div>
<br>
<div align='justify', font-size= 15xp>
<h2><b>Background and General Findings about London Bicycles </b></h2>
London’s public bicycle scheme are a great way to get around the city and are widely used, there is a total of 781 bike stations located in the London Area. However, it appears that customer support frequently receive complains about bike stations being empty. To better address this problem a dataset from London bicycles were rides date from 2015-01-04 to 2017-06-14 was analyzed. In this dataset a total of 24,369,201 rentals were registered, however a total of 24,286,001 ‘actual trips’, bike rides over one minute, took place and consider for the study. A 60 seconds threshold was used to determine if a ride was an error either by a customer who unlock the bike by mistake or by the company itself. 
 <br>
 <br>
Bike usage normally peaks at 8:00 UTC and then at 17:00 UTC, the increased usage around this time may indicate that people are using the bikes to commute to work (Exhibit 1). As well, it appears that most rides are taking place Tuesdays and Thursdays (Exhibit 2). Further, it was found that the most frequently used route start and end in the same stations (Exhibit 3). As such, it was realized that London bikes have mostly two types of users: the commuters, and those who ride for pleasure. As well, to further investigate the types of users present in our dataset, commuters and pleasure riders were further broken down based on trip duration of people’s trips. Renting bikes costs 2 pounds per day and the first 30 minutes of a trip are free, anything above that cost extra, as well a yearly subscription (<a href= "https://www.visitlondon.com/traveller-information/getting-around-london/london-cycle-hire-scheme" target="_blank">link </a>). Based on this, commuters and pleasure riders were further broken down into those who ride above or below 30 minutes and those groups above 30 were considered to have a subscription (Exhibit 4).  As well, bike usage appears to be seasonal with higher use during the summer and less so during the winter. However, usage appears to be decreasing (see <a href="https://datastudio.google.com/s/k872xGjVfJg" target="_blank"> dashboard</a>) and further investigation on this is essential.
 <br>
 <br>
<h2><b>Analysis and Recommendations </b></h2>
While analyzing the data I noted that the table about rides has the latest date entry in 2017 while stations is updating in real time. Therefore, a deeper understanding of how supply/demand is throughout the day is necessary. For the purpose however, three periods of time were looked at for this analysis, 12:00 and 17:00 UTC of March 27, 2020 and again on March 28, 2020 at 13:00 UTC. The idea was to observe if the same stations were recurrently empty. 
 <br>
 <br>
There are only two stations that appear to be empty in at least 2 out of the 3 time periods this are ‘Breams Buildings, Holborn’ and ‘Christian Street, Whitechapel’ (Exhibit 5, 6 & 7).  What is more, these stations are not in a frequently use route (Exhibit 3). Only ‘Park Lane, Hyde Park’ which appears empty in the 3rd period seems of concern since this station has frequent use (Exhibit 3 & 7). This station is widely used by the pleasure riders, an important group for the company. As well, there are only 7 full stations in period 1 and 3 (Exhibit 8 & 9). And again, none of these stations are in a busy route. Finally, the relationship between time of day and most frequent end and start stations was looked at. Again, this confirmed that the most frequently used stations based on time seem to have an adequate supply and demand (Exhibit 10).
 <br>
 <br>
Overall, there appears to be neither a big problem with empty nor full stations. There are 781 stations of which only a very small proportion are empty or full. What is more these stations appear to be quite far from each other, meaning that a customer could go to the next closest station either to grab a bike or park. So, the problem does not appear to be of big concern, of course this situation could be improved but it will require a financial investment from the company, and it does not seem to be necessary or urgent to address every single empty station, especially if it is not in a frequently use route, and the empty stations are not always the same one (based on these periods). 
 <br>
 <br>
Nevertheless, to have a decisive conclusion the rides tables will need to be update to the present time. As mentioned, the station dataset updates in real time, while the latest rides in the rides table is dated, and thus customers behaviour may have change since 2017. My final recommendation is this: (1) Based on the data and selected periods there is no evidence to believe investment should be made to increase capacity of stations or build new ones. And, (2) gathering historic data on stations, how often they are empty or full in a day for example over a period of time and updating trips information to 2019-2020 will result in more accurate insights. Making an analysis on this data will be more useful to better identify trends and have a clearer conclusion and recommendation. 
<br>
 <br>
 </div>
<h2><b>Exhibits</b></h2>
 <br>
 
<i>Exhibit 1: </i>
<br>
<div align="center">
 <img src='https://github.com/cdchopitea/London_Bicycles/blob/master/Exhibits/Exhibit_1.png'> 
 <br>
Total trips by hour, ordered from greater to lowest total trips
 </div> 
 
<br>
<br>
<i>Exhibit 2: </i>
<br>
<div align="center">
 <img src='https://github.com/cdchopitea/London_Bicycles/blob/master/Exhibits/Exhibit_2.png'> 
 <br>
Total trips over 60 second by day of week, ordered from highest to lowest
 </div>
 
<br>
<br>
<i>Exhibit 3: </i>
<br>
<div align="center">
 <img src='https://github.com/cdchopitea/London_Bicycles/blob/master/Exhibits/Exhibit_3.png'> 
 <br>
Top 10 most popular routs in the network
 </div>

<br>
<br>
<i>Exhibit 4: </i>
<br>
<div align="center">
 <img src='https://github.com/cdchopitea/London_Bicycles/blob/master/Exhibits/Exhibit_4.png'>
 <br>
Types of riders based on time and pleasure/commuting
 </div>
 
<br>
<br>
<i>Exhibit 5: </i>
<br>
<div align="center">
 <img src='https://github.com/cdchopitea/London_Bicycles/blob/master/Exhibits/Exhibit_5.png'>
 <br>
Empty stations period 1 – 12:00, March 26, 2020
 </div>
 
 <br>
<br>
<i>Exhibit 6: </i>
<br>
<div align="center">
 <img src='https://github.com/cdchopitea/London_Bicycles/blob/master/Exhibits/Exhibit_6.png'>
 <br>
Empty stations period 2 – 17:00, March 26, 2020
 </div>
 
<br>
<br>
<i>Exhibit 7: </i>
<br>
<div align="center">
 <img src='https://github.com/cdchopitea/London_Bicycles/blob/master/Exhibits/Exhibit_7.png'>
 <br>
Empty stations period 3 – 13:00, March 27, 2020
 </div>
 
 <br>
<br>
<i>Exhibit 8: </i>
<br>
<div align="center">
 <img src='https://github.com/cdchopitea/London_Bicycles/blob/master/Exhibits/Exhibit_8.png'>
 <br>
Full stations period 1 – 12:00, March 26, 2020
 </div>
 
  <br>
<br>
<i>Exhibit 9: </i>
<br>
<div align="center">
 <img src='https://github.com/cdchopitea/London_Bicycles/blob/master/Exhibits/Exhibit_9.png'>
 <br>
Full stations period 3 – 13:00, March 27, 2020
 </div>
 
 <br>
<br>
<i>Exhibit 10: </i>
<br>
<div align="center">
 <img src='https://github.com/cdchopitea/London_Bicycles/blob/master/Exhibits/Exhibit_10.png'>
 <br>
 Most popular stations based on time for start and end stations
 </div>
 
 
 
      
