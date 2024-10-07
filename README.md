# TikTok Video Classification: Claim vs. Opinion

## Problem Statement

TikTok is a popular social media platform where users upload millions of videos daily. However, with the immense volume of content, it becomes challenging to moderate videos flagged for misleading claims. Currently, human moderators manually review these reports, which creates delays.

This project aims to automate the classification of TikTok videos into two categories: "claims" and "opinions." By doing this, TikTok can prioritize user-reported videos, allowing moderators to focus on those more likely to present harmful claims.

I developed and fine-tuned two machine learning models: **Random Forest** and **XGBoost**, and evaluated their performance using cross-validation. The objective is to determine the best model for classifying videos to ease the load on human moderators.

## Goal

To predict whether a TikTok video presents a "claim" or an "opinion." This will help TikTok prioritize videos flagged for claims, improving content moderation and efficiency on the platform.

## Project Breakdown

The project is divided into four stages using the **PACE** (Plan, Analyze, Construct, Evaluate) framework:

1. **Plan** – Understanding the problem within a business context
2. **Analyze** – Performing exploratory data analysis and visualization
3. **Construct** – Building and comparing machine learning models
4. **Evaluate** – Interpreting the model results, identifying limitations, and providing recommendations

## Plan Stage

### Business Need

TikTok users report videos that violate terms of service, and the majority of harmful videos present claims rather than opinions. A machine learning model that identifies claims would assist TikTok in directing these flagged videos for human review.

### Modeling Objective

The goal is to classify videos into "claim" or "opinion" categories using a machine learning model. The **target variable** is the `claim_status` column in the dataset, which indicates whether a video is a claim (1) or an opinion (0).

### Evaluation Metric

Since the primary goal is to minimize **false negatives** (claim videos misclassified as opinions), the evaluation metric chosen is **recall**, which measures the ability to correctly identify claim videos.

## Analyze Stage

### Data Exploration

The dataset contains various categorical, textual, and numerical features representing TikTok videos. Some important observations:
- There are 19,382 observations.
- Missing values were minimal and were dropped.
- Engagement metrics (likes, views, shares) were more strongly associated with claim videos.

### Visualizations and Trends

Key insights from the exploratory data analysis:
- Claim videos have higher engagement rates than opinion videos.
- Banned authors tend to post videos with higher engagement rates.
- The distribution of features like `likes_per_view`, `comments_per_view`, and `shares_per_view` shows higher engagement for claim videos.

### Handling Outliers

We calculated the interquartile range (IQR) to identify outliers in engagement metrics, ensuring that the model's predictions aren't biased by extreme values.

## Construct Stage

### Feature Engineering

We tokenized the text data in the `video_transcription_text` column using **CountVectorizer** to convert it into numerical features. We also created new features like `text_length` and transformed categorical variables into numerical representations for the model.

### Data Splitting

The dataset was split into **training (80%)** and **testing (20%)** sets, and the target variable `claim_status` was used to classify the videos.

### Model Building

Two models were built and compared:
- **Random Forest**
- **XGBoost**

Both models were trained using cross-validation and hyperparameter tuning, with the **Random Forest** model emerging as the champion due to its higher recall.

## Evaluate Stage

### Model Evaluation

We evaluated the models using confusion matrices, recall, precision, F1-score, and accuracy metrics. The **Random Forest** model had a nearly perfect recall, making it the ideal choice for this task.

### Key Insights

- The most predictive features were related to engagement metrics such as views, likes, shares, and downloads.
- Claim videos had significantly higher engagement rates compared to opinion videos.

## Conclusion

The **Random Forest** model performed exceptionally well in classifying TikTok videos as claims or opinions. The model’s strong performance, particularly in identifying claims, ensures that it can reliably assist moderators in prioritizing flagged videos for review.

Future improvements could include incorporating additional features, such as the number of reports a video has received, to further enhance prediction accuracy.

---
## Conect with me

[**LinkedIn**](https://www.linkedin.com/in/venkat-ramoju/)

[**Portfolio-Website**](https://venkatramoju01.github.io/MyWebsite/)

[**GitHub**](https://github.com/VenkatRamoju01/)

[**Kaggle**](https://www.kaggle.com/venkatramoju)

