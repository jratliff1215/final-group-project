# From the Billboard Top 100 to the Grammy Awards
## Does inclusion on the Billboard Hot 100 chart increase the likelihood that a song will win a Grammy award?

Each week, the Billboard Top 100 ranks the best songs from multiple genres into a published list. However, the top spot doesn’t guarantee more than a moment of recognition. Using Top 100 Data and Grammy Winners from the past 20 years, our team will analyze datasets to determine if a Grammy winner can be determined based on the Billboard Top 100. Our team selected this topic during the recent Grammy award show on March 14, 2021. The inspiration came from the randomness of the winners, as several songs beat others which our group thought to be popular. Additionally, music brings the world together, and during these times, we can all use a little more music and song.


The datasets to be used include weekly Billboard Hot 100 songs from 1999 through 2018, and Grammy winners from 1999 through 2018. We will use logistic regression and machine learning to determine if winners can be predicted based on Billboard information. The data was found on Kaggle.com. A total of eight files were provided with music information from sources such as Spotify, Pandora, and International Charts. Our team selected Billboard Top 100 to compare against the Grammy winner file. The Billboard Top 100 data was selected for two reasons. The Billboard Charts have been available since 1958, with the Billboard Top 10 dating back to 1894 (1). Other options available are recent additions to music tracking and charts, thus determined to not provide sufficient inital data nor provide the ability to track further back in history for machine learning training. Second, the Team selected the Billboard Top 100 for how the songs are selected to be on the chart. Like the Grammys, the Billboard Top 100 is chosen each week by a committee and not consumer activity. 

# Data Exploration and Analysis

The datasets to be used include weekly top 100 songs from 1999 through 2018 and Grammy winners from 1999 through 2018. We will use logistic regression and machine learning to determine if winners can be predicted based on Billboard information. 

Our team selected this topic during the recent Grammy award show on March 14, 2021. The inspiration came from the randomness of the winners, as several songs beat others which our group thought to be popular. Additionally, music brings the world together, and during these times, we can all use a little more music and song. 

The data was provide on Kaggle.com. A total of eight files were provided with music information from sources such as Spotify, Pandora, and International Charts. Our team selected Billboard Top 100 to compare against the Grammy winner file. The Billboard Top 100 data was selected for two reasons. The Billboard Charts have been available since 1958, with the Billboard Top 10 dating back to 1894 (1). Other options available are recent additions to music tracking and charts, thus determined to not provide sufficient initial data nor provide the ability to track further back in history for machine learning training. Second, the Team selected the Billboard Top 100 for how the songs are selected to be on the chart. Like the Grammys, the Billboard Top 100 is chosen each week by a committee and not computer processing. This similarity matched the data sets on a basic compilation level. 

# Data Exploration and Analysis
Upon finding the data, the Team selected Excel to initially explore the data and identify general trends. Excel is not a popular tool for large file exploration or significant file combinations. However, the initial Excel exploration did provide the Team with initial ideas on how to approach the combination and further exploration of the data sets. Once the initial exploration provided some data insight, the Team moved the information to Python and Jupyter notebook for futher analysis. Postgres joins were completed to provide a basis for the machine learning. 


Tableau tables and charts have been constructed to provide visualizations of the dataset. These charts show total number of grammy wins compared to the total weeks on the Billboard chart, peak position on the chart, year the song was released, and genre. We have also created a chart that compares the total weeks on the chart and grammy wins based on the song's genre. 

# Machine Learing Model Questions
- Model Selection
  - We chose the logistic regression model because it is used to predict binary outcomes, and the goal of our project is to predict whether or not an artist that is on the Billboard Top 100 Chart will win a Grammy.  Some limitations of this model are that it cannot work with non-linear outcomes and it requires a large data set.
Benefits of this model are that it is simple to implement and make predictions for binary outcomes (yes/no). It is also easy to understand and update with new data to be used in the future.
- Preprocessing
  - Our team used Python in order to clean and preprocess our data. We started by dropping duplicates in the Billboard csv order to get a single instance of each song.  We arranged the data so that the first inclusion illustrated peak position on chart and total weeks on the chart, then dropped all but the first inclusion of each song.  We then dropped the "weekly_rank", "writing_credits", and "lyrics" columns, because they are not relevant for this analysis. In the Grammy CSV, we totaled number of Grammy Awards for each song to get total number of Grammy Wins.  This required elimination of the Grammy Award Title column, which is a limitation of this analysis.
