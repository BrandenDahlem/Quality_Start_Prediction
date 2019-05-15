# MLB Pitching Performance Clustering and "Quality" Start Prediction

### Motivation: 

In a follow-up to my midterm project exploring team data across 20 seasons in the MLB, I would like this project to again focus on baseball. Not only is it a sport with an incredible amount of available data, but it is also something I have thoroughly enjoying diving deeper into these past few months. 

### Questions: 

  1. *Can clustering methods be used to classify pitchers by complete season statistics?*
 
  2. *Can predictive analytics be used in determining the outcome of individual game performance?*

### Resources: 

The following online resources and Python libraries were utilized in the facilitation of this project:

- http://www.Baseball-reference.com

- Sean Lahman's Baseball Database

#### Python Libraries: 

- Pandas
- scikit-learn
- Matplotlib
- Selenium

##### Additional Libraries:

- BeautifulSoup
- PyBaseball


### Data Collection

Data was collected from Baseball-reference using packages from the Selenium library, as well as BeautifulSoup, to scrape tabular data across 13 seasons for all 30 MLB teams. Included below is a GIF of the web scraper in the process of loading and reloading the webpage for each of the ~400 keyword searches used to complete the dataset. 

![Data Scraper](https://media.giphy.com/media/1UZ8fMGbztxrSXiYyV/giphy.gif)

## Project Structure:

### Clustering based on single-season performance: 

- _8800_ entries, one for every single-season performance between the 2006 and 2018 seasons. 

- Key statistics being used in this experiment: 
  - IP: Innings Pitched - Number of Innings thrown by a pitcher over the course of a season
  - K/9: Strikeout Rate - Number of Strikeouts thrown in a 9-inning game
  - **tERA:** True Earned Run Average - Attempts to quantify a pitcher's performance based on what he can control. Pitchers              who record mostly ground balls and popups, as opposed to line drives and fly balls, are rewarded for inducing                  weaker contact.
  - **LOB%:** Percentage of runners left on base over the course of a game
  - FIP: Fielding Independent Pitching - Similar to tERA, but does not factor balls in play. Measures only outcomes a pitcher             can control. 
  - **GB/FB:** Ground Ball to Fly Ball Ratio - Higher value means lower risk
  - **BABIP:** Batting Average on Balls in Play - The opposite of FIP, measures only the performance of the pitcher based on                    their defense
  - SwStr%: Percentage of pitches that resulted in a batter swinging
  
<a href="url"> <img src="https://github.com/BrandenDahlem/Quality_Start_Prediction/blob/master/images/cluster_1.png" align="Center" height="600" width="600" ></a>

The bottom of this chart are mostly relief pitchers, and pitchers with fewer innings. The bottom Right corner of the plot are relievers with a very high Strikeout per 9 innings rate. We can determine this due to the tapering off as innings increase. High performing starters tend to not record as many strikeouts as relief, as their role in a game tends to be much longer.

I then clustered for groups of 10 to 15 pitchers based on the same performance metrics, but instead of using 5 clusters, I used 1000 clusters. For example, I used single-season performances of Aroldis Chapman, a prolific veteran reliever, to highlight the different cluster groups his performances fall into. 

<a href="url"> <img src="https://github.com/BrandenDahlem/Quality_Start_Prediction/blob/master/images/aroldis.png" align="Center" height="440" width="700" ></a>

The same was done for starting pitchers. First, I indentified clusters that included Cy Young Award-winning pitchers, the award given out at the end of the season to the player voted by sports writers as the top overall performer. I then identified the cluster with the greatest amount of these seasons. 

<a href="url"> <img src="https://github.com/BrandenDahlem/Quality_Start_Prediction/blob/master/images/cy_young_cluster.png" align="Center" height="440" width="700" ></a>

But the findings I found most valuable in this research involved locating pitchers that could potentially be seen as "undervalued" by most fans and/or front offices. So I found clusters with a few Cy Young award winners and identified pitchers within those clusters that had similar performances. 

<a href="url"> <img src="https://github.com/BrandenDahlem/Quality_Start_Prediction/blob/master/images/small_cluster.png" align="Center" height="220" width="350" ></a>

This cluster contains seasons from Clayton Kershaw and Jacob DeGrom, both former Cy Young award winners. 

<a href="url"> <img src="https://github.com/BrandenDahlem/Quality_Start_Prediction/blob/master/images/big_pitchers.png" align="Center" height="220" width="350" ></a>

And performances from Jose Berrios, Mike Foltynewicz, and Walker Buehler, all of whom are signed to rookie contracts at the league minimum of $570,000. It's worth noting, in this instance, that Clayton Kershaw's annual salary is $31 million, and Jacob DeGrom just signed a contract with the Mets for 5 years, $137.5 million.

<a href="url"> <img src="https://github.com/BrandenDahlem/Quality_Start_Prediction/blob/master/images/small_pitchers.png" align="Center" height="220" width="350" ></a>




### Quality Start Prediction

- “Quality Start” - John Lowe, a sportswriter for the Philadelphia Inquirer, coined the term in 1985 as a means to gauge whether a pitcher did his job.
    - A Quality Start is defined  as, “When a starting pitcher pitches at least SIX innings and allows THREE earned runs or           fewer.”

- _65,000 entries_, one for each pitching start from 2006-2018

- Features being considered: 
    - SO/IP - Number of strikeouts recorded per inning in a start
    - BB/IP  - Number of walks per inning pitched
    - **Str_Ratio**  - Ratio of strikes/balls in an outing
    - H/IP - Hits per inning pitched
    - HR - Home Runs allowed in a start
    - **WPA** - Win Probability Added - “Clutch Statistic” - Determines a small positive or negative value for each play within a                 game that a player has directly contributed to
    - **aLI** - average Leverage Index - Similar to WPA, measures the performance of the player in high pressure situationss
    - 2B - Doubles allowed
    - SB - Stolen Bases allowed

  
<a href="url"><img src="https://github.com/BrandenDahlem/Quality_Start_Prediction/blob/master/images/quality_distribution.png" align="Center" height="300" width="300" ></a>
 
 Worth noting is the distribution of the dataset, which appears to be almost 50/50. This is beneficial in making predictions moving forward. 
 
 One statistic I found valuable in evaluating this distribution further was the variable for Bill James' Game Score: 
 
 <a href="url"> <img src="https://github.com/BrandenDahlem/Quality_Start_Prediction/blob/master/images/BJgamescore.png" align="Center" height="440" width="700" ></a>
 
 
