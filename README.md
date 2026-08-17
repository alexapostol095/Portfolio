# Portfolio

## Solo Python Projects

### Alert Triage for Anti-Money Laundering: Ranking a Transaction Monitoring Queue Under Capacity Constraints
`Notebook:` [AML Alert Triage Notebook](https://github.com/alexapostol095/ibm_aml_project/blob/main/aml_portfolio.ipynb)

`Data:` [IBM Transactions for Anti Money Laundering (HI-Small)](https://www.kaggle.com/datasets/ealtman2019/ibm-transactions-for-anti-money-laundering-aml)

`Repository:` [IBM AML Project](https://github.com/alexapostol095/ibm_aml_project)

`Description:` A supervised detection study on 5.08M synthetic interbank transactions (IBM/AMLworld, Altman et al., NeurIPS 2023) in which 0.102% are labelled laundering, framed around the constraint that actually binds transaction monitoring in practice: investigator capacity rather than model accuracy. Accounts are resolved to customers via the accompanying account master — 518,581 accounts mapping to 166,207 entities at 3.12 accounts each — making counterparty structure measurable at the level a bank monitors rather than the level payments are recorded at; removing the resulting entity-level degree and volume features costs roughly 13% of average precision. The split is temporal and cut on cumulative volume rather than calendar midpoint (the file spans 18 days with a sparse tail), and every aggregate is computed from the training window alone, since deriving degree features over the full dataset before splitting leaks future behaviour into past predictions. Amounts are normalised within currency, because median payment size spans a millionfold across the 15 currencies present and a raw amount therefore encodes denomination more than magnitude. Class imbalance is handled by retaining every positive and downsampling negatives 20:1, with the resulting calibration cost stated explicitly and ranking metrics used throughout in consequence. XGBoost reaches an average precision of 0.272 against a 0.0016 base rate — a 170× lift, roughly seven times the linear baseline — but the substantive result is the capacity curve: precision is 86% in the top 50 alerts, the system finds 176 cases at 1.4 alerts per case at a capacity of 250, and even reviewing 5,000 alerts recovers under half the laundering present. Efficient triage and adequate coverage are different problems. The notebook is also explicit about where the dataset betrays its simulator: no laundering transaction in the file is cross-currency, and a single generator-assigned categorical carries 28% of model importance, so the shape of these results transfers to real payment traffic while their height does not.


### Where Fishing Vessels Go Dark: A Descriptive OSINT Study of AIS Disabling on the High Seas
`Notebook:` [AIS Going Dark Notebook](https://github.com/alexapostol095/ais_going_dark_exploration/blob/main/ais_going_dark_exploration.ipynb)

`Data:` [Global Fishing Watch — AIS Disabling Events](https://github.com/GlobalFishingWatch/AIS-disabling-high-seas)

`Repository:` [AIS Going Dark Exploration](https://github.com/alexapostol095/ais_going_dark_exploration/tree/main)

`Description:` A descriptive open-source-intelligence study of where, how, and by which fleets large fishing vessels switch off their AIS transponders on the high seas, built on 55,368 real disabling events (2017–2020) from Global Fishing Watch (Welch et al., 2022) and loaded directly from source for full reproducibility. Event start positions are clustered on the sphere with DBSCAN under a haversine metric to surface disabling hotspots, each characterized by its flag and gear *composition* rather than a single modal label; fleet behaviour is profiled by gap duration, distance from shore, and distance travelled while dark (separating loitering from transiting); and an IsolationForest scores the extreme tail of long, remote, far-travelled disappearances as an analyst triage layer. The project is deliberately descriptive and makes no claims about intent: the events are model-derived likely-intentional gaps confounded by satellite reception, and "anomalous" is treated as statistically unusual, never as evidence of wrongdoing.

### Adjusting ERA for Bequeathed Runners: Crediting Starters by Run Expectancy at Handoff
`Notebook:` [Adjusted ERA Notebook](https://github.com/alexapostol095/era_adjustment_bequeathed_runners/blob/main/adjusted_era_2025.ipynb)

`Data:` [Adjusted ERA Output](https://github.com/alexapostol095/era_adjustment_bequeathed_runners/blob/main/adjusted_era_2025.csv)

`Repository:` [Bequeathed-Runner ERA Adjustment](https://github.com/alexapostol095/era_adjustment_bequeathed_runners/tree/main)

`Description:` This project corrects a structural flaw in traditional ERA: when a starter leaves with runners on base, whether those runners score is decided by the reliever, yet the runs are charged to the starter. Using pitch-level Statcast data (via `pybaseball`) collapsed to plate-appearance level, I recompute ERA by replacing the actual downstream fate of each starter's bequeathed runners with their expected value under league-average pitching, given the base-out state at the moment of the pitching change.

### Separating Skill from Luck: A Bayesian Approach to MLB Pitcher Evaluation
`Notebook:` [MLB Bayesian Analysis](https://github.com/alexapostol095/pitching_bayesian_shrinkage/blob/main/mlb_bayesian_pitcher_model.ipynb)

`Data:` [MLB Starter Data](https://github.com/alexapostol095/pitching_bayesian_shrinkage/blob/main/fangraphs_pitching_2025.csv)

`Description:` A hierarchical Bayesian model built with JAX and NumPyro that estimates true pitcher skill from 2025 FIP data, quantifying uncertainty through partial pooling and Bayesian shrinkage.

### Forecasting Hourly Energy Demand: SARIMA vs. Prophet vs. LightGBM
`Notebook:` [Energy Demand Forecasting Notebook](https://github.com/alexapostol095/energy_demand_forecast/blob/main/timeseries_energy_forecasting.ipynb)

`Data:` [PJME Hourly Demand Data](https://github.com/alexapostol095/energy_demand_forecast/blob/main/PJME_hourly.csv)

`Repository:` [Energy Demand Forecast](https://github.com/alexapostol095/energy_demand_forecast)

`Description:` A rolling-origin backtest comparing three forecasting approaches on PJM East hourly electricity demand: SARIMA fit on daily aggregates and disaggregated to hourly resolution, Prophet fit directly on the hourly series, and LightGBM trained as independent quantile regressors on horizon-safe lag and calendar features. Beyond point accuracy (MAE/MAPE), I evaluated each model's prediction interval calibration by comparing empirical coverage against the nominal 90% target across six backtest folds. SARIMA, despite being the simplest approach, produced both the best mean accuracy and the most reliably calibrated intervals, while LightGBM's quantile intervals swung from severely under-covered to well-calibrated depending on the fold.

### Analyzing U.S. Defense Contract Spending on Ground Vehicle Programs (2016–2020)
`Notebook:` [Ground Vehicle Analysis](https://github.com/alexapostol095/ground_vehicle_exploration/blob/main/ground_vehicles.ipynb)

`Data:` [Ground Vehicle Data](https://github.com/alexapostol095/ground_vehicle_exploration/blob/main/ground_vehicles.xlsx)

`Write-up:` [Ground Vehicle Write-up](https://github.com/alexapostol095/ground_vehicle_exploration/blob/main/Alexander%20Apostol%20Ground%20Vehicle%20Exploration%20.pdf)

`Description:` This project explores U.S. federal contracting data related to ground vehicle programs to uncover trends in military procurement, vendor concentration, and program-level spending over time.


### Predicting the Results of the 2025 Polish Presidential Election
`Notebook:` [Polish Election Prediction](https://github.com/alexapostol095/Projects/blob/main/polish_election_prediction_notebook.ipynb)

`Data:` [Polish Election Data](https://github.com/alexapostol095/Projects/tree/main/polish_election_data)

`Description:` In this notebook, I adapt a previously used election-prediction technique in the context of the 2025 Polish Presidential Election. My prediction ended up missing by a comfortable margin, unfortunately, but I personally gained a lot of useful experience regarding data cleaning and aggregation. 


### Is the "Clutch Gene" Real in Baseball? Investigating the Differences in the Sabermetric-Based Predictions of High Leverage Performance versus Regular Performance
`Notebook:` [Leverage Analysis](https://github.com/alexapostol095/Projects/blob/main/leverage_notebook.ipynb)

`Data:` [Leverage Analysis Data](https://github.com/alexapostol095/Projects/blob/main/leverage_data.zip)

`Description:` In this notebook, I aimed to assess the extent to which variables indicative of OPS+ (On-Base Plus Slugging Plus) are also relevant in predicting tOPS+ (Player-specific OPS+ in High Leverage Situations) and sOPS+. 

### A Visual Analysis of Josiah Gray's 2023 Season
`Notebook:` [Josiah Gray Analysis](https://github.com/alexapostol095/Projects/blob/main/josiah_analysis.ipynb)

`Description:` In this notebook, I aimed to analyze different aspects of Josiah Gray's pitching and potential improvements. I focused on attributes like release points, sequencing, pitch decisions and more. 

## Research Assistant Projects

### Reddit Classification Task

`Repository:` [Reddit Classification Task](https://github.com/alexapostol095/reddit_classification_template/tree/main)

`Description:` This task set up a general template for utilizng LLMs in the interest of Reddit post classification, part of a larger project directed by Dr. Gui Liberali and Dr. David Kusterer. In this instance, I wrote code that utilizes a local llama3 LLM model in order to classify 100 Reddit posts, 50 from the Republican subreddit and 50 from the Democrat subreddit, based on their political leanings. The LLM was tasked to score posts on a scale from 1 to 5, with lower scores corresponding to more republican posts and vice versa. 

### Video Similarity Analysis Task

`Repository:` [Video Similarity Analysis Task](https://github.com/alexapostol095/video_similarity_analysis)

`Description:` This repository contains the code and video files utilized in a project where video similarity analysis was conducted through Siamese Neural Networks and SimCLR embeddings. Computer vision was utilized by extracting frame-level embeddings meant to provide a numerical representation of the subjects/objects within the frames. The base of the frame-extraction code was written by Dr. Gui Liberali, I contributed in the area of extracting embeddings from the given frames.


## Other

### Master's Thesis: Enhancing Price Sensitivity Models with Network Analysis and Clustering for Key Value Item Identification

`Repository:` [Master's Thesis](https://github.com/alexapostol095/master_thesis)


### Purchase Prediction with Boosted Trees (Part of Erasmus Learning from Big Data Minor)

`Notebook:` [Purhcase Prediction Notebook](https://nbviewer.org/github/alexapostol095/Projects/blob/main/purchase_prediction.ipynb)

`Description:` This notebook employed various machine learning/analytical methods to predict the shopping tendencies of 2,000 customers across 250 different products over 90 weeks, resulting in 500,000 predictions. Feature engineering employed K-means clustering in the 2nd and 3rd dimensions and basic yet intuitive data transformation. The analysis compared the uses of Adaptive Boosting, Gradient Boosting, XG Boosting, and Random Forest learning algorithms, with the XG Boosting algorithm providing the best result. The parameters of the XGBoost model were optimized through Bayesian inference. The final model yielded a log loss of 0.0773, which was the 2nd best in the class and the 3rd best in the 5-year running history of the challenge. The project served as a challenging introduction to large prediction tasks utilizing common yet powerful algorithms.
