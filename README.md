# From Billboard to Grammy
## Can weeks on the Billboard Top 100, peak position on the chart, gender, or time at the top spot predict a Grammy win for a song? 

Each week, the Billboard Top 100 ranks the best songs from multiple genres into a published list. Songs float on and off, with only a few every taking the top spot. However, the top spot doesn’t guarantee more than a moment of recognition. Using Top 100 Data and Grammy Winners from the past 20 years, our team will analyze datasets to determine if a Grammy winner can be determined based on the Billboard Top 100. 

The datasets to be used include weekly top 100 songs from 1999 through 2018 and Grammy winners from 1999 through 2018. We will use logistic regression and machine learning to determine if winners can be predicted based on Billboard information. 

Our team selected this topic during the recent Grammy award show on March 14, 2021. The inspiration came from the randomness of the winners, as several songs beat others which our group thought to be popular. Additionally, music brings the world together, and during these times, we can all use a little more music and song. 

The data was provide on Kaggle.com. A total of eight files were provided with music information from sources such as Spotify, Pandora, and International Charts. Our team selected Billboard Top 100 to compare against the Grammy winner file. The Billboard Top 100 data was selected for two reasons. The Billboard Charts have been available since 1958, with the Billboard Top 10 dating back to 1894 (1). Other options available are recent additions to music tracking and charts, thus determined to not provide sufficient initial data nor provide the ability to track further back in history for machine learning training. Second, the Team selected the Billboard Top 100 for how the songs are selected to be on the chart. Like the Grammys, the Billboard Top 100 is chosen each week by a committee and not computer processing. This similarity matched the data sets on a basic compilation level. 

# Communication Protocol
Our group will communicate primarily via slack, with scheduled zoom meetings outside of class when necessary.  We have shared cell phone numbers in case of urgent questions, but will use slack for the majority of group communications.

# Data Exploration and Analysis
Upon finding the data, the Team selected Excel to initially explore the data and identify general trends. Excel is not a popular tool for large file exploration or significant file combinations. However, the initial Excel exploration did provide the Team with initial ideas on how to approach the combination and further exploration of the data sets. Once the initial exploration provided some data insight, the Team moved the information to Python and Jupyter notebook for futher analysis. Postgres joins were completed to provide a basis for the machine learning. 

Tableau tables and charts have been constructed to provide visualizations of the dataset. These charts show trends between weeks on the Billboard chart, peak position on the chart, and age of the song at the time of the Grammys. Each chart provides an interactive feature such as genre filtering or Grammy year view reduction. These features allow the user to filter by their favorite genre or compare changes across years. 

# Machine Learing Model Questions
- Which model did you choose and why?
  - We chose the logistic regression model because it is used to predict binary outcomes, and the goal of our project is to predict whether or not an artist that is on the Billboard Top 100 Chart will win a Grammy.
- Preprocessing
  -   Using two different datasets poses multiple challenges for cleaning. Discepansies in names of both artists and songs, and duplicate entries were the primary features that needed to be addressed before working with the data. Next, we determined the relevent columns in both datasets: "Name (of artist), Name (of song), Weeks on Billboard, Peak Position on Billboard, Grammy Win (Yes/No) to be useful for our MLM.
- How are you training your model?
  - We are training our model using a SQL database containing 15 out of the 20 years included in the original dataset.  We will then use the data for the remaining 5 years to test that model.
- What is the model's accuracy?
  - 0.9411764705882353
- How does this model work?
  - This model takes in data from our database and removes the column we wish to predict.  The model is then trained using the data, and predicts the outcomes based on the training. 
- If there are statistics involved, what stats are being included in analysis and why?
  - To illustrate how accurate the Machine Learning Model is, we are including the accuracy of the MLM, 94.12%. This shows that the MLM will accurately predict whether an artist will receive a grammy based on their Billboard Top 100 Chart performance 94.12% of the time. With more time, it will be useful to including both the F1 score and confusion matrix to further assess the precision and sensitivity of the MLM. 

# Presentation
The [Google slides](https://docs.google.com/presentation/d/1gNiLVhv1PRAzBwcYhDEzvymbgdiNwZT_MBioeOvYKPA/edit#slide=id.gce7da8c980_0_82) are currently in draft mode and will continued to be finalized throughout the next two weeks. 

(1) Source: Billboard Chart Beat; https://www.billboard.com/articles/columns/chart-beat/6746273/first-billboard-issue-november-1-1894
