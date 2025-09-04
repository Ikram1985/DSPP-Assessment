












DSPP formative assessment - Section 1  - Housing Prices 














 BPP Coursework Cover Sheet 
Please use the table below as your cover sheet for the 1st page of the submission. The sheet should be before the cover/title page of your submission. Programme 	BSc (Hons) Data Scientist 
Module name 	Data Science Professional Practice 
Schedule Term 
Student Reference Number (SRN) BP0306155
Report/Assignment Title - Data science project Car Sales, Price predictions and resale value.
Date of Submission 
10/09/25
Declaration of Original Work: 
I hereby declare that I have read and understood BPP’s regulations on plagiarism and that this is my original work, researched, undertaken, completed and submitted in accordance with the requirements of BPP School of Technology. 
The word count, excluding contents table, bibliography and appendices, is 1182 words. 
Student Reference Number: BP0306155
Date: 10/09/25
By submitting this coursework, you agree to all rules and regulations of BPP regarding assessments and awards for programmes. Please note, submission is your declaration you are fit to sit. 
BPP University reserves the right to use all submitted work for educational purposes and may request that work be published for a wider audience. 
BPP School of Technology 










Executive summary

This project I am going to examine the following from the dataset.  Housing prices from 1969 until 2020. The data is broken down into 6 categories. These are square feet, Bedrooms, Bathrooms, Neighbourhood, Year Built and Price.  Given that the 1960 were the highest record for price a property was sold, is interesting given that the demand has once increased over the years. Looking at most recent times there seems to be a decline in property price from 2010 to 2020. Given that information it looking like the decline is carrying on for 2030 and 2040. Which may indicate this will be a good time for buyers to enter the market to purchase a property.  Also looking at the data, there are a few outliers within those properties that have been valued, which show some have higher values than the median within those neighbourhoods. 
But overall, the data has a fair split, and there are no biases within the dataset, which allowed me to do a fair analysis overall. 





















Introduction

Data Source and Preparation:

Data collection
The Data set was pulled from Kaggle (Housing Price Prediction Data)This dataset was chosen due to wanting insight into how the housing market has been developing from 1969 until 2020. Wanted to use this dataset to provide insight into the number of bedrooms per property, the price ranges, average price properties sold per decade and lastly to forecast 2030 and 2040 price range
•	The dataset contains 5 columns and 50000 rows
•	This dataset was chosen as it provides me with all the data needed to work on projecting future prices. 

Data processing
Loading and exploring the data.
Too load the data into Colab, I needed to make sure the file was .CSV as the code used will be shown in the screenshot below. (Screenshot 1)
 
