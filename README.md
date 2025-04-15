# Quantacus_ML_CaseStudy

# Overview
This project aims to optimize marketing email campaigns for an e-commerce company using Machine Learning. The marketing team wants to increase user engagement by identifying factors that influence email openings and link clicks. This project analyzes past campaign data to predict user behavior, derive actionable insights, and help improve future campaigns.

# Dataset Description
Three key datasets are used in this analysis:

1. email_table
Details of emails sent to users, including:

email_id: Unique identifier

email_text: Version type (short or long)

email_version: Type of greeting (generic or personalized)

hour: Local time when the email was sent

weekday: Day of the week the email was sent

user_country: Country of the recipient

user_past_purchases: Number of past purchases by the user

2. email_opened_table
Records email_ids of emails that were opened

3. link_clicked_table
Records email_ids of emails where the embedded link was clicked


# ML objectives

Goal 1: Predict whether an email will be opened or not

Goal 2: Predict whether a user will click the link in the email

# Methodology

Data Merging: Combined all three datasets using email_id

Exploratory Data Analysis (EDA):

Conversion funnel: Sent → Opened → Clicked

Impact of:

Email type (text/version)

Sending time and weekday

User’s past purchases

Geographical differences

Feature Engineering:

Converted categorical variables into dummy/label encoded format

Created is_opened and is_clicked binary flags

Modeling:

Applied multiple ML models like Logistic Regression, Random Forest, and XGBoost

Used train-test split and cross-validation

Performance evaluated using accuracy, precision, recall, F1 score

Explainability:

Feature importance was analyzed to identify top drivers for open and click rates.

# Key Insights

Personalized emails consistently perform better than generic ones

Short text format yields higher click-through rates

Emails sent during working hours (9AM–5PM) had higher engagement

Past purchasers are significantly more likely to click on emails

Day of the week had a marginal impact; Monday and Tuesday saw slightly higher engagement

Country-based differences exist in engagement, indicating potential for localization strategies

# Answer to questions

 Q1: What percentage of users opened the email and what percentage clicked on the link within the email?
Answer: Yes, the notebook includes a conversion funnel analysis that calculates:

 Open Rate = (# of emails opened) / (total emails sent)

 Click Rate = (# of emails clicked) / (total emails sent)

These percentages are visualized and also printed, helping understand campaign engagement.
----------------------------------------------------------------------------------------------
 Q2: The VP of marketing thinks it's stupid to send emails randomly. Can we build a model to optimize future sends to maximize clicks?
Answer: Absolutely. The notebook builds two ML classification models:

 One to predict email opens

 Another to predict link clicks

Features used include:

Email type (short/long)

Version (personalized/generic)

Time & day sent

User country

Past purchases

These models help prioritize sending emails to users most likely to engage, instead of random sending.
----------------------------------------------------------------------------------------------
 Q3: By how much would the model improve click-through rate (CTR)? How would you test that?
Answer: The notebook includes model performance metrics and simulates predictions to:

Identify top users most likely to click

Compare predicted clickers vs actual clickers

The README mentions this under:

"Generated actionable recommendations for marketing team to improve future campaigns."

To test improvement:

You could run an A/B test:

Group A: Receives emails chosen randomly

Group B: Receives emails using the model’s targeting

Compare CTR between the two

You might see a measurable lift in CTR, e.g., from 9% → 12%, based on your model’s precision.
-----------------------------------------------------------------------------------------------
Q4: Did you find any interesting patterns across user segments?
Answer: Yes, summarized in the " Key Insights" section of the README:

Personalized emails boost both open and click rates

Shorter emails perform better

Emails during working hours increase engagement

Users with past purchases are more likely to click

Country-based differences suggest localized strategies

These patterns help refine user segmentation for better-targeted campaigns.
-------------------------------------------------------------------------------------------------
