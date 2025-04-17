# Email Marketing Campaign Analysis & Optimization using Machine Learning

## 📌 Business Problem

Despite email marketing being one of the most cost-effective channels for customer engagement, the marketing team at an e-commerce platform is facing a critical challenge: **low click-through rates (CTR)** from their campaigns. While emails are being delivered and opened, only a small fraction of users are clicking the links within—limiting traffic to the site and reducing potential conversions.

The core business problem is:  
> **"How can we identify and prioritize the users most likely to engage (click) with marketing emails, in order to maximize campaign effectiveness and drive higher ROI?"**

Solving this allows the company to:
- Target only high-potential users, improving CTR and customer engagement
- Reduce customer fatigue by avoiding irrelevant emails
- Optimize resource allocation across campaigns
- Personalize future outreach efforts more effectively

Using machine learning, we aim to build a predictive model that helps the marketing team identify the top-performing user segments, enabling **data-driven targeting strategies** that significantly outperform random selection.


## 1. Campaign Performance Metrics

- Open Rate: 10.39%
- Click-Through Rate (CTR): 2.12% (random baseline)
- Click-to-Open Rate (CTOR): 20.38%

## 2. Predictive Model Development

I built several machine learning models to predict which users are most likely to click on email links:
- Logistic Regression (baseline)
- Random Forest
- Gradient Boosting

The best performing model was **Gradient Boosting**, with an Accuracy of **0.9786** & AUC-ROC score of **0.7442**. With **Best Hyperparameters** : {'learning_rate': 0.1, 'max_depth': 3, 'n_estimators': 100}

Key factors influencing click behavior:
1. Short email has high open and click rate
2. personalized email has high open and click rate as compared to generic email
3. Morning (6-12) has high open and click rate, followed by Afternoon (12-18)
4. Open & Click rate of US and UK is thrice of France and Spain
5. Open & Click rate is high if user has purchased previously

## 3. Expected Improvement and Testing Approach

By targeting the top **50%** of users identified by our model, we could achieve a CTR of **3.6%**, representing a **70% improvement** over the random approach.

To validate this improvement, I recommend:
- A/B testing with **20,000 users** in each group
- Sending emails randomly to the **control group**
- Using the model to prioritize users in the **test group**
- Measuring lift and conducting statistical significance testing (e.g., chi-squared or t-test)

## 4. Interesting Patterns by User Segments

Several notable patterns emerged from our analysis:

1. **Personalization Effect:** Emails with dynamic content based on user preferences saw up to 2x higher CTR.
2. **Timing Patterns:** CTR was highest when emails were sent between **8–10 AM** on **weekdays**.
3. **Content Length Impact:** Short, focused emails with one CTA performed better than longer newsletters.
4. **Purchase History Influence:** Users who made a purchase within the last 30 days were 2.5x more likely to click.

## 5. Recommendations

Based on our analysis, I recommend:

1. Shift from mass emailing to **model-driven targeted campaigns**.
2. **Prioritize top 10–30% users** for high-value campaigns to maximize ROI.
3. Personalize content using **purchase history and product affinity**.
4. Optimize send times based on **user time zones and peak activity windows**.
5. Continuously retrain the model every month using **fresh behavioral data**.

## 6. Next Steps

To further improve email campaign performance:

1. Deploy the predictive model as a service to power campaign segmentation.
2. Launch A/B tests comparing model-based targeting vs. current strategy.
3. Explore deeper personalization using **collaborative filtering or embeddings**.
