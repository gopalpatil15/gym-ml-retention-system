# Day 1 – Data Understanding


## 1. Data Schema
member_id – unique ID for each gym member  
join_date – date when the member joined the gym  
last_payment_date – last date of fee payment  
monthly_fee – monthly membership fee  
attendance_count – number of gym visits in last 30 days  
membership_status – active or inactive member  
member_gender - male or female
member_age - age 
payment-status - payment done or remainig 

## 2. Churn Definition
A gym member is considered churned if they have not attended the gym and have not made any payment for more than 30 day.  Churn is treated as a binary value where 1 means churned and 0 means active.

## 1. Data Schema
- **member_id** – unique ID for each gym member  
- **join_date** – date when the member joined the gym  
- **last_payment_date** – last date of fee payment  
- **monthly_fee** – monthly membership fee  
- **attendance_count** – number of gym visits in last 30 days  
- **membership_status** – active or inactive member  
- **member_gender** – male or female  
- **member_age** – age in years  
- **payment_status** – payment done or remaining  

### Derived Features
- **days_since_last_payment** – difference between today and `last_payment_date`  
- **membership_duration** – difference between today and `join_date`  
- **avg_attendance_per_month** – normalized attendance across membership duration  
- **payment_gap** – number of days between payments  
- **attendance_trend** – increase/decrease in visits compared to previous months  
- **fee_to_attendance_ratio** – perceived value of membership  

---

## 2. Churn Definition
A gym member is considered **churned** if:
- They have not attended the gym **AND**  
- They have not made any payment for **more than 30 days**.  

Churn is treated as a **binary value**:  
- `1` → churned  
- `0` → active  

> Future extension: multi-class churn (e.g., *financial churn*, *behavioral churn*) for deeper insights.

---

## 3. Features and Target

### Input Features
- `attendance_count`  
- `days_since_last_payment`  
- `membership_duration`  
- `monthly_fee`  
- `payment_status`  
- `member_gender`  
- `member_age`  

### Target
- `churn` (binary: 1 = churned, 0 = active)

---

## 4. Dataset Plan
- **Synthetic dataset**:  
  - Created based on the defined schema.  
  - Ensure balanced churn ratio (avoid skewed active vs. churned).  
  - Add randomness/noise to mimic real-world behavior.  

- **Real dataset**:  
  - Apply the same schema to public churn datasets (e.g., Kaggle gym churn datasets or general customer churn datasets).  
  - Validate feature importance and adjust definitions if needed.  

---

## 5. Example Feature Table

| Feature                   | Type        | Notes                            |
|---------------------------|-------------|----------------------------------|
| attendance_count          | Numeric     | Visits in last 30 days           |
| days_since_last_payment   | Numeric     | Derived from `last_payment_date` |
| membership_duration       | Numeric     | Days since `join_date`           |
| monthly_fee               | Numeric     | Membership cost                  |
| payment_status            | Categorical | Paid / Remaining                 |
| member_gender             | Categorical | Male / Female                    |
| member_age                | Numeric     | Age in years                     |
| churn (target)            | Binary      | 1 = churn, 0 = active            |

--- 30 days. Churn is treated as a binary value where 1 means churned and 0 means active.

## 3. Features and Target
Input Features:
- attendance_count
- days_since_last_payment
- membership_duration
- monthly_fee

Target:
- churn

## 4. Dataset Plan
This project will start with a synthetic gym dataset created based on the defined schema. Later, the same system can be applied to real or public churn datasets.

