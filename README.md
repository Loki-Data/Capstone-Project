__BrainStation Capstone__

Sarcasm Detection Model and Response Generator
A machine learning model that detects whether a comment is sarcastic while also producing a sarcastic response

Loki Keeler | holisticloki@gmail.com

https://www.github.com/Loki-Data | https://www.linkedin.com/in/loki-keeler/

__Inspiration__

Laughing has always seemed to be the most important thing in my life. In particular, dry sarcasm has always been my favorite form of comedy. The joy from a well placed, sarcastic comment can be infectious and produce temporary happiness with everyone around. 

Sarcasm can be difficult for even humans to pick up on at times, and it is even more difficult for Artificial Intelligence. Many Language Learning Models, such as BERT or ChatGPT, have improved their sarcasm detection over the past few years, but still is not quite at the level of human detection. 

For an LLM to excell in human conversations, it must be able to know when the human is saying something sarcastic, and also know how to place a sarcastic response every now and again. First it must be able to recognize sarcasm before producing sarcasm. Furthermore, with social media on the rise with nearly five billion users, an LLM that fully masters sarcasm can help billions create that funny post that makes them go viral. Thus, an LLM that could make people laugh with the use of sarcasm could make billions of dollars. Plus, with the incredible Reddit sarcasm dataset that came out in the last decade, this is very possible.

It is with this motivation that I plan to use the Reddit sarcasm dataset and apply it on an already functioning LLM to see if we can better detect sarcasm.


__Data Dictionary__


Label -	        Whether the comment is sarcastic (1) or not sarcastic (0). Int

Comment -	    The actual comment from Reddit that is being analyzed. Object  

Author -	    Author of the comment. Object

Subreddit -	    The category on Reddit where the comment was written. Object

Score -	        The sum of Up-votes and Down-votes. This is a way for Reddit users to approve or disapprove of                 comments. Int

Ups -	        The amount of Up-votes (approving votes) a comment received. Int

Downs -	        The amount of Down-votes (dispproving votes) a comment received. Int

Date -	        The month and year the comment was created. Object 

Created utc -   The exact second the comment was created. Object 

Parent Comment-	The original comment or posting on Reddit that our analyzed comment replied to. Object 


__Project Overview__

The project is split into a number of notebooks:

EDA 1

Data Dictionary
Loading Reddit Sarcasm Corpus Data (train-balanced-sarcasm_csv)
General EDA and understanding of data:
There are just over 1 million rows of data, half of which are labeled as sarcastic
94% of all data lies between the score value range of -20 and 20. This data provides a much more normal distribution so I continue on with this subset of the data.
Another finding was that sarcastic comments had slightly more approving up votes overall.

EDA 2

Further breakdown of data and initial attempts of logistic regression models with numeric data (not comments, yet).
All of these came out pretty poor.

Modeling 3

In this journal I have dove into NLP. I tokenized the comments and used a Count Vectorizer, then performed some logistic regression models as well as a Decision Tree Classifier paired with a pipeline and GridSearch. With this I was able to pull up the top 20 words that occur to signify sarcasm. Furthermore, the logistic model improved upon the one in the previous journal, but the Decision Tree model did not perform as well.

Modeling 4

Further testing commenced as I used a TF-IDF this time, and edited my tokenizer to allow words with capital letters. With this the Logistic Regression model increased in accuracy, precision, and recall (almost all percentages were at 70%). This was exciting, but the Decision Tree performed poorly again.

Modeling 5

(To be completed) Here we will work on our Decision Tree model

Modeling 6

(To be completed) Here we will perform a Random Forest

Modeling 7

(To be completed) Now we will attempt our Sarcasm Response Generator

