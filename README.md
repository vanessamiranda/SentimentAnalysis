# Unlocking Business Insights: Harnessing SentimentAnalysis on Real-World Data for Informed Decision-Making

This report delves into sentiment analysis of Yelp reviews focusing on Burger Busters (a real company with a factitious name to protect its anonymity) vs. other competing burger joints. By employing data analysis, visualisation techniques, sentiment categorisation, comparison studies, hypothesis testing and identification of factors this study aims to reveal valuable insights. The findings uncover variations in sentiment distribution, a lack of negative sentiment representation and the influence of factors on star ratings. These insights underscore the significance of customer experience in shaping reviews. Provide strategies for Burger Busters to improve their ratings and enhance customer satisfaction.

## Text Preprocessing
1.  Natural Language Toolkit (NLTK) is applied to removal of stopword
2.  Text Cleaning and Normalization

##  Exploratory Data Analysis
### Finding 1: Star Ratings Distribution
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/d71937b7-aaae-4151-b03d-19a6d349de8f)
1. Ratings of 1, 2 and 3 stars are less prevalent. This indicates that a smaller proportion of reviews convey negative sentiments.
2. Implications for Sentiment Analysis: The dominance of 5 star ratings implies that the majority of reviews are positive or highly favorable, in nature.

To validate the accuracy of the sentiment categorization results, it was employed the VADER sentiment categorization method as seen below 
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/ed955b4d-60c1-4ef3-9e98-264f79941832)

### Finding 2: Burger Busters vs. All Burger Joint Reviews 
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/4c916a29-59a8-4fe2-a831-c18c7b67fd2e)
The results showed in Figure 3 that 43.97% of the reviews for Burger Busters had a positive sentiment, which is in stark contrast to the much higher positive sentiment rate of 81.58% found in all the other burger joints. This conspicuous distinction suggests a potential issue in the sentiment distribution of Burger Busters' review

### Finding 3: Entire Database: Sentiment Score vs. Star Ratings Matrix by Category
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/789cf16e-5441-4b6d-9672-d4f0eaf28c24)

Based on the above graph, it is evident that reviews spanning each category exhibit a diverse distribution across the sentiment score spectrum (-1 to 1) and the entire range of star ratings (1 to 5 stars). The following observations were made:
1. Positive Correlation: All three categories show a positive correlation, as indicated by the upward slope of the regression lines. This suggests that higher sentiment scores are generally associated with higher star ratings across the board for each category.
2.  dispersion of data points reveals that most reviews have sentiment scores above zero, indicating a prevalence of positive sentiment expressed in the dataset.
3. There is a concentration of data points at the higher end of the sentiment score scale, especially close to 1.0, which likely represents a large number of very positive reviews.
There are outliers, especially in the Service category, where some reviews have high sentiment scores but low star ratings. This incongruence hints at a potential disparity between the sentiment conveyed in the textual content and the overall star rating assigned by the reviewer.

### Finding 4: Burger Busters vs All Other Burger Joints - Sentiment Scores by Topics Result
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/d6c0347f-c90c-4e6b-80e9-3a7e0335ec7a)

As seen above, that there is potential for Burger Busters to enhance their sentiment scores in these aspects when compared to other players in the burger joint industry:
1. Food: Burger Busters: -0.0316 vs. Other Burger Joints: 0.2143.  Analysis: On average, reviews related to the food at Burger Busters are more negative compared to other burger joints
2. Service: Burger Busters: -0.0391 vs Other Burger Joints: 0.1901. Analysis: The service at Burger Busters is viewed less favorably than at other burger joints.
3. Ambience/Environment: Burger Busters: -0.0323 vs  Other Burger Joints: 0.2011 Analysis: The environment at Burger Busters seems to be less appealing to customers compared to other burger places.

