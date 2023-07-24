# Viewer-Engagement-Prediction-Model


Leveraging ML to predict whether **viewer engagement** is above **threshold (30%)** measured by percentage of video elapsed using a range of features relating to video context and quality (**title length, document entropy/topic diversity, recency/freshness, transcript simplicity/easiness, stopword frequency, speaker pace/speed, silence percentage**). 

- Available data split into **training** and **validation sets** to **tune hyperparameters** and run metrics on **model performance** before use on test data set via Coursera autograder
- **Grid-search cross validation** performed to **optimize hyperparameters** (**maximum depth, maximum features, number of trees**)for ensemble model - **Random Forest Classifier** (**Scikit-learn**)
- Model output is in form of predicted **probability of engagement**
- Model performance on unseen test data in autograder achieved **ROC-curve AUC** > **0.90**


## About the prediction problem

One critical property of a video is engagement: how interesting or "engaging" it is for viewers, so that they decide to keep watching. Engagement is critical for learning, whether the instruction is coming from a video or any other source. There are many ways to define engagement with video, but one common approach is to estimate it by measuring how much of the video a user watches. If the video is not interesting and does not engage a viewer, they will typically abandon it quickly, e.g. only watch 5 or 10% of the total. 

A first step towards providing the best-matching educational content is to understand which features of educational material make it engaging for learners in general. This is where predictive modeling can be applied, via supervised machine learning. For this assignment, the task is to predict how engaging an educational video is likely to be for viewers, based on a set of features extracted from the video's transcript, audio track, hosting site, and other sources.


Rational for prediction problem:

* It combines a variety of features derived from a rich set of resources connected to the original data
* The manageable dataset size means the dataset and supervised models for it can be easily explored on a single device without the need for a computing cluster
* Predicting popularity or engagement for a media item, especially combined with understanding which features contribute to its success with viewers, is a simple  but also practical representative application of machine learning in a number of business and educational sectors.


Data Source:

The training and test datasets of educational video features are from the VLE Dataset assembled by researcher Sahan Bulathwela at University College London.
https://github.com/sahanbull/VLE-Dataset


Features:

    title_word_count - the number of words in the title of the video.
    
    document_entropy - a score indicating how varied the topics are covered in the video, based on the transcript. Videos with smaller entropy scores will tend to be more cohesive and more focused on a single topic.
    
    freshness - The number of days elapsed between 01/01/1970 and the lecture published date. Videos that are more recent will have higher freshness values.
    
    easiness - A text difficulty measure applied to the transcript. A lower score indicates more complex language used by the presenter.
    
    fraction_stopword_presence - A stopword is a very common word like 'the' or 'and'. This feature computes the fraction of all words that are stopwords in the video lecture transcript.
    
    speaker_speed - The average speaking rate in words per minute of the presenter in the video.
    
    silent_period_rate - The fraction of time in the lecture video that is silence (no speaking).