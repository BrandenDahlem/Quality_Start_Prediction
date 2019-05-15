# Quality Start Prediction

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





The structure of my project will consist of a deeper look into what type of factors early on in a game determine the overall performance of a pitcher throughout that same game. Pitch F/x data details over 30 metrics for each pitch a pitcher throws in a season.

The performance standard of a “quality start”, or less than 3 earned runs over 6 innings or more, will be my measuring stick. In order to maintain a balance throughout the examination,  I will be working to identify pitchers that have both several quality starts, as well as a number of poor starts over the course of an entire season. 

This project incorporates the use of both R and Python.

In Python, I will be using datasets collected from baseball-reference.com in order to determine which pitchers would be best suited for this experiment. I will be calculating their fit within this project using various machine learning techniques we have studied in this course up to this point. I believe starting with unsupervised learning methods, such as clustering, will help determine this.

In R, I will use the data scraping library, baseballr, to parse through Pitch F/x data acquired by MLB Advanced Media. This will be the data I use to gather individual pitcher data once I have the pitchers identified from the work in Python. 