- Database Interfacing
  -  Our MLM interfaces with our data by using a Python string to load cleaned CSVs from a postgres database. We began by using Python to load the cleaned data into 3 Postgres tables - Billboard, Grammy, and Grammy Genre.  We then used a join statement to combine the billboard data with the grammy wins column and grammy genre column. Finally, we used a connection f-string to load this into our MLM.
- Feature Engineering & Feature Selection
  - In order to identify the necessary features and maximize the performance of the machine learning model, we dropped Variables: "weekly_rank", "writing_credits", "lyrics". 
  - These variables were not informative for our logistic regression analysis. Dropping these unnecessary variables allowed for our machine learning model to easily read through the independent variables and increased our overall Accuracy Score from 84.62% to 94.12%.
- Training & Testing Sets
  - We are using "X" to predict "y".  "y" is the “GrammyAward” column, or the output. "X", or features, is created by dropping the “artists’’ and “name” columns from the DataFrame. Next we used the train_test_split module to split X and y into training and testing sets: X_train, X_test, y_train, y_test.    
- Model Traning
  -  We are comparing the actual outcome values from the test set against the model's predicted values. y_test are the outcomes (whether or not an artist that is on the Billboard Top 100 Chart will win a Grammy)from the original dataset that were set aside for testing. The model's predictions, y_pred, were compared with these actual values, y_test. Additional testing in the future can be performed using larger datasets containing Billboard and Grammy information from prior to the year 2000.  
- Accuracy Score
  - 0.9411764705882353 
  - The accuracy score is simply the percentage of predictions that are correct. The accuracy of the logistic regression machine learning model is 94.12%. This shows that the machine learning model will accurately predict whether or not an artist will receive a grammy based on their Billboard Top 100 Chart performance 94.12% of the time.

# Results

Our final model provided an accuracy result of 94.12%. We determined this was significant and to not reject our hypothesis that Billboard Chart information can be used to predict Grammy Winners. In comparison to the original analysis we completed, and as discussed by Hayley, that showed little or no correlation based on numbers, this model allows the user to be comfortable with their prediction. As it is well known, simply looking at a data point, it cannot be assumed what the outcome will be. For example, four-time Grammy Winner Michael Bublé has never been in the Top 20 of the Hot 100 Chart and never exceeded more than 10 weeks on the chart. For the reverse, the international YouTube sensation of Gangnam Style reached the second spot on the chart, remained there for 4 weeks, and spent over 35 weeks on the Hot 100, did NOT win a Grammy. 

At the outset of this project and the initial analysis completed on the dataset, we noted issues with the data set and other considerations we needed to be mindful of throughout the project and when reviewing the hypothesis. The cleaned Billboard information included several thousand data points. However, the set wasn’t complete due to factors such as a song not exiting the chart on our dataset, thus weeks on chart may be inaccurate. If a song was new to the chart, the peak position is likely related to the current position, which may not be where the song actually peaks. By adding this information to the dataset, which would require locating appropriate datasets, our model would likely become more accurate in predicting Grammy winners. 