Pandas allows the data to be read in multiple columns and rows((Colab, 2025) (import pandas as pd)
 Once this has been coded, it is then importing the CSV file from the location store into Colab. (housing_price = pd.read_csv("/content/housing_price_dataset.csv")

Next step is to explore the data and see how many rows and columns within the dataset, if there is any missing values and the different types of data from Integers to object and float. ( housing_price.info() )
(Screenshot 2)
 
The next step is to drop any missing values or null within the data set, this is down to making sure the quality and integrity of the data. (Saste, 2024)
Once happy with the dataset it is time to move on to do some data analysis 

Data Analysis
First wanted to know what the split for the neighbourhood are. As this is broken down into Suburb, Rural and Urban, reason behind this is to see if there are any biases within the data that leans towards one of the neighbourhoods. Data bias fails to give an accurate picture of the dataset. (Editor Team, 2025)
For the following was used to get this data. (housing_price['Neighborhood'].value_counts() )
(Screenshot 3)
 
Looking at the screenshot above there is an even split between the three neighbourhoods. 
Next step was to look at the bedroom each of the neighbourhoods had, for this the groupby code used and then used the mean, median, min and max to get this data. (housing_price.groupby('Neighborhood')[['Bedrooms']].agg(['mean', 'median', 'min' ,'max'])
(Screenshot 4)
 
Rural has a higher median, other than that the dataset is evenly distributed. 

Last one used for data analysis and most Important is the value. The same type of code was used as for the bedroom. (housing_price.groupby('Neighborhood')[['Price']].agg(['mean', 'median', 'min' ,'max']) )
(Screenshot 5)
 
Again, with this the split is even across all datasets. This shows the price range for each of the neighbourhoods. Which is interesting to read as rural has the highest value with urban coming in last. 

Visualisations 
Now it is time to visualise this dataset. As it would be easier for someone that is not data literate to understand the data. As this is easy to read and patterns can be identified easily.  (Kosters, 2022)
First,  wanted to visualise the number of bedrooms within the dataset. This is just to show there is an even split with each number of bedrooms. But looking at the visual you can see that 3 bedrooms is slightly higher than the others. 
housing_price['Bedrooms'].plot(kind = 'hist')
(Screenshot 6)
 
Next one that was visualised was the price per property. This is highly that most of the values is around 200,00 to 250,00 range. Which is an interesting insight as that would allow anyone who is selling their property to know which price range sales were made. 
housing_price['Price'].plot(kind = 'hist')
(Screenshot 7)

 
Next up was to project future sales that would happen in 2030 and 2040. For this the data for years built must be converted into decades. Below is the code and the write up next to the code for each step. 




(Screenshot 8)
 
As shown above the data is spread evenly other than 2020 as this is yet to be completed. 

Next step was to create a line chart to show the average price each house sold per decade. 
(Screenshot 9)
 
Looking at this the highest average prices where in the 1960 and then there was a massive drop in the 1970. This pattern is repeated in the 80’s and 90’s. Within the 2000’s era, there seems to be stability within the price as it is not fluctuating as much as the past. 
Before doing the forecasting, needed to see if there is a lot of outliners within the data set. This is best visually shown using a box chart. Outliers are data points that are noticeably away from all the other data points. (DASCA, 2024)
(Screenshot 10)
 
As you can see above there is few outliners within each decade, what is interesting there are a lot more outliners within the 1960 at the higher end of the box and whisper chart. 
After reviewing the above, it was time to code for forecasting the future values for 2030 and 2040.
Below is the code used to create the linear regression forecasting model. This is using the decades and the historical values to plot and forecast the future figures. 
(Screenshot 11)
 
(Screenshot 12)
 
As you can see, looking as the other two projected decades it is following a similar trend to the other decades within the 2000’s. However, this could all change in there is a housing market crash like the one in 2008. 

Discussion/Recommendations for Future Iterations:
For future analysis, would look at expanding the forecasting out until 2070 or 2080 to look and see what other trends will be showing. Anything that would be possible to do in the future instead of forecasting by decades leave the dataset by year and see how that is presented when it is visualised as the would give a better visual to those used both by drilled down by years. Also look at doing further analysis on the outliners and seeing which neighbourhoods these fall under rather than having it all group into one. As this would give better insight and overall value to the end analysis.  









Reference 
Colab, G. (2025) colab.google, colab.google. Available at: http://0.0.0.0:8080/articles/pandas/ (Accessed: 4 September 2025).
DASCA (2024) Why Detecting Outliers is Crucial for Accurate Data Analysis? Available at: https://www.dasca.org/world-of-data-science/article/why-detecting-outliers-is-crucial-for-accurate-data-analysis (Accessed: 4 September 2025).
Editor Team, P. (2025) Common Types of Data Bias (With Examples) | Pragmatic Institute. Available at: https://www.pragmaticinstitute.com/resources/articles/data/5-common-bias-affecting-your-data-analysis/ (Accessed: 4 September 2025).
Kosters, M. (2022) The Five Benefits of Data Visualization | Deloitte Netherlands. Available at: https://www.deloitte.com/nl/en/services/tax/perspectives/bps-the-five-benefits-of-data-visualization.html (Accessed: 4 September 2025).
Saste, Y. (2024) (5) The Mystery of NULL Values: Why They Matter and How to Tackle Them | LinkedIn. Available at: https://www.linkedin.com/pulse/mystery-null-values-why-matter-how-tackle-them-yugandhara-saste-novjf/ (Accessed: 4 September 2025).

