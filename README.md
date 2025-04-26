# cmpsc311-homework-4-solved
**TO GET THIS SOLUTION VISIT:** [CMPSC311 Homework 4 Solved](https://www.ankitcodinghub.com/product/311/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;124584&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CMPSC311 Homework 4 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
We’re hoping to model the relationship between pests and missed garbage collection in NYC. For convenience, we’ll assume the 311 Service Requests cover all requests made to the city for both complaints about pests and complaints about missed garbage collection.

Below is a query to find 311 requests that mention “pest” in their descriptor. Its purpose is to give you a template query for the following problems.

• Reference for LIKE

• Reference for functions dealing with strings like LOWER

• Reference for date_extract_y, this is unique to SoQL on this platform

• Reference for using AND in our WHERE statement

In [1]:

import requests import pandas as pd

In [2]:

# url = “https://data.cityofnewyork.us/resource/erm2-nwe9.json”

# query = “””

# SELECT

# agency, agency_name,

# complaint_type,

# descriptor,

# COUNT(unique_key) as cnt,

# date_extract_m(created_date) as monthAssignment Project Exam Help

# WHERE

# lower(descriptor) like ‘%pest%’ AND

# GROUP BY

# agency, agency_name, complaint_type, descriptor, month

# 50000

# “””

# params = {“$query”: query}

# resp = requests.get(url=url, params=params)

# assert resp.status_code == 200

In [3]:

# df = pd.DataFrame(resp.json())

# df[“cnt”] = df.cnt.astype(float)

# df.sort_values(“cnt”).tail(10)

Question 0 – getting the response variable¶

All references to time should be extracted from the created_date variable. I highly recommend you to limit the time range you’re querying when you’re still testing out your query, e.g. limit to a single year and month.

Using the SoQL language similar to the example above, please create a data frame, called pest, where each row corresponds to a different year, month, and borough. The columns should be the year, month, borough, and number of requests made. Please make sure the number of requests made is of type float.

Please make sure all data with the following constraints are included:

• The agency should be ‘HPD’

• The lower-cased value from complaint_type should be “unsanitary condition” • The lower-cased value from descriptor must contain the word pest

• You can assume that the number of data are less than 50000. Do NOT use pandas functionalities to perform the aggregation.

In [4]:

### TEST FUNCTION: test_311_get_y

# DO NOT REMOVE THE LINE ABOVE

Question 1 – getting the independent variable¶

All references to time should be extracted from the created_date variable. I highly recommend you to limit the time range you’re querying when you’re still testing out your query, e.g. limit to a single year and month.

Using the SoQL language similar to the example above, please create a data frame, called missed_collect, where each row corresponds to a different year, month, and borough. The columns should be the year, month, borough, and number of requests made.

Please make sure the number of requests made is of type float.

Please make sure all data with the following constraints are included:

• The agency should be ‘DSNY’

• The lower-cased value from complaint_type must contain the word miss (this includes recycles and other variables which we will aggregate over) Assignment Project Exam Help

• You can assume that the number of data are less than 50000.

Do NOT use pandas functionalities to perform the aggregation.

### TEST FUNCTION: test_311_get_x

# DO NOT REMOVE THE LINE ABOVE

If you cannot solve the two problems above, please use pest.csv and missed_collect.csv to proceed.

For data in Manhattan, please use seaborn.lineplot, to plot the requests about pests and missed collections on the same plot.

• Make sure the two lines have different colors.

• Please make a data frame with both sets of data titled mdf

• Make sure mdf only has data from Manhattan

• Make sure mdf has a column titled “counts” for the y-axis

• You should set the different colored lines using the hue argument. The variable you pass to this from mdf should be called “var”.

• Your graph should clearly show which dataset has more available data

Side comment: in an exam you would be asked about interpreting this graph.

In [6]:

### TEST FUNCTION: test_plot_wrangle

# DO NOT REMOVE THE LINE ABOVE

In [7]:

Question 3 – creating a base model dataset¶

Please create a new data frame called bdf where we will model the relationship between the number of pest requests vs the number of missed collection requests.

Here are some specifications for bdf:

• It should have a column titled “counts” which are the number of pest requests

• It should have a column titled “month”

• It should have a column titled “log_counts” which are log(1 + the number of pest requests) where log is the natural log.

• It should have a column titled lag0 which are the number of missed collection requests.

• You should have an “indicator” column for each borough but one (which one you drop will not matter), i.e. the values in this column should be 1 if the record is from this borough and 0 otherwise. Their titles do not matter.

• You should have a column titled year that contains the year of the pest request counts.

• Each row should maintain the same interpretation as a record for a year, month, and borough.

In [8]:

### TEST FUNCTION: test_model_wrangle

In [9]:

### TEST FUNCTION: test_data_split

# DO NOT REMOVE THE LINE ABOVE

In [11]:

In [12]:

Question 5 – Choosing the best model¶

Let’s fit several different models (finally) using the data points that correspond to train then predict on the validate records to calculate the root mean squared error, i.e. $sqrt{rac{1}{n} sum_i|Y_i – hat{Y}_i|^2}$. All the following model will be a ordinary linear regression that includes an intercept.

1. counts regressed on the all the borough columns (recall we dropped one), this is the baseline

2. counts regressed on lag0 with all the borough columns (recall we dropped one)

3. counts regressed on lag1 with all the borough columns (recall we dropped one)

4. log_counts regressed on lag0 with all the borough columns (recall we dropped one)

5. log_counts regressed on lag1 with all the borough columns (recall we dropped one) For each model, please perform the appropriate transformation so the units for the RMSE are comparable across models. Please store the RMSEs in a list called rmse for the different models in the order listed above. In [13]:

### TEST FUNCTION: test_models

# DO NOT REMOVE THE LINE ABOVE

In [14]:

In [15]:
