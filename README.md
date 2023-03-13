# Employee_Attrition


* We have a list of customers and their transactions with the following schemas
 * Customers Data
  * Customer Id
  * Customer name
  * Activation Date
  * Current Status  <-- target
 * Transactions Data
  * Transaction Id
  * Customer Id
  * Time Spent
  * Amount Spent
* Each customer belongs one of 4 classes
  * Bronze
  * Silver
  * Gold
  * Platinum
* Depending on the customer and their nature of transaction the task is predict which category a new customer is willing to purchase.
* We do feature engineering to obtain data which form distinct clusters for each category

![max_purchase_amount__total_time_spent_kde](/max_purchase_amount__total_time_spent_kde.png)

![max_purchase_amount_kde](/max_purchase_amount_kde.png)

![q75_puchase_amount__total_time_spent_kde](/q75_puchase_amount__total_time_spent_kde.png)


# Feature Importance

|                              **feature** | **chi2_score** |
|-----------------------------------------:|---------------:|
|                         total_time_spent |   1.398257e+06 |
|     num_days_active__min_purchase_amount |   1.605518e+07 |
|     num_days_active__max_purchase_amount |   4.846275e+06 |
|            num_days_active__num_very_low |   8.016138e+05 |
|                 num_days_active__num_low |   5.677959e+06 |
|            num_days_active__num_moderate |   2.625029e+07 |
|                num_days_active__num_high |   5.222245e+06 |
|           num_days_active__num_very_high |   8.155667e+05 |
|        num_days_active__total_time_spent |   7.752625e+08 |
| min_purchase_amount__avg_purchase_amount |   1.578698e+07 |


# Random Forest Confusion Matrix

|                      | **Predicted: Bronze** | **Predicted: Gold** | **Predicted: Platinum** | **Predicted: Silver** | **Total** |
|---------------------:|----------------------:|--------------------:|------------------------:|----------------------:|----------:|
|   **Actual: Bronze** |                   976 |                   0 |                       0 |                     4 |       980 |
|     **Actual: Gold** |                     0 |                 204 |                       0 |                    59 |       263 |
| **Actual: Platinum** |                     0 |                   9 |                      69 |                     0 |        78 |
|   **Actual: Silver** |                    60 |                  21 |                       0 |                   248 |       329 |

# Random Forest Performance 

|            **class** | **precision** | **recall** |   **f1** |
|---------------------:|--------------:|-----------:|---------:|
|           **Bronze** |      0.942085 |   0.995918 | 0.968254 |
|             **Gold** |      0.871795 |   0.775665 | 0.820926 |
|         **Platinum** |      1.000000 |   0.884615 | 0.938776 |
|           **Silver** |      0.797428 |   0.753799 | 0.775000 |
| **Weighted Average** |      0.904775 |   0.907273 | 0.904844 |
