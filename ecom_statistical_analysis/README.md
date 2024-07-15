# Overview
This dataset is for an ecommerce clothing store, it contains 500 records of data pertaining to user’s time on website/app, yearly spend, and average session length.

# Data Cleaning
Dropped the first 3 columns (email, address, and avatar) because it provided no useful information.

# Exploratory Data Analysis (EDA)
Used the pandas describe function to quickly summarize the dataset. Discovered very insightful information such as that users spend an average of only 12.05 minutes on the app. Meanwhile they spend on average 25 minutes more on the website at 37.06 minutes.

Some more information I discovered is that the average session length between both the app and website is 33.05 minutes, most of that coming from the website. Moreover, yearly spend on the store ranges from $256.67 to $765.52 with an average spend of $499.31. The standard deviation is 79.31 meaning 68% of users spend between $420.69 and $579.31 on a yearly basis.

# Predictive Modeling with Linear Regression
I saw that there was a linear relationship between length of membership and yearly spend so I created a linear regression model to predict yearly spend for users. The first step was to train the model. Using the train test split function from scikit-learn, I split the data into 70% for training and 30% for testing.

Afterwards I fitted the model using linear regression from scikit-learn and ran the predictions. I made a scatterplot of the predictions against the actual values to visualize how accurate the model was. It was a fairly straight line with a 45 degree angle meaning it works well. Looking at the mean absolute error of 7.5416, it means the predictions are only +- $7.54 off from the actual values which is good given that yearly spend ranges from $256.67 to $765.52.

I then wanted to check the rest of the assumptions for linear regression which are normality and homoscedasticity for residuals. I used a distance plot to check for normality, the curve on the plot looked normally distributed for the most part. Then I made a residual plot, the red line was fairly straight and close to zero indicating equality of variances between the predicted data points so I determined the assumptions to be true.

# Hypothesis Testing
I wanted to test whether users who allocate a lot of time on the website spend on average more than users who don’t. The null hypothesis is that there is no significant difference in the mean yearly spend between the two groups. The alternative hypothesis is that there is a significant difference in the mean yearly spend between the two groups.

Using Q1 and Q3 as the threshold for defining users who spend a lot vs little time on the website, I calculated the mean for the two groups. I then ran a t-test to get the t-statistic and p-value. The t-stat is -0.1839 which alone looks to be insignificant. This is supported even further with a critical value of 1.965, the t-stat needs to be greater than the critical value to be considered significant. (I obtained the critical value using a significance level of 0.05 and the degrees of freedom). Additionally, the p-value is 0.8542 meaning we fail to reject the null hypothesis.

There is not enough evidence to conclude that there is a significant difference or effect between users who spend a low amount of time on the website vs. a high amount of time on the website. This makes sense given that the means are $498.89 for the low group and $500.82 for the high group. There isn’t much of a difference on how much they spend whether they use the website for a long period of time or short.

Lastly I checked the assumptions for a t-test which are normality (using a Shapiro-Wilk test) and homogeneity of variances (Levene test). The p-values for both tests were high (well above 0.05) which meant the assumptions were true and the t-test is valid.

# So What?/Recommendations
From both the exploratory data analysis and hypothesis test, I would recommend this ecommerce store to focus attention on getting users to utilize the app more. Reason #1 being that time spent on their website doesn’t correlate with more sales. Using the average yearly spend from both groups, there is only a $1.93 difference. This is a very small difference given the overall average yearly spend of $499.31. It wouldn’t make sense for the business to spend any additional effort on keeping the user on their website.

Reason #2 why I recommend the owner to focus on the app is that users spend a lot less time on it than the website, on average 25 minutes less. This is a big difference where they could be missing out on potential revenue. There are several ways to go about this, one way is to create an incentive for users to use the app. This can take many forms such as discounts, exclusive offers, free shipping, etc. This would not only attract new users, they would spend more time on the app looking at the deals. Another way to incentivize users is to create a better user interface (UI). With a better looking app, naturally users will spend more time on it and the improved user experience (UX) will lead to more sales.

After tweaking the app, the next step is to advertise these changes to let users know of the improvements. I’d recommend creating marketing campaigns and posting them to whichever social media they have the most presence on such as Facebook or Instagram. They can use prior data to target the appropriate audience and optimize engagement/increase the conversion rate to the app. This step is crucial because if no one knows about the changes, little to no progress will be made.

Furthermore, the hypothesis may seem to contradict my recommendation but let me explain. Users spend triple the amount of time on the website (37.06 minutes on average) than on the app (12.05 minutes on average). Although there isn't a significant difference in sales on the website, the app (which gets ⅓ the amount of attention) I argue would increase sales if it received attention. There is a significant amount of untapped revenue that can be made by making changes to the app.

Lastly, I’d recommend the business to also focus attention on getting users to buy a longer membership. Based on the linear regression, the positive correlation with length of membership and yearly sales suggests that the longer someone is a member with the business, the more they spend. Right now it goes up to 7 months but if they offered a yearly membership, they will see an increase in sales. I’d even suggest offering the yearly membership at a discount. The sales they miss out on by charging the regular price will be made up throughout the year because users will end up making more purchases.

Overall, I’d recommend the business to focus attention on improving the app. There is a lot of potential there and changes to be made. By offering more app exclusive deals, users will spend more time on the app and buy more clothes. Improving the user interface of the app will grab and retain the attention of the user; whether internally or hiring a front-end developer to design it better. As seen with the linear regression, the positive correlation between length of membership and yearly spend calls for offering longer memberships. With a yearly membership at a discounted price, sales will see significant growth. All in all the website is doing well as it is. Moving forward, this ecommerce business needs to refine their app in order to increase sales.
