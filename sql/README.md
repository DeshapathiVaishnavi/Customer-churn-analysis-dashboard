SQL Queries

Overall Churn Rate

SELECT
COUNT(CASE WHEN churn_flag='Yes' THEN 1 END) * 100.0 / COUNT(*) AS churn_rate
FROM fact_billing;

Churn by Contract Type

SELECT
contract_type,
COUNT(*) AS customers,
SUM(CASE WHEN churn_flag='Yes' THEN 1 ELSE 0 END) AS churned_customers
FROM dim_services s
JOIN fact_billing b
ON s.customer_id = b.customer_id
GROUP BY contract_type;

Monthly Revenue Lost

SELECT
SUM(monthly_charges) AS monthly_revenue_lost
FROM fact_billing
WHERE churn_flag='Yes';
