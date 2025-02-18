# Credit-Card-Transaction-Dashboard

# project Objective
* To develop the comprehensive credit
  card weekly dashboard that provide
  real time insights into key performennce
  metrics and trends ,enabling stackholder
  to monitor and analyze credit card operations
  effectively .


# project Insights ->
1. Week on Week change:
- Revenue increased by 28.8%,
- Total Transaction Amt & Count increased by 1.68% & 1.71%
2. Overview YTD ->
- Overall revenue is 55.32M
- Total interest is 7.84M
- Total transaction amount is 45M
- Male customers are contributing more in revenue 30M, female 25M
- Blue & Silver credit cards are contributing to 93% of overall transactions
- TX, NY & CA are contributing to 68%
- Overall Activation rate is 57.5%
- Overall Delinquent rate is 6.06%


# Dax Queries

```week_num2 = WEEKNUM('public cc_detail'[week_start_date])Revenue = 'public cc_detail'[annual_fees] + 'public cc_detail'[total_trans_amt] + 'public cc_detail'[interest_earned]```

```Current_week_Revenue = CALCULATE(SUM('public cc_detail'[Revenue]),FILTER(ALL('public cc_detail'),'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])))```

```Previous_week_Revenue = CALCULATE(SUM('public cc_detail'[Revenue]),FILTER(ALL('public cc_detail'),'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])-1))```

```AgeGroup = SWITCH(TRUE(),‘public cust_detail'[customer_age] < 30, "20-30",‘public cust_detail'[customer_age] >= 30 && ‘public cust_detail'[customer_age] < 40, "30-40",‘public cust_detail'[customer_age] >= 40 && ‘public cust_detail'[customer_age] < 50, "40-50",‘public cust_detail'[customer_age] >= 50 && ‘public cust_detail'[customer_age] < 60, "50-60",‘public cust_detail'[customer_age] >= 60, "60+","unknown")```

```IncomeGroup = SWITCH(TRUE(),‘public cust_detail'[income] < 35000, "Low",‘public cust_detail'[income] >= 35000 && ‘public cust_detail'[income] < 70000, "Med",'public cust_detail'[income] >= 70000, "High","unknown")```

