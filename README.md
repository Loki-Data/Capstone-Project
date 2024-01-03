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

Capstone 1

Data Dictionary
Loading Reddit Sarcasm Corpus Data (train-balanced-sarcasm_csv)
General EDA and understanding of data:
There are just over 1 million rows of data, half of which are labeled as sarcastic
94% of all data lies between the score value range of -20 and 20. This data provides a much more normal distribution so I continue on with this subset of the data.
Another finding was that sarcastic comments had slightly more approving up votes overall.

Capstone 2

Initial attempts of logistic regression models.
All of these came out pretty bad. I will have to play around with different models to get desirable results.

Capstone 3

(To be completed)
Here I will dive into Text classifiers, sentence embeddings, N-grams, and possibly other regression models.
Hopefully with this I can train a model to detect sarcasm very well.

Capstone 4

(To be completed)
Applying regression models and classifiers on top of an existing LLM (BERT or ChatGPT 3.0)

