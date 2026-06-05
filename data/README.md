Dataset Structure

dim_customers

Column| Description
customer_id| Unique customer ID
gender| Customer gender
senior_citizen| Senior citizen flag
tenure_months| Customer tenure

dim_services

Column| Description
customer_id| Customer ID
internet_service| Internet type
contract_type| Contract category
payment_method| Payment mode

fact_billing

Column| Description
customer_id| Customer ID
monthly_charges| Monthly bill
total_charges| Lifetime bill
churn_flag| Churn status
