# Portfolio

## Solo Python Projects

### 1. Predicting the Results of the 2025 Polish Presidential Election
`Notebook:` [Polish Election Prediction]()

`Data:` [Polish Election Data](https://github.com/alexapostol095/Projects/tree/main/polish_election_data)

### 2. Is the "Clutch Gene" Real in Baseball? Investigating the Differences in the Sabermetric-Based Predictions of High Leverage Performance versus Regular Performance
`Notebook:` [Leverage Analysis](https://nbviewer.org/github/alexapostol095/Projects/blob/main/leverage_notebook.ipynb)

`Data:` [Leverage Analysis Data](https://github.com/alexapostol095/Projects/blob/main/leverage_data.zip)

`Description:` In this notebook, I aimed to assess the extent to which variables indicative of OPS+ (On-Base Plus Slugging Plus) are also relevant in predicting tOPS+ (Player-specific OPS+ in High Leverage Situations) and sOPS+. 

### 3. A Visual Analysis of Josiah Gray's 2023 Season
`Notebook:` [Josiah Gray Analysis](https://nbviewer.org/github/alexapostol095/Projects/blob/main/josiah_analysis.ipynb)

`Description:` In this notebook, I aimed to analyze different aspects of Josiah Gray's pitching and potential improvements. I focused on attributes like release points, sequencing, pitch decisions and more. 

## Research Assistant Projects

### Reddit Classification Task

`Repository:` [Reddit Classification Task](https://github.com/alexapostol095/reddit_classification_template/tree/main)

`Description:` This task set up a general template for utilizng LLMs in the interest of Reddit post classification, part of a larger project directed by Dr. Gui Liberali and Dr. David Kusterer. In this instance, I wrote code that utilizes a local llama3 LLM model in order to classify 100 Reddit posts, 50 from the Republican subreddit and 50 from the Democrat subreddit, based on their political leanings. The LLM was tasked to score posts on a scale from 1 to 5, with lower scores corresponding to more republican posts and vice versa. 

### Video Similarity Analysis Task

`Repository:` [Video Similarity Analysis Task](https://github.com/alexapostol095/video_similarity_analysis)

`Description:` This repository contains the code and video files utilized in a project where video similarity analysis was conducted through Siamese Neural Networks and SimCLR embeddings. Computer vision was utilized by extracting frame-level embeddings meant to provide a numerical representation of the subjects/objects within the frames. The base of the frame-extraction code was written by Dr. Gui Liberali, I contributed in the area of extracting embeddings from the given frames.


## Other

### Purchase Prediction with Boosted Trees (Part of Erasmus Learning from Big Data Minor)

`Notebook:` [Purhcase Prediction Notebook](https://nbviewer.org/github/alexapostol095/Projects/blob/main/purchase_prediction.ipynb)

`Description:` This notebook employed various machine learning/analytical methods to predict the shopping tendencies of 2,000 customers across 250 different products over 90 weeks, resulting in 500,000 predictions. Feature engineering employed K-means clustering in the 2nd and 3rd dimensions and basic yet intuitive data transformation. The analysis compared the uses of Adaptive Boosting, Gradient Boosting, XG Boosting, and Random Forest learning algorithms, with the XG Boosting algorithm providing the best result. The parameters of the XGBoost model were optimized through Bayesian inference. The final model yielded a log loss of 0.0773, which was the 2nd best in the class and the 3rd best in the 5-year running history of the challenge. The project served as a challenging introduction to large prediction tasks utilizing common yet powerful algorithms.

