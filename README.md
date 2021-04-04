# From Billboard to Grammy
## Can weeks on the Billboard Top 100, peak position on the chart, gender, or time at the top spot predict a Grammy win for a song? 

Each week, the Billboard Top 100 ranks the best songs from multiple genres into a published list. Songs float on and off, with only a few every taking the top spot. However, the top spot doesn’t guarantee more than a moment of recognition. Using Top 100 Data and Grammy Winners from the past 20 years, our team will analyze datasets to determine if a Grammy winner can be determined based on the Billboard Top 100. 

The datasets to be used include weekly top 100 songs from 1999 through 2018 and Grammy winners from 1999 through 2018. We will use logistic regression and machine learning to determine if winners can be predicted based on Billboard information. 

Our team selected this topic during the recent Grammy award show on March 14, 2021. The inspiration came from the randomness of the winners, as several songs beat others which our group thought to be popular. Additionally, music brings the world together, and during these times, we can all use a little more music and song. 

# Communication Protocol
Our group will communicate primarily via slack, with scheduled zoom meetings outside of class when necessary.  We have shared cell phone numbers in case of urgent questions, but will use slack for the majority of group communications

# Machine Learing Model Questions
- Which model did you choose and why?
  - We chose the logistic regression model because it is used to predict binary outcomes, and the goal of our project is to predict whether or not an artist that is on the Billboard Top 100 Chart will win a Grammy.
- How are you training your model?
  - We are training our model using a SQL database containing 15 out of the 20 years included in the original dataset.  We will then use the data for the remaining 5 years to test that model.
- What is the model's accuracy?
  - 0.8461538461538461
- How does this model work?
  - This model takes in data from our database and removes the column we wish to predict.  The model is then trained using the data, and predicts the outcomes based on the training. 

# Database Interfacing
For segment 2 of our projecct, our database interfaces with our project through a connection to our machine learning model.  An idea to improve this functionality for phase 3 of the project would be to use web scraping to add 2021 Grammy Winners to our data set. 


