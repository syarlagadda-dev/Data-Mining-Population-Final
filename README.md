README

-----City Lifestyle Segmentation and Happiness Analysis-----

In this project, we explore how different lifestyle factors in cities relate to overall happiness. Using the public dataset from Kaggle “City Lifestyle Segmentation Dataset”, we use seven core features; income, rent, internet access, air pollution, density, transit, and green space. We segment the cities into three distinct lifestyle clusters; High-Density Urban Cities, High-Income Modern Cities, and Low-Income Developing Cities. 

Once the data is clustered, we examine how key variables like income, rent, internet access, air pollution, and public transport are associated with happiness. We do this by running linear regression models to see how each variable influences happiness within each group.

Our goal is to compare how different types of cities respond to the same lifestyle variables and identify which factors matter the most for each cluster.

-----Dataset-----

City Lifestyle Segmentation Dataset 
By: Umut Uygurr
https://www.kaggle.com/datasets/umuttuygurr/city-lifestyle-segmentation-dataset

Below are the columns we used and their associated datatypes::

city_name                            →  object

country                              →  object

population_density                   →  int64

avg_income                           →  int64

internet_penetration                 →  float64

avg_rent                             →  int64

air_quality_index                    →  int64

public_transport_score               →  float64

happiness_score                      →  float64

green_space_ratio                    →  float64

-----Steps Taken-----

For preprocessing, we selected the aforementioned numeric features for clustering and regression. We standardized the feature values using StandardScaler to make sure the data from each variable scales fairly. We split out the happiness score as the target for linear regression while using the lifestyle features ad predictors. 

Once we were ready, depending on each city's overall wealth, access to amenities, etc. each city was clustered as either High-Density Urban, High-Income Modern, or Low-Income Developing. 

After clustering, we simply used linear regression to calculate and visualize the impact on our target happiness value from the other variables. For each cluster, the impact of each variable was noticeably different. 

-----Cluster Feature Analysis-----

Our findings for each cluster are as follows. High-Density Urban Cities have the most dense population, forcing a cramped environment with less green space and lower quality air. However, this allows the best public transport out of necessity. The cost of rent is high but manageable and access to the internet is high. High-Income Modern Cities have the least dense population allowing for large green space, high quality air, the highest internet access, great public transport, high income, and most importantly, comfort. But this comes with an extremely high cost of living. Finally, Low-Income Developing Cities sit in the middle for density, having large amounts of green space, average air quality, and the cheapest rent. There are lots of downsides however. Due to low infrastructure, public transport is horrible, income is the lowest, and there is way less internet access.

-----Regression Model Analysis-----

Of the four features that show strong relationships with happiness, our findings are as follows. With income climbing, so too does happiness. Especially in low income/high density cities, and having a lesser but still positive effect in higher income cities. Without context, this may not make sense as with higher rent costs, happiness rises, affecting low income cities the most. However, this makes sense due to rent directly correlating with income and access to amenities. Unsurprisingly, higher access to the internet allows higher levels of happiness, having the greatest positive effect on low income cities as it is something they lack. Finally, air pollution has a steady decrease in happiness across the board, hardly affecting one cluster over the other. Overall, these results show that wealth, digital connectivity, and clean air are key factors for how happy cities are, with noticeable differences in how wealthy and dense said city already is.

-----Conclusion-----

High-income modern cities seem to have an overall higher level of happiness than their urban and developing counterparts. It appears that high income and greater access to amenities, internet, transportation, and more are the main reasons for this.

Because of this, however, factors influencing happiness have less of an effect on modern city residents (as seen by the less–steep linear regression slopes), since they already “have everything” in abundance.

Meanwhile, for urban and developing cities, factors affecting happiness have a much stronger correlation. For example, higher internet access had a profound effect on happiness for developing cities in particular, since that was a struggle point for them.

This suggests that if we want to improve resident happiness, we must focus on correcting specific issues depending on the situation of the cities in question, instead of using a uniform approach. This data also suggests that if we wanted to increase the U.S.’s “total happiness,” focusing on urban and developing cities would be more efficient than directing resources toward wealthier modern ones.
