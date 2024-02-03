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

For this model we used the same tokenizer and TF IDF vectorizer on my comments, but used Random Forests modeling. At first, the model was overfitting and providing accuracies of about 64%. I then looked into the confusion matrix of this model and added hyperparameters. With this I was able to reduce the overfitting, but not completely get rid of it. Also, I wasn't able to increase the accuracy of this model. This was interesting because this lower than the score of my logisitic regression model in the previous notebook.

Modeling 6

For this model I used a BERT (Bidirectional Encoder Representations from Transformers) from HuggingFace. This is a powerful transformer than specializes in Natural Language Processing. I added no parameters to this, fed in the comments from my dataset and let it run. Amazingly, this beast produced 94% scores across the board (accuracy, recall, precision, and F1 scores) on the test set! Without any fine tuning, this model beat all my other fine tuned models by 25%. 

Detector 7

Here I attempt to create a sarcasm detector with my best finely tuned model (not the BERT), which was a logistic regression model with a TF IDF vecorizer and a specialized tokenizer. I create the function and put it to practice. Outstanding news is that it works! It as able to detect sarcasm in most instances. Furthermore, for the instances it got incorrect, if I added just one word, such as "totally", it was able to detect the sarcasm. This highlighted some of the feature importance from this model.
 

__Conclusion & Next Steps__

I was able to create many models different Logisitic Regression, Decision Tree, and Random Forest models with different tokenizers and different vectorizers. To my surprise, a logisitic regression model (69% accuracy) with a TF IDF vectorizer performerd better than my finely tuned Random Forest models. This primarily had to do with the feature importance my vectorizer created. Then, after tuning all my models I applied a BERT from HuggingFace which performed with a 94% accuracy, absolutely crushing my other models. This showed despite my best efforts, I came no where near close to the transformers currently available to the public. 

That being said, I was able to create a function for a sarcasm detector with my best performing logisitic regression model. This function was overall successful! And when it wasn't successful, I was able to tweak the sentence with just a word or two for the function to pick up on the sarcasm.

Next steps include diving into the context of the sentence, thus the parent comment to the comment, or possibily the charactistics of the user stating the comment, to see if we can better detect sarcasm this way. Futhermore, I would like to create a model that can also generate a sarcastic response after detecting sarcasm.