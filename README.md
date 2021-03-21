# From Billboard to Grammy
## Can weeks on the Billboard Top 100, peak position on the chart, gender, or time at the top spot predict a Grammy win for a song? 

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