## Deep Dive into the Sentiment Analysis Findings
### Finding 1
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/67e14ebd-3f31-44ed-bec5-77d049e06c4d)
It was found that there were few positive reviews linked to low star ratings, particularly ratings of 1 and 2 stars indicating a significant level of dissatisfaction, among these customers. As a result, a strategic decision to stop using VADER and instead used 1 and 2 star ratings as proxies of sentiments since they are associated with dissatisfaction and negative experiences.

### Finding 2
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/49bca7a2-fbbc-4343-bd49-3f4f53ae7b95)
Hypothesis testing above further validated  initial finding of terminating the use of VADER categorization. The analysis focused on reviews associated with Burger Busters  and explored the presence of positive sentiment indicated by predefined positive keywords. The results reveal that out of the negative reviews for Burger Busters, 570 reviews contained positive keywords. This represents approximately 38.57% of negative reviews for Burger Busters  expressing positive sentiment, which suggests a substantial presence of positive language even in reviews with lower star ratings.

### Finding 3
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/fe6c2d30-a83d-44e0-99dd-65e332241ac3)
Based on Hypothesis Testing Results: Keywords Analysis Entire Database Reviews, it was observed that 32,910 reviews contained positive keywords, accounting for approximately 62.22% of negative reviews expressing positive sentiment. The Z-test statistic of -119.82 with an associated p-value of 0.0 indicates a highly statistically significant difference in proportions. This suggests that the observed proportion of negative reviews containing positive keywords is significantly different from the overall proportion of negative reviews with positive keywords in the dataset.  The extremely low p-value of 0.0 further supports the rejection of the null hypothesis, suggesting a substantial difference in the presence of positive sentiment in negative reviews for Burger Busters compared to the dataset as a whole.

### Finding 4
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/608dcc9b-2b0c-4023-b967-a01c512e989f)
The sample findings from the analysis of Burger Busters reviews with low star ratings (1 and 2 stars) and positive sentiment scores provide additional insights that reaffirm the decision to use star ratings as proxies for sentiments, moving away from VADER sentiment analysis. The recognition of sarcasm underscores the limitations of sentiment analysis tools like VADER, which may struggle to capture nuanced expressions or tone such as irony or sarcasm. 

### Finding 5 
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/aa32eaaa-e9bb-4655-a046-fac854964cb0)
In examination of the star ratings distribution above, a discernible pattern emerged. Burger Busters accounted for only 10% of all 5-star ratings, a proportion significantly below the average of 37% observed among other burger establishments.

### Finding 6
![image](https://github.com/vanessamiranda/SentimentAnalysis/assets/52948453/b7b02110-3363-4fb4-b84f-238e5f016672)
As seen above, we found that the feature 'food_count' has a coefficient of 0.0359, which means that positive comments about the food mentioned in reviews are associated with higher predicted ratings. On the other hand 'service_count' has a negative coefficient of 0.1283 indicating that negative comments about the service in reviews are linked to lower predicted ratings. As for 'ambience_count' it has a coefficient of 0.0353 suggesting that an increase in ambience related terms used in reviews is slightly associated with higher anticipated star ratings.

Recommendation 
Customers have expressed concerns regarding service quality and waiting times. To address this Burger Busters should focus on optimizing service efficiency and minimizing wait times. This can be achieved by implementing order management systems conducting staff training programs that emphasize attentiveness and responsiveness. While the presence of ordering apps is noted, a continuous refinement of these technological solutions can contribute to sustained customer satisfaction improvements.

Recommendation:
Enhance customer service skills it is recommended to introduce staff training initiatives that prioritize attentiveness and responsiveness. Encourage staff to proactively engage with customers, ensuring their needs are met promptly. Regularly update and optimize the ordering apps to ensure a seamless and user-friendly experience. Leverage customer feedback received through the app to identify areas for improvement. Implement features such as personalized recommendations and promotions to enhance the overall ordering experience. Enhance a customer loyalty program within the ordering app. Incorporate gamification elements, personalized rewards, and exclusive offers to incentivize repeat business and increase overall customer satisfaction.






 










