## Customer Categorization using BI - RFM Model

### Project Objective:
Use RFM or Recency, Frequency and Monetary model to categorize customers for creating an effective marketing strategy

### Dataset Used:
<a href= https://github.com/SurabhiBajaj98/Customer_Categorization_usingBI/blob/main/Global%20Superstore%20Data.xlsx> Global Superstore </a>

### Visualization Goals:
1.	Based on RFM scores, exercise judgement and creativity to create different customer segments
2.	Get visibility on sales amount, profitability by segment, sub – category, market and products for each customer category

### Process:
1.	After extracting the data into BI, a regular sanity check exposed duplicity in one product ID being used for multiple product names
2.	New Product IDs created using indexing and merging it to the raw data
3.	#### Recency (in days) - <br>
    a) Created a new table grouped by Customer ID <br>
  	b) Calculated the most recent order date/last transaction date for each customer <br>
    c) Recency = Difference between today’s date and the last transaction date
5.	#### Frequency - <br>
    Summarization of customer ID by the number of orders placed by each of them (counting rows for each ID from the raw data) 
7.	#### Monetary - <br>
    Summarization of customer ID by total sales amount
9.	#### Assigning RFM Scores – Data distribution, individual judgement and executive intervention is required to assign scores. <br>

    For e.g. In case of recency, the lesser the difference the better as it indicates last purchase was made very recently. Here, the data was majorly concentrated around 300-350 days.
  	
    Thus Recency score was as follows:

                GlobalSuperstore[Recency] <=400 , 5, <br>
                GlobalSuperstore[Recency] <=500 , 4, <br>
                GlobalSuperstore[Recency] <=600 , 3, <br>
                GlobalSuperstore[Recency] <=700, 2,  <br>
                GlobalSuperstore[Recency] >700, 1    <br>
              
    Similar approach was adopted to score frequency and monetary values. However, in these cases the higher the value, the higher the score. <br>
   
7.	#### Categorizing Customers –
   
|R Score|F Score|M Score|Category|
|-------|-------|-------|--------|
|   5	|   5   |	5	| Best   | 
|   5	|  >=3	|  Any	|Potential loyalists |
|   5	|  < 3	|  Any	| New Customers |
|   5	|  >=4	|  >=4	| Loyal Customers |
|  <=3	|   5	|  >=4	| At Risk Customers |
|  <=2	|  <=2	|  <=2	|Low Value Customers |
|  Else |  Else |  Else | Others |

#### Note: This is not a standard categorization. It is totally at your discretion.

### Dashboard:

![Dashboard_RFM](https://github.com/user-attachments/assets/58bd628a-4455-40d8-bcc6-487b706419ec)


