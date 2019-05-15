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
  


<a href="url"> <img src="https://github.com/BrandenDahlem/Quality_Start_Prediction/blob/master/images/cluster_1.png" align="Center" height="440" width="440" ></a>






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


<br>
<br>
<br>

The structure of my project will consist of a deeper look into what type of factors early on in a game determine the overall performance of a pitcher throughout that same game. Pitch F/x data details over 30 metrics for each pitch a pitcher throws in a season.

The performance standard of a “quality start”, or less than 3 earned runs over 6 innings or more, will be my measuring stick. In order to maintain a balance throughout the examination,  I will be working to identify pitchers that have both several quality starts, as well as a number of poor starts over the course of an entire season. 

This project incorporates the use of both R and Python.

In Python, I will be using datasets collected from baseball-reference.com in order to determine which pitchers would be best suited for this experiment. I will be calculating their fit within this project using various machine learning techniques we have studied in this course up to this point. I believe starting with unsupervised learning methods, such as clustering, will help determine this.

In R, I will use the data scraping library, baseballr, to parse through Pitch F/x data acquired by MLB Advanced Media. This will be the data I use to gather individual pitcher data once I have the pitchers identified from the work in Python. 

