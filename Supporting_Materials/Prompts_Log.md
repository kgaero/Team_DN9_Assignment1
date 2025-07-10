<!-- ───────── START of Prompts by Kunal Ghosh (ghosh178@purdue.edu) ───────── -->

# Prompt Log of Kunal Ghosh - Product Performance Analyst

## D - Discover (Basic Finding) - Exploration 1: Understanding the Business Context

prompt = """
Act as an expert in Data science. 
As a Product Performance Analyst,
What visualization should I build to answer these questions:
For Product Performance Analyst:
Focus Questions:
Which products/categories perform best?
What drives product profitability?
Where should we focus product strategy?
Required Analysis:
Product profitability analysis
Category performance comparison
Discount impact on product success
"""


## Exploration 2: Data Quality Assessment
### First, get basic statistics from your data

prompt = """
Provide Bigquery to generate basic statistics of the data for the table with columns including:
Sales, Profit, Quantity, Discount, Category, Sub-Category, 
Customer ID, Segment, Region, State, City, Order Date, Ship Date
"""


## I - Investigate (Dig Deeper) Exploration 3: Quick Insights Generation

prompt = """
How to visualize Category performance comparison
"""

prompt = """
Act as expert in Python, Google Colab, Big Query. 
The table scheme is in attachment. 
The data is in pandas imported from BigQuery using the query below: 
%%bigquery superstore SELECT * FROM mgmt599-kunalghosh-lab1.lab1_eda.Superstore 

I would like a pivot table with Category, Sub-category, Discount as rows, order year, order month as columns and Sum of profit as Values. For style, ensure following:
Keep all Profit > 0 = white background. Cell with Profit < 0 = light red
draw borders and set discount only single decimal.
add the Grand Total Profit column on right of Discount before monthwise columns.
Color the discount column cell of those rows for which Grand Total column > 0 to Green otherwise Light Red if Grand Total column < 0.
Provide the python code.
"""

prompt = """
Provide decision framework to perform Segmentation Analysis: Break down aggregates into meaningful segments on the table below:
Schema for BigQuery table mgmt599-kunalghosh-lab1.lab1_eda.superstore:
- Row_ID (_INTEGER)
- Order_ID (_STRING)
- Order_Date (_DATE)
- Ship_Date (_DATE)
- Ship_Mode (_STRING)
- Customer_ID (_STRING)
- Customer_Name (_STRING)
- Segment (_STRING)
- Country (_STRING)
- City (_STRING)
- State (_STRING)
- Postal_Code (_INTEGER)
- Region (_STRING)
- Product_ID (_STRING)
- Category (_STRING)
- Sub_Category (_STRING)
- Product_Name (_STRING)
- Sales (_FLOAT)
- Quantity (_INTEGER)
- Discount (_FLOAT)
- Profit (_FLOAT)
"""

# V - Validate (Quality Assurance)

prompt = """
Provide code to perform 2x2 Quadrant analysis - Cash cow analysis?
"""

prompt = """
Provide the entire code to plot Discount × Profitability (Promotion Efficiency)
"""

prompt = """
Provide the entire code to plot Margin × Volume (Velocity vs Profitability)
"""

prompt = """
Provide the entire code for Order Value × Discount (Revenue vs Promotion Depth)
"""

prompt = """
Provide the entire code for Shipping Speed × Profitability
"""

prompt = """
Provide entire code for Segment × Profit Growth
"""

prompt = """
Provide entire code for Geography: Region × Margin
"""

prompt = """
provide the entire code to plot Category × Return on Discount
"""

prompt = """
provide entire code for Order Count × Geo‐Dispersion
"""

prompt = """
provide the entire code for Customer Diversification sub-categorywise
"""

prompt = """
Provide the entire code to plot Order Size × Order Profit
"""

prompt = """
Provide the entire code to plot Postal Code Density × Profit
"""

prompt = """
Provide the python entire code to plot  Estimate Price Elasticity by Sub-Category
"""


# E - Extend (Strategic Application)

prompt = """
Check carefully, what are cows, dogs, star and questions mark sub-category. 
Strictly based on the content in all the slides, suggest the most actional business recommendations across all slides and reason for the suggestion. 
"""


prompt = """
Provide the entire code to calculate the monetary impact of Limit max discount on Binders = 0.2, Machines = 0.3, Tables = 0.0, Storage = 0.0, phone = 0.2, to cut losses. 

Calculate the Loss of these items of the 2017 for these discount values and provide the total loss.
"""


<!-- ───────── END of Prompts by Kunal Ghosh (ghosh178@purdue.edu) ───────── -->