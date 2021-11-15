```
├── README.md                           <- The top-level README for reviewers of this project
├── JupyterScripts/project.ipynb      <- Narrative documentation of analysis in Jupyter notebook
├── non_technical.pdf                    <- PDF version of project presentation
└── images                              <- Images generated from the project.ipynb code
```
![cloud](./images/cloud.png)
# Classification of short political articles collected from several news/opinions websites 
# ** By Y. Kostrov
***

# Overview
 In this project, I create a model that will classify political articles into three categories consisting
  "left", "right", and "center".

 During the analysis:
 1. I perform exploratory data analysis.
 2. I prepare the data for training.
 3. I will split the data into training and testing sets.
 4. I explore three different embeddings for text: Counting(Count Vectorizing), Term Frequency–Inverse Document Frequency (TFIDF), and Doc2Vec.
 5. I build a Naive Base model, Logistic Regression, Random Forest, and Deep Learing models.
 6. I compare the results of the models to choose the better model based on the metric described below and retrain it on the whole data set.

 # Business Problem
This project is centered around understanding the political view of the short article that we can find on the internet. It is, often, very hard to decide which political inclination the article has. The reader can take the text and use the model that comes out of this project to confirm the understanding of the political notion that the user has after reading with the prediction of the model.

# Metrics for Assessment
1. The primary metric for this project will be accuracy. Accuracy is the number of correct predictions divided by total number of predictions. Since we have a pretty close number of articles in three different classes, accuracy should serve well as a primary metric. I will also look at the confusion matrix to keep an eye on the False Negatives and False Positives counts.
2. Based on part 1., I use precision and recall as two additional metrics. Recall is defined as a number of true positives divided by the number of total atual positives. Precision is defined as a number of true positives divided by the total number predicted as positives.

# Data Description.
The data for this project was collected by me from the following websites: www.freebeacon.com, www.americanthinker.com, www.huffpost.com, www.slate.com, news.gallup.com, www.cbsnews.com. I put the articles into three category based on the political view of the hosting website. The categories are "left", "center", and "right". The data file has only two columns: "article" and "label".
Please see the ![Crawler](https://github.com/ekostrov/CapstoneProject/blob/main/Crawler.ipynb)
for the data collection process.
# Modeling 
I have used CountVectorizer with three models: Naive Bayes, Support Vector Machines, and Random Forest. Then, I have added TFIDF and used the same three models as above, to see if the performance would imporve. Indeed, I have gotten better results with TFIDF. I have implemented Doc2Vec embedding but it didn't do that well. Final attempt was to use deep learning with LSTM model. It did almost as well as SVM model with TFIDF but tiny bit worst.
# Conclusion
 I used the Support Vector Machines model for the final training. We have perfect scores in our final training which is a bit surprising. The trained model might not scale well on the new data since it might be overfitted.

 # Business Decision
I suggest to use Support Vector Machines model for the prediction of the political inclanation of the article. It can help internet users who are not sure about the flavor of the political news to verify what kind of an article they are reading. I have to add, that collecting more data would improve the performance of the model.

# Ways to improve the model.
* Collecting more data from different websites would make the model more robust and scalable.
* Building more advanced deep learning model model with stacked LSTM layers.
* Use XGBosst classifier.


# Please review my full work in [Jupyter Notebook](https://github.com/ekostrov/xray_binary_classification/blob/main/JupyterScripts/submission.ipynb) or in the [non technical presentation](non_technical.pdf)

For any additional questions, please contact Yevgeniy (Gene) Kostrov at ekostrov@yahoo.com
