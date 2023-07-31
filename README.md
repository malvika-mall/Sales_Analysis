# Sales Analysis
In this project, I used Python Pandas &amp; Python Matplotlib to analyze and answer business questions about 12 months worth of sales data. The data contains hundreds of thousands of electronics store purchases broken down by month, product type, cost, purchase address, etc.

# Key Questions:
1. What was the best month for sales? How much was earned that month?
2. What city sold the most product?
3. What time should we display advertisements to maximize likelihood of customer’s buying products?
4. What Products are most often sold together?
5. What product sold the most? Why do you think it did?

# Exploratory Data Analysis:
Firstly, we need to import necessary libraries and dataset and carry out initial data pre-processing such as handling missing or null values and check for duplicates if any. 

Now we’re ready to answer the problem number 1. To remind you, the question is: What was the best month for sales? How much was earned that month?

To answer this problem, obviously we need an additional column called “Month”. If you look carefully at Figure 5, you will see the first 2 characters in “Order Date” values represent months. So the next task we will do is to add “Month” Column.
```
      #Extracting Month from Order Date
      all_data['Order Date'][0].split('/')[0]

      #Defining function to return months
      def return_month(x):
      return x.split('/')[0]

      all_data['Month']=all_data['Order Date'].apply(return_month)
```
1. What was the best month for sales? How much was earned that month?
   
![bar](https://github.com/malvika-mall/Sales_Analysis/blob/main/03%20Visualizations/Top_month.png)

From the above bar chart, we can clearly see that month 12 (December) is the highest sales in 2019 with approximately $4,810,000. Maybe the best product sales are on December because it’s holiday and Christmas.

2. What city sold the most product?
To answer this question, obviously we need to create a new column called “City” column. We notice that “Purchase Address” Column contain the city. We can’t get it directly, we need to extract the data. We can use one of most useful function in pandas, .apply() method.
```
    #Defining function
    def city(x):
    return x.split(',')[1]

    all_data['city']=all_data['Purchase Address'].apply(city)
```
![chart](https://github.com/malvika-mall/Sales_Analysis/blob/main/03%20Visualizations/Top_city.png)

San Fransisco is the highest sale compare to other cities. Maybe Sillicon Valley need more electronic products. Maybe the advertisement is better in San Fransisco. We can use this data to improve the sales of bussiness.
