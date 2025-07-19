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

prompt = """
Provide the entire code to calculate profit and loss pie charts showing contribution of each sub-category. 
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

<!-- ───────── START of Prompts by Sai Nuka (snuka@purdue.edu) ───────── -->

# Prompt Log of Sai Nuka - Regional/Operational Analyst

Initial Question (Used for initial regional profit analysis):
How do the four regions rank in terms of profit performance, and what are their basic profit metrics
(Used in the comment above the SQL query in cell w4hioxWZumFI)

Gemini first impressions (Used to get Gemini's initial thoughts on regional profit data):
I just ran a simple query to analyze regional profit performance for a Superstore dataset.

Here are the results:
{regional_basic.to_string(index=False)}

As a business analyst seeing this data, please provide your first impressions:
(Used in the prompt_first_impressions variable in cell XdMxLcldv2yQ)

Gemini Hypothesis (Used to generate data-driven hypotheses):
As a business analyst, I've investigated regional performance patterns in a Superstore dataset. Here are my findings:

{findings_summary}

Based on these investigation results, please generate 3 data-driven hypotheses about WHY these regional performance differences exist.

Focus on operational, geographic, and market factors that could explain these patterns.
(Used in the prompt_hypotheses variable in cell y7ywmkGo2s7f)

Gemini Analysis of Hypothesis 1 Results (Used to analyze Query 1 results against Hypothesis 1):
Hypothesis 1: The "Economic Hub" Effect
The disproportionately high profits in the West and East are driven by the concentration of business in major economic hubs (like California and New York), which host a higher density of high-value corporate clients and affluent consumers who purchase higher-margin products.

Supporting Data:

Finding #1: The West and East have the highest average profit per order ($33.85 and $32.14, respectively).
Finding #3: California and New York alone account for a massive portion of their regions' profits (CA: $76k of $108k West profit; NY: $74k of $91.5k East profit).
Finding #2: The West and East dominate in the Corporate and Home Office segments, which typically represent higher-value, more profitable orders than the general Consumer segment.
Potential Explanation (Geographic & Market Factors): States like California (Silicon Valley) and New York (Financial District) are home to a vast number of large corporations and a thriving "prosumer"/Home Office market. These customers are likely purchasing more expensive items (e.g., high-end office chairs, advanced technology) in larger quantities, leading to a much healthier profit margin per order. The business effectively succeeds by winning in these key, dense markets.

**ACTUAL QUERY RESULTS:**

**Query 1a - Product Categories in Economic Hubs vs Other Regions:**
{economic_hubs_data.to_string(index=False)}

**Query 1b - Corporate Customer Performance by Region:**
{corporate_aov_data.to_string(index=False)}

**ANALYSIS REQUEST:**
As a business analyst, please analyze these actual query results against the "Economic Hub" hypothesis.
Use your expertise to determine what aspects are most important to examine and draw conclusions.
Provide a comprehensive analysis of whether this hypothesis holds up based on the data evidence.
(Used in the prompt_hypothesis1_analysis variable in cell pD5T7O1_XFfw)

Gemini Analysis of Hypothesis 2 Results (Used to analyze Query 2 results against Hypothesis 2):
Hypothesis 2: The "Central" Problem - Margin Erosion
The Central region's poor performance, specifically its extremely low average profit per order, is caused by a less profitable product mix and/or a more aggressive pricing and discount strategy, likely driven by local market competition or a different customer demographic.

Supporting Data:

Finding #1: The Central region has the lowest average profit per order ($17.09), which is nearly half that of the West and East.
Finding #1: Despite having the second-highest number of orders (2,323), the Central region has the lowest total profit ($39,706). This indicates a systemic issue with profitability on each sale, not a lack of sales activity.
Finding #2: The Consumer segment profit in the Central region ($8,564) is drastically lower than in other regions, suggesting the bulk of its high order volume may come from low-margin consumer sales.
Potential Explanation (Operational & Market Factors): The Central region may face more price-sensitive competition, forcing the use of heavy discounts to win sales. Alternatively, the product mix being sold might be skewed towards lower-margin categories (e.g., office supplies vs. technology). This operational choice (or market necessity) erodes profit on every transaction, leading to a high-volume, low-profit scenario.

**ACTUAL QUERY RESULTS:**

**Query 2a - Discount Strategy Analysis by Region:**
{discount_analysis_data.to_string(index=False)}

**Query 2b - Product Mix Analysis - Central Region:**
{product_mix_data.to_string(index=False)}

**ANALYSIS REQUEST:**
As a business analyst, please analyze these actual query results against the "Central Problem - Margin Erosion" hypothesis.
Use your expertise to determine what aspects are most important to examine and draw conclusions.
Provide a comprehensive analysis of whether this hypothesis holds up based on the data evidence.
(Used in the prompt_hypothesis2_analysis variable in cell _eHFsmqhYtHR)

Gemini Analysis of Hypothesis 3 Results (Used to analyze Query 3 results against Hypothesis 3):
Hypothesis 3: The "Segment Strategy" Mismatch
Regional performance variations are influenced by how well the regional sales and marketing strategies align with the dominant customer segments in that area. The East's success, for example, is amplified by a strong focus on the Home Office segment, while the South may be underperforming in that same area.

Supporting Data:

Finding #2: The East's profit from the Home Office segment ($26,709) is its strongest category, even outperforming its Corporate segment. This is a unique pattern not seen elsewhere.
Finding #2: In stark contrast, the South has the lowest profit from the Home Office segment ($4,620) of any region.
Finding #2: The West demonstrates a balanced strength but leads significantly in the broad Consumer segment ($57,450), suggesting a successful mass-market approach.
Potential Explanation (Operational & Market Factors): These differences suggest tailored (or untailored) regional strategies. The East's sales team might be specifically trained or incentivized to target and serve home-based professionals, a strong demographic in that region. Conversely, the South's marketing and sales efforts might be more focused on general consumers, thereby missing opportunities with potentially lucrative Home Office or Corporate clients. This isn't just about the market existing, but about the operational focus to capture it.

**ACTUAL QUERY RESULTS:**

**Query 3a - Customer Segment Performance by Region:**
{segment_analysis_data.to_string(index=False)}

**Query 3b - Home Office Segment Analysis by Region and Category:**
{home_office_analysis_data.to_string(index=False)}

**ANALYSIS REQUEST:**
As a business analyst, please analyze these actual query results against the "Segment Strategy Mismatch" hypothesis.
Use your expertise to determine what aspects are most important to examine and draw conclusions.
Provide a comprehensive analysis of whether this hypothesis holds up based on the data evidence.
(Used in the prompt_hypothesis3_analysis variable in cell LiHSEFepaniV)

Gemini's strategic response (Used to generate the strategic action plan):
I need to transform these validated regional analysis insights into actionable business strategies.

**HYPOTHESIS 1 ANALYSIS - Economic Hub Effect:**
{response_hypothesis1.text}

**HYPOTHESIS 2 ANALYSIS - Central Problem Margin Erosion:**
{response_hypothesis2.text}

**HYPOTHESIS 3 ANALYSIS - Segment Strategy Mismatch:**
{response_hypothesis3.text}


Based on these validated insights, what should the business do? How can we measure impact? What are the risks?

Transform these findings into a comprehensive strategic action plan that executives can implement across regional operations.
<!-- ───────── END of Prompts by Sai Nuka (snuka@purdue.edu) ───────── -->

<!-- ───────── START of Prompts by Rakesh Prusty (prustyr@purdue.edu) ───────── -->
# Prompt Log of Rakesh Prusty - Sales & Revenue Analyst

Here are the prompts used in this analysis, categorized by the DIVE methodology step they correspond to:

## Initial Setup and Data Load

*   "Read the mgmt599-rakesh-assignment-1.assignment1_eda.superstore_dataset table from BigQuery, perform exploratory data analysis"

## Discover (D)

*   "Visualize Sales Trend over time"
*   "Analyze Sales Performance by Different Dimensions"
*   "how sales is corelated to different dimensions. Produce charts and summary"

## Investigate (I)

*   "Analyze Sales Amount by Category and Subcategory"
*   "Analyze Monthly Sales Trend by Region"
*   "Analyze Monthly Sales Trend by Category"
*   "Deep dive into high-performing categories/subcategories"
*   "Investigate profitability issues in specific subcategories"
*   "Analyze Monthly Sales Trend by Segment"
*   "Analyze performance in high-performing regions and segments"
*   "Analyze the impact of Discount on Sales"
*   "Identify High-Sales Periods and Filter Data"
*   "Analyze Sales by Dimension in High-Sales Periods"
*   "Analyze Quantity and Profit in High-Sales Periods"
*   "Summarize Predictive Factors"

## Validate (V)

*   "Check for Consistency of High-Sales Months Across Years"
*   "Contribution of Top Categories/Subcategories in High-Sales Months"
*   "Distribution of Sales Across Discount Levels"
*   "How would you validate that investigate summary is not due to data collection bias?"
*   "Design 3 tests to confirm the Investigate Summary using the available data"

## Extend (E)

*   "Analyze strategies for end-of-year seasonality"
*   "Optimize discount and promotional strategies"
*   "Synthesize findings and formulate growth recommendations"
*   "Analyze strategies for end-of-year seasonality"
*   "Immediate Actions: What can be done today?"
*   "Strategic Implications: How does this change our approach?"
*   "Future Investigations: What follow-up analysis is needed?"
*   "Risk Mitigation: What could go wrong with our recommendations?"
<!-- ───────── END of Prompts by Rakesh Prusty (prustyr@purdue.edu) ───────── -->

<!-- ───────── START of Prompts by Pavan Meka (pmeka@purdue.edu) ───────── -->
# Prompt log of Pavan Meka - Product Performance Analyst

## Preprocessing/Data Cleaning:
*  Clean and preprocess the dataset by handling null values, parsing order dates into year/quarter/month, converting key fields to numeric types, and engineering features like Profit Margin for further analysis.

## D- Discover
- Aggregate KPIs by category, subcategory, and product using:  
  SUM(sales), SUM(profit), AVG(profit margin), and COUNT(order_id).
- Rank top 10 products and categories based on:  
  Total Sales, Total Profit, and Profit Margin.
- Group data by Year or Quarter to analyze temporal trends.
- Identify product cycles and detect seasonal spikes or dips in performance.

## I- Investigate

- Explore discounting patterns across customer segments, regions, and subcategories.
- Segment data into discount ranges (0%, 0.01–0.2, >0.2) and compare metrics like sales, profit, and profit margin.
- Evaluate profitability across Consumer, Corporate, and Home Office segments.
- Use Order Quarter to identify seasonal discount trends and detect performance volatility.
- Create charts to see how discounts affect profit margins.
- Check how much sales and profit each discount level brings on average.
- Look at how often each discount level is used over time.
- Find out which product categories and subcategories get the highest discounts.
- See if giving more discounts leads to more sales or lower profits.

## V - Validate

- Check how discount, sales, quantity, and profit margin are related using a correlation chart.
- Use a regression model to see which factors affect profit margin the most.
- Compare average profit margins between no-discount and high-discount orders using a t-test.
- Use ANOVA to check if profit margins are different across product categories.
- Understand if the differences found are meaningful or just due to chance.
- Check how different discount levels perform in each region.
- Use a heatmap to show profit margins by discount and region.
- See how different customer types (like Consumer or Corporate) buy from each product category.
- Use a heatmap to show which customer and category pairs give the best profits.

## E - Extend

- Group products using Product Strategy Matrix
- Find best and worst categories and subcategories by profit.  
- See how discounts affect profit margins across categories and regions.  
- Compare regions and customer segments for higher profits.  
- Check seasonal trends using year and quarter data.  
- Use heatmaps to view profit and transactions by discount and subcategory.
 
<!-- ───────── END of Prompts by Pavan Meka  (pmeka@purdue.edu) ───────── -->
<!-- ───────── START of Prompts by Erjon Brucaj (ebrucaj@purdue.edu) ───────── -->
# Prompt log of Erjon Brucaj - Customer Behavior Analyst

**Prompt 1: Identifying High-Value Customer Segments Using CLV Scoring**

I'm analyzing customer value for a retail dataset using a calculated Customer Lifetime Value (CLV) score based on total sales, total profit, number of orders, and average profit margin.
These are my top 10 customers based on the highest CLV scores:
Customer   num_orders   total_sales   total_profit   avg_profit_margin   clv_score
Tamara Chand    5	        19052.22	    8981.32	        0.213	            0.703
Adrian Barton	   10	        14473.57	    5444.81	       -0.083	            0.651
Sanjit Chand	    9	        14142.33	    5757.41	        0.263	            0.637
Raymond Buch   6	        15117.34	    6976.10	        0.210	            0.623
Sanjit Engle	   11	        12209.44	    2650.68	        0.194	            0.571
Ken Lonsdale	   12	        14175.23	     806.86	       -0.033	            0.567
Hunter Lopez	   6	        12873.30	    5622.43	        0.314	            0.562
Clay Ludtke      12	        10880.55	    1933.78	        0.245	            0.556
Greg Tran         11	        11820.12	    2163.43	        0.286	            0.554
Keith Dawkins	  12	         8181.26	    3038.63	        0.245	            0.552
Help me understand:
1. What are the key insights or patterns from this group?
2. Why might these patterns exist?
3. What strategic actions or business implications could follow from this?
**Prompt 2: Uncovering Purchasing Behavior Trends Across Segments and Time**

You are an expert data analyst working with a retail dataset from a Superstore. Below is a summary of key outputs from our customer behavior analysis. Use this data to analyze customer purchasing patterns and provide actionable insights.

I'm analyzing purchasing patterns in a retail dataset.

Here are summary tables I created:
1. **Top 10 customers by number of orders:**
customer	     num_orders    total_sales    total_profit    avg_discount
Emily Phan	            17	        5478.06	     144.96	       0.197
Sally Hughsby	            13	        3406.84	     558.47	       0.136
Noel Staavos	            13	        2964.82	    -234.77	       0.215
Patrick Gardner          13	        3086.91	     137.46	       0.169
Zuschuss Carroll         13	        8025.71	   -1032.15	       0.255
Joel Eaton	            13	        6760.82	     221.80	       0.146
Erin Ashbrook	            13	        2846.71	     -52.74	       0.300
Chloris Kastensmidt    13	        3154.86	     141.28	       0.234
Suzanne McNair         12	        5563.39	     581.57	       0.127
Rick Bensley	            12	        4715.47	     640.55	       0.135
2. **Monthly orders and sales:**
[Include 3–5 high months]
- 2022-11: 261 orders, $118,447.83
- 2022-12: 224 orders, $83,829.32
- 2022-09: 226 orders, $87,866.65
3. **Top-selling subcategories:**
subcategory	        sales	        profit
Phones	   $330,007.05	       $44,515.73
Chairs	               $328,449.10	       $26,590.17
Storage	   $223,843.61	       $21,278.83
Tables	               $206,965.53	      -$17,725.48
Copiers	            $149,528.03	    $55,617.82

4. **Average Order Value by segment:**
- Home Office: $472.67
- Corporate: $466.41
- Consumer: $449.11
Help me understand:
1. What key patterns or customer behaviors stand out from this data?
2. Why might these patterns be occurring?
3. What actions or business strategies could be informed by these trends? Customers by Average Order Value (AOV):

**Prompt 3: Evaluating Customer Retention and Churn Risk Signals**

You are a customer analytics expert analyzing retention data for a Superstore retail dataset. Below is a summary of key outputs identifying patterns in customer behavior, particularly repeat buyers and churn risk.

---I'm analyzing customer retention in a retail dataset, Here are my summary tables:
1. **Customer Type Counts:**
customer_type     count
Repeat                  781
One-Time              12
2. **Average Profit by Customer Type:**
customer_type     total_profit
Repeat                 365.72
One-Time             63.95
3. **High-CLV Customers At Risk of Churn:**
customer           clv_score   recency_days   num_orders   total_profit
Tamara Chand     0.703       399                         5            8981.32
Sanjit Chand        0.637       349                         9            5757.41
4. **Repeat vs One-Time by Segment:**
segment         One-Time    Repeat
Consumer        0.0147      0.9853
Corporate         0.0212      0.9788
Home Office     0.0068      0.9932
5. **Category Preference by Customer Type:**
customer_type    category             num_orders
One-Time             Furniture                10
One-Time            Office Supplies       11
One-Time            Technology              6
Repeat                Furniture                 2111
Repeat                Office Supplies       6015
Repeat                Technology             1841
6. **Average Discount by Customer Type:**
customer_type   discount
One-Time        0.1556
Repeat          0.1562

Help me understand:
1. What retention risks or opportunities stand out in this data?
2. Why might these patterns exist?
3. What strategies could improve retention, particularly among high-value or at-risk customers?

<!-- ───────── END of Prompts by Erjon Brucaj (ebrucaj@purdue.edu) ───────── -->
