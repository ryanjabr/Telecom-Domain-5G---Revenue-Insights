# AtliQo Telecom - Revenue Insights
## Codebasics Resume Project Challenge - 3

## Problem Statement :
AtliQo is one of the leading telecom providers in India and launched its 5G plans in May 2022 along with other telecom providers. However, the management noticed a decline in their active users and revenue growth post 5G launch in May 2022.

### Approach to solve the problem :
AtliQo’s business director requested their analytics team to provide a comparison report of KPIs between pre and post-periods of the 5G launch. The management is keen to compare the performance between these periods and get insights that would enable them to make informed decisions to recover their active user rate and other key metrics. They also wonder if they can optimize their internet plans to get more active users.

## Task :
- Create the comparison report based on the mock-up provided. Please note the mock-up is created by a business user who has minimal idea about dashboarding. Hence, you need to represent the insights in a much better way. The target audience of this dashboard is top-level management - hence the dashboard should be self-explanatory and easy to understand.

- Create relevant insights not provided in the metric list/mock-up dashboard to support the cause.

## Creating Base measures

```dax
Total Revenue = SUM(fact_atliqo_metrics[atliqo_revenue_crores])
```

```dax
Avg ARPU = AVERAGE(fact_atliqo_metrics[arpu])
   ```

```dax
ARPU Before 5G = CALCULATE([Avg ARPU],dim_date[before/after_5g]="Before 5G")
```

```dax
ARPU after 5G = CALCULATE([Avg ARPU],dim_date[before/after_5g]="After 5G")
```

```dax
ARPU % change = DIVIDE([ARPU after 5G]-[ARPU Before 5G],[ARPU Before 5G],0)
```

```dax
Average Revenue = AVERAGE(fact_atliqo_metrics[atliqo_revenue_crores])
```

```dax
Avg Revenue before 5G = CALCULATE([Average Revenue],dim_date[before/after_5g]="Before 5G")
```

```dax
Avg Revenue After 5G = CALCULATE([Average Revenue],dim_date[before/after_5g]="After 5G")
```

```dax
Avg Revenue % change = DIVIDE([Avg Revenue After 5G]-[Avg Revenue before 5G],[Avg Revenue before 5G])
```

```dax
Revenue Before 5G = CALCULATE([Total Revenue],dim_date[before/after_5g]="Before 5G")
```

```dax
Revenue after 5G = CALCULATE([Total Revenue],dim_date[before/after_5g]="After 5G")
```

```dax
Total Active Users = SUM(fact_atliqo_metrics[active_users_lakhs])
```

```dax
Monthly Active Users = AVERAGE(fact_atliqo_metrics[active_users_lakhs])
```

```dax
Monthly active users before 5G = CALCULATE([Monthly Active Users],dim_date[before/after_5g]="Before 5G")
```

```dax
Monthly active users After 5G = CALCULATE([Monthly Active Users],dim_date[before/after_5g]="After 5G")
```

```dax
Monthly Active users % change = DIVIDE([Monthly active users After 5G]-[Monthly active users before 5G],[Monthly active users before 5G])
```

```dax
Total Unsubscribed Users = SUM(fact_atliqo_metrics[unsubscribed_users_lakhs])
```

```dax
Monthly Unsubscribed Users = AVERAGE(fact_atliqo_metrics[unsubscribed_users_lakhs])
```

```dax
Monthly Unsubscribed Users before 5G = CALCULATE([Monthly Unsubscribed Users],dim_date[before/after_5g]="Before 5G")
```

```dax
Monthly Unsubscribed Users after 5G = CALCULATE([Monthly Unsubscribed Users],dim_date[before/after_5g]="After 5G")
```

```dax
Monthly Unsubscribed users % change = DIVIDE([Monthly Unsubscribed Users after 5G]-[Monthly Unsubscribed Users before 5G],[Monthly Unsubscribed Users before 5G])
```

```dax
MS % = AVERAGE(fact_market_share[ms_pct])
```


## Dashboard
## Insights from the final report

- Atliqo's Revenue has declined by 0.5 % after 5G Installation

- Plans P1,P2 and P3 are the top 3 plans that fetch highest revenue (before and after 5G Installation). 
   
