##  Dataset Feature Meanings & Impact on Churn
### Dataset : `churn-bigml-80.csv`
| Feature                    | Meaning                                                                | Why It Might Affect Churn                                                                                                                                                         |
| -------------------------- | ---------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **State**                  | US state (e.g., "KS") where the customer lives                         | Could represent regional service quality or marketing coverage. May correlate with churn due to regional policies or signal strength. Often low impact unless geo-patterns exist. |
| **Account length**         | How long the customer has had an account (in days)                     | Longer account length may mean higher loyalty. Short-term users may be more likely to churn if dissatisfied.                                                                      |
| **Area code**              | Area code of customer phone number (like 415, 408...)                  | May indirectly reflect region. Not highly predictive unless area-based policies or rates differ.                                                                                  |
| **International plan**     | Whether the user subscribes to international calling plan (`Yes`/`No`) | Customers with no international plan but high international usage may churn due to high bills. Or if competitors offer better rates.                                              |
| **Voice mail plan**        | Whether the user has voicemail service                                 | Could indicate a premium service user. May correlate with engagement or customer satisfaction.                                                                                    |
| **Number vmail messages**  | Number of voicemail messages received                                  | Could signal engagement or usage. Low values might mean low interaction, or plan underuse. Not always significant alone.                                                          |
| **Total day minutes**      | Total minutes of calls made during the day                             | High usage during the day could mean higher cost. Might be frustrated with pricing or service quality → higher churn.                                                             |
| **Total day calls**        | Total number of day-time calls                                         | Shows engagement. Many short calls vs. fewer long calls can imply different usage behaviors. May help segment customers.                                                          |
| **Total day charge**       | Charges incurred during day-time calling                               | Highly correlated with `Total day minutes`. Directly impacts billing, which can affect churn if customers feel overcharged.                                                       |
| **Total eve minutes**      | Total evening call minutes                                             | Similar logic as day minutes. Less impactful if evening rates are cheaper.                                                                                                        |
| **Total eve calls**        | Number of calls made in the evening                                    | Frequency of usage may be more important than volume. May help detect active vs. passive users.                                                                                   |
| **Total eve charge**       | Charges for evening calls                                              | Important if rates are too high or if bundled poorly.                                                                                                                             |
| **Total night minutes**    | Call duration at night (usually lowest rates)                          | Night minutes are often discounted, so may not drive churn directly unless quality is poor.                                                                                       |
| **Total night calls**      | Number of night-time calls                                             | Could reflect lifestyle habits. Low impact on churn unless tied to poor service.                                                                                                  |
| **Total night charge**     | Charges for night calls                                                | Generally low, so may have less impact unless customer is ultra price-sensitive.                                                                                                  |
| **Total intl minutes**     | Total international minutes used                                       | High international usage + no plan = higher cost → dissatisfaction → churn.                                                                                                       |
| **Total intl calls**       | Number of international calls made                                     | Similar logic to above. Frequency might indicate intent to use more.                                                                                                              |
| **Total intl charge**      | International call charges                                             | Crucial for pricing sensitivity. May drive churn if customers feel overcharged.                                                                                                   |
| **Customer service calls** | Number of calls to customer service                                    |  `Red flag.` Strongly correlated with churn. More calls = more issues or complaints.                                                                                              |
| **Churn**                  | Target: whether customer has churned (`True`/`False`)                  | Ground truth label for prediction.                                                                                                                                                |

---

## Key Drivers of Churn

| Likely to be Important                | Why                                                              |
| ------------------------------------- | ---------------------------------------------------------------- |
| `Customer service calls`              | High values indicate unresolved issues or dissatisfaction.       |
| `International plan` + `Intl charges` | Users without plan but high intl usage may feel overcharged.     |
| `Total day minutes/charges`           | High day-time usage could lead to large bills → dissatisfaction. |
| `Account length`                      | Short-term customers churn more easily.                          |
| `Voice mail plan`                     | May signal customer commitment or satisfaction.                  |

---