Throughout most of its time, the Billboard Charts have been compiled based on committee decisions which relied on radio play or cassette or CD purchases. However, in reference to an earlier mention of Gangnam style, The Harvard Business Review published an article written by Kevin Evers, who explained how "Gangnam Style" had changed Billboard's ranking methodology of its music charts. Instead of relying solely on radio plays and paid purchases, Billboard started to place a heavier emphasis on digital sales and YouTube views. This 2017 change in the compilation process of the Hot 100 may have an impact on more recent chart and Grammy winner prediction. 
# Presentation Link
- [Google Slides](https://docs.google.com/presentation/d/1gNiLVhv1PRAzBwcYhDEzvymbgdiNwZT_MBioeOvYKPA/edit#slide=id.gce7da8c980_0_82)
- Tableau Dashboard - https://public.tableau.com/profile/jomol#!/vizhome/BillboardtoGrammyDashboard/BillboardtoGrammy?publish=yes

# Presentation Outline
Team Introductions - ALL - 1 minute:
- Hayley (sharing screen) - 15 seconds
- Jennifer - 15 seconds
- Maya - 15 seconds
- Lijoy - 15 seconds

Introduce Topic - Hayley - 3 minutes:
- Selected topic - 15 seconds
  - An analysis of Grammy award wins based on Billboard chart inclusion
- Reason selected - 15 seconds
  - Grammy Awards 2021 had just taken place, my experience in the music industry led me to be curious about consumer opinions vs. awards/critical recognition
- Description of Source Data - 30 seconds
  - Used Kaggle to find a dataset that covered Billboard statistics for the past 20 years.  Tables included Spotify streams, Billboard chart data, and Grammy award wins.
- Questions we hope to answer - 30 secs
  - Chose to analyse Grammy data and Billboard data to answer the question - “Does inclusion on the Billboard Hot 100 chart increase the likelihood that a song will win a Grammy?” Landed on this question because both Grammy awards and Billboard inclusion are determined by elite committees, do those committees agree quality?
- Data Exploration Phase - 45 secs
  - Used Excel, first step was to examine state of data, fortunately data was clean, very few null values, consistent formatting throughout. Next step was to consider potential obstacles, Artist or song titles spelled differently on grammy/billboard tables, songs included multiple times for weeks on chart
- Data Analysis Phase - 45 secs
  - Used Python for data cleaning - got down to single instance of each song and removed unnecessary columns. Used Tableau to create dashboard, illustrating how weeks on the billboard chart, peak position on the billboard chart impact likelihood to win a Grammy.  Also added interactive element to be able to filter by genre

Machine Learning - Maya - 3 minutes:
- Data Preprocessing
  - Used Python, Got single instance of each song by dropping duplicates & keeping first inclusion which illustrated peak position on chart and total weeks on the chart. Dropped "weekly_rank", "writing_credits", "lyrics", because they are not relevant for this analysis. Totaled number of Grammy Awards for each song to get total number of Grammy Wins, Required elimination of the Grammy Award Title, limitation of this analysis, would be interesting to filter by award in a future study
- Database connection
  - Used python to load cleaned CSVs into a postgres database.  Used Join statement to combine billboard data with grammy wins.  Used connection string to load this into machine learning model
- Feature engineering and Feature Selection
  - Dropped Variables: "weekly_rank", "writing_credits", "lyrics". These variables are not informative for our MLM analysis.
- Description of how data was split into training and testing sets
  - We are using X to predict y. y is the “GrammyAward” column, or the output X, or features, is created by dropping the “artists’’ and “name” columns from the DataFrame. Use the train_test_split module to split X and y into training and testing sets: X_train, X_test, y_train, y_test.
- Explanation of model choice, including limitations and benefits
  - Logistic Regression model because it is used to predict binary outcomes, and the goal of our project is to predict whether or not an artist that is on the Billboard Top 100 Chart will win a Grammy.
  - Limitations : Cannot work with non-linear outcomes, Need large data set
  - Benefits: Simple to implement and make predictions for binary outcomes (yes/no), Simple to understand and update with new data to be used in the future
- Description of Model Training
  - We are comparing the actual outcome values from the test set against the model's predicted values. y_test are the outcomes (whether or not an artist that is on the Billboard Top 100 Chart will win a Grammy) from the original dataset that were set aside for testing. The model's predictions, y_pred, were compared with these actual values, y_test.
- Description of current accuracy score 
  - 0.9411764705882353 (The accuracy score is simply the percentage of predictions that are correct.)
The accuracy of the MLM, 94.12%. This shows that the MLM will accurately predict whether an artist will receive a grammy based on their Billboard Top 100 Chart performance 94.12% of the time.
- Confusion Matrix
  - Useful to include both the F1 score and confusion matrix to further assess the precision and sensitivity of the MLM.

Dashboard - Lijoy - 3 minutes:
- How was the Database created?
- Tools used?
- Dashboard walk through with features
- Interactive features?


Results - Jennifer - 3 minutes:
- Does the model work? Can wins be predicted with new data?
  - Billboard chart is limited to those songs that have exited completely for weeks on chart or those that have just entered. 
  - Grammys started 1959 Billboard started 1894 - we could include multiple historical dataset
  - Changes in the award categories and expansion to include other countries
- Future features
  - Scraper to add weekly data and populate database each week
  - Use additional, modern data sets from spotify or pandora - does population streams have impact? 
- Additional analysis
  - Does genre have an impact on win? Interact with dashboard
  - When is a song released in relation to the Grammy awards?




