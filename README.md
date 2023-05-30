![image](https://github.com/ezman1105/Data-Scientist-Project-InvestigationOfSeattleAirbnbOpenData/blob/main/pexels-info.jpeg)

# Project - Investigation of Seattle Airbnb Open Data
## by Chih-Chuan Ma


## Motivation

> Airbnb is one of the top resources to find a place to stay when I travel, and it is a unique and personalized resource for guests and travelers. Multiple types of properties in various regions can be selected, and travelers could look for a stay based on their requests. The datasets, as listed below, describe the listing activities of homestays, price and availability on days, and detail comments from reviewers in Airbnb of Seattle. 

> a. Listings, including full descriptions and average review score 
> b. Reviews, including unique id for each reviewer and detailed comments 
> c. Calendar, including listing id and the price and availability for that day 

> In this project, factors impacting price of homestay is analyzed and filtration of types of properties that have the better value of money will be discussed based on my personal preference. Score of reviews are revised as weighted average score according to the personal points of view for ratings. Besides, as a stranger to Seattle, I am curious which region and what season would be more expensive (or relatively cheap) to hire a place. Also, whether the score of review, amenities that I required, or any other factors would impact the price of stay? Thus, the relationship among region-related, review-related, and price of homestay would be analyzed.

## Library Used
> In the analysis, libraries including numpy, pandas, and matplotlib are used. Besides, seaborn is imported for visualization. Packages of sklearn are also introduced since functions such as train_test_split, Standard Scaler will be applied. In the project, model of linear regression is utilized and to achieve better performance, linear regression model is combined with transformed target regressor. Finally, the output is evaluated by value of r-squared and thus re_score is imported.
> For the detailed, please refer to the "requirements.txt"

## Data Wraggling 

> 1. Removal of unnecessary columns: 
     a. Columns with url path
     b. Identifiers such as 'id','host_id', and 'scrape_id'
     c. 'name','summary','space','description','zipcode','host_name','host_location','host_about','host_verifications' are not required in the analysis
     d. Columns with identical content such as 'state', 'market', 'country code', 'country', 'names of jurisdiction', 'smart_location', 'experiences_offered ,and 'city'
> 2. Convert 'price' from string to float
> 3. Remove clolumns with more than 20% of missing values
> 4. In both df_listings & df_reviews, columns with missing values below 20%, rows with missing values should be removed
> 5. In df_calandar, remove rows with missing prices  
> 6. Create a new column to store whether the hosts equipt the required amenities (Free Parking on Premises, Wireless Internet and Kitchen)  
> 7. Create a new column showing the weighted average rating score. The weighted is based on personal preference as below.
     a. review_scores_rating * 100%
     b. review_scores_accuracy * 100%
     c. review_scores_cleanliness * 120%
     d. review_scores_checkin * 80%
     e. review_scores_communication * 80%
     f. review_scores_location * 50%
     g. review_scores_value * 120%

## Overview of data
> The original datasets contain information of price from January of 2016 to January of 2017 (df_calendear) and listings with hosts with 92 columns and 3818 rows (df_listings). 

> The wrangled dataset of listings has 48 variables with 2555 rows. As many as data is trying to be reserved, but columns over one fifth of missing values, and rows with NaN are removed to avoid a biased result if the average value is inserted. 

> Airbnb is one of the top resources to find a place to stay when traveling. Among numerous luxurious ameninities, all I care is a convenient free parking space, speedy WIFI, and a kitchen. In addition, since a car will be hired when traveling in the USA, the location of the stay is not really important. However, the feedback of cleanliness and value of money from others is crucial for me. As a result, new columns including 'review_scores_weighted' and 'required_amenities' are created to help me to analyze the places I would probably look for.

## Summary of Findings

> The average cost of stay in Airbnb Seattle ranges from USD80 to USD120, and most properties locate in regions of Capital Hill, Ballard, Belltown, Minor and Queen Anne. The cost of accomodation varies a lot by different seasons. Obviously, the trend of price of stay increased from January and achieved yearly high in Summer, especially from July unitl the end of August. The gap of price difference could be more than 20% based on the data in 2016. Furthermore, the hosts in Airbnb Sealttle are very efficient. Most of the time, feedback from hosts could be received within couple of hours, and questions from customers are rarely ignored.

> The criteria of further selection is based on my personal preference since I do care about ratings from other travellers, especially the comments of cleaningness and whether is it easy to park a car and kitchen is equiped. As a result, it's efficient to observe regions with higher weighted scores as higher priority, and places with more negative comments can ben avoided. Taking whether the host of property is verified, number of reviews, and price per night into consideration, Yesler Terrace has the highest average cost of a stay with the required amenities, at more than USD150. Other places meeting my criteria include High Point, Arbor Hieghts, Riverview, Harrison/Denny-Blaine , and Licton Springs could be my target areas since under the identical conditions, the stay can be cheaper, ranging from USD50 to USD100.

> Price of stay becomes more expensive while more accomodates, bedrooms, beds, bathrooms and guests are requested. Places with greater numbers of reviews are also more expensive; however, properties with more monthly reviews would be cheaper. The linear regression model is based on a revised dataset combining with numerical and categorical variables. while the training section is scaled, the r-squared of the prediction is 68.38% which is higher than 63.4% of training section.

> In summary, although the quotation and other variabels in Airbnb of Seattle may differ nowadays, the analysis demonstrates an overview of Airbnb in Seattle, including the speed of host respond, the trend of homestays price, price of regions with better comments of quality, and factors impacting cost of stay. The investigation provides a good practiece that efficiently filter places locate in high quality regions with relatively reasonable budget, and avoid costly rooms with negative experience.

> The results of the analysis is written in my personal blog. Please feel free to refer to the link below.
> https://medium.com/@johnma19821105/investigation-of-seattle-airbnb-open-data-4f598086ab4c

## Key Insights for Presentation

> From the investigaton, I would like to present insights as below: 
> a. Capital Hill, Ballard, Belltown, Minor and Queen Anne are the top 5 regions where most of homestays are provided. In addition, house and apartment are the majority property type in Seattle.

> b. As a family of four that cares about the quality of stay, regions such as Hight Point, Arbor Heights, Riverview, Harrison/Denny-Blaine and Licton Sprints should be investigated as higher priority due to the best average weighted reviews scores. On the contrary, areas including View Ridge, Pinehurst and University District should be avoided since the feedback from travelers is quite negative and the review scores are much lower than the average.

> c. Summer is the most busiest season in Seattle since the price of stay is the most expensive, compared to the price is relatively cheap in January.

> d. Among regions with best average review scores, Yesler Terrace has the highest average cost of a stay with the required amenities, at more than USD150. Other places, on the other hand, ave the lower average price, ranging from USD50 and USD100. In other words, compared to Yesler Terrace travelers could spend 50% less if they stay in High Point, Arbor Hieghts, Riverview, Harrison/Denny-Blaine , or Licton Springs.

## Acknowledgment
[Insertion of pics in readme.md, by Steph Yang](https://medium.com/@stephyang/%E5%9C%A8github%E7%9A%84readme-md%E5%8A%A0%E5%85%A5%E5%9C%96%E7%89%87%E5%8F%8Agif%E7%9A%84%E6%96%B9%E6%B3%95-7282a4a63141)
[Pexels -- Free resource to download pictures without license](https://www.pexels.com/zh-tw/search/information/)
[How to Create Requirements.txt Python?](https://www.scaler.com/topics/how-to-create-requirements-txt-python/)
[Linear Regression in Python](https://realpython.com/linear-regression-in-python/)
