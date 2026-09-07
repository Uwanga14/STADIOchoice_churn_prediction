# STADIOchoice_churn_prediction

# Motivation
In the past decade pay-TV and streaming industry has been changing due to consumers moving from satellite TV to streaming services. STADIOchoice is currently facing a challenge whereby their profitable satellite subscriber base of 13.8 million households is declining by about 5% annually, although the STADIOstream has grown to 7.7 million subscribers it hasn’t become profitable. One of the main drivers of this challenge is increasing subscriber churn, which has risen from 6.5% to 9.2% per month over the past two years. During the same period, customer acquisition costs increased from R240 to R355 per subscriber, while trial-to-paid conversion rates declined from 41% to 33%. These trends suggest that attracting and retaining subscribers has become more difficult, thereby reducing revenue growth, increasing marketing costs, and placing pressure on the long-term sustainability of the streaming business. STADIOchoice is attempting to replace a declining but profitable satellite business with a profitable streaming business while investing approximately R34 billion annually in content and sports rights. 
Investigating and addressing subscriber churn is critical to achieving STADIOchoice’s strategic objective of becoming a streaming-first, subscriber-focused organisation. The company possesses valuable data through its unified data platform, including streaming viewing behaviour, billing records, customer support interactions, cancellation history, search activity, and content consumption information. Although existing detection methods of customer churn has shown considerable margins, these conventional methods fail to fully exploit the data within the organisation and effectively identify subscribers who are most likely to cancel their subscriptions therefore understanding the factors influencing churn. The application of Data Science techniques can assist by identifying patterns within historical customer data and developing predictive models that models that estimate the likelihood of subscriber cancellation. The insights generated from this study may support more targeted retention strategies, improve customer engagement, optimise marketing expenditure, reduce unnecessary retention incentives, and strengthen customer lifetime value. These benefits could contribute directly to improved profitability, better decision-making, and the long-term success of STADIOchoice’s streaming business in an increasingly competitive market. 

# Problem statement
STADIOchoice is facing a challenge of increasing churn rate within its streaming business. Monthly streaming churn has increased from 6.5% to 9.2% over the past two years, while customer acquisition costs have risen from R240 to R355 per subscriber and trial-to-paid conversion rates have declined from 41% to 33%. These trends are reducing the profitability of STADIOstream and creating a significant risk to the company’s long-term strategy, which depends on growing a successful streaming business as its satellite subscriber base continues to decline. STADIOchoice collects extensive data on subscriber viewing behaviour, billing history, cancellation records, customer support interactions, search activity, and content consumption. This data remains unclear whether these data sources can be used to accurately identify subscribers who are likely to cancel their subscriptions before churn occurs. The absence of a reliable churn prediction capability limits the company’s ability to proactively retain customers, use retention incentives effectively, and maximise customer lifetime value. The aim of this study is to investigate whether predictive data science techniques can be used to identify STADIOstream subscribers who are at a high risk of churning by analysing subscriber behaviour, billing data, customer support interactions, search activity, and cancellation history. The findings may provide evidence that supports targeted retention strategies, improves customer retention decision-making, and contributes to the long-term profitability and sustainability of STADIOchoice’s streaming business.

# Data request
To build a churn prediction model we will need data from STADIOchoice that allows us to understand subscriber behaviour, engagement, payment patterns, content consumption, customer service interactions, and historical cancellations. 

DATASET 1: Subscriber data
| Column Name          | Data Type   | Example      | Additional Information                                |
|---------------------|-------------|-------------|------------------------------------------------------|
| Subscriber ID       | String      | Sub1432     | It is a unique customer identifier                   |
| Subscription type   | Categorical | streaming   | Streaming, satellite, hybrid                         |
| Subscription status | Categorical | active      | Active, cancelled, suspended, trial                  |
| Converted to paid   | Boolean     | yes         | Shows whether a customer converted from trial to subscription |
| Churn status        | Boolean     | yes         | Shows whether a customer churned                     |
| Sign up date        | Date        | 2026-01-03  | Date the subscription started                        |
| Churn date          | Date        | 2026-09-03  | Churn date                                           |
| Acquisition channel | String      | Facebook ad | Marketing source used for acquisition                |

DATASET 2: Subscription & Billing history
| Column Name               | Data Type   | Example      | Additional Information                               |
|--------------------------|------------|--------------|-----------------------------------------------------|
| Subscriber ID            | String     | Sub1432      | It is a unique customer identifier                  |
| Billing date             | Date       | 2026-01-01   | Monthly billing date                                |
| Plan name                | String     | Premium plus | Package subscribed to                               |
| Monthly fee              | Numeric    | 499          | Monthly subscription fee                            |
| Payment status           | Categorical| successful   | Successful, failed, reversed                         |
| Payment failure count    | Integer    | 2            | Number of payment failures in previous 12 months    |
| Downgrade flag           | Boolean    | yes          | Indicates subscription downgrade                    |
| Auto renewal             | Boolean    | yes          | Indicates auto renewal status                       |
| Retention outcome        | Categorical| retained     | Retained or churned                                 |
| Cancellation request date| Date       | 2026-04-01   | Date cancellation was requested                     |
| Tenure                   | Numeric    | 765          | Duration of subscription                            |

DATASET 3: Streaming Viewing Activity
| Column Name                   | Data Type    | Example | Additional Information                 |
|------------------------------|-------------|---------|----------------------------------------|
| Subscriber ID                | String      | Sub1432 | A unique customer identifier           |
| Watch duration               | Numeric     | 52      | Minutes watched                        |
| Days since last watch        | Numeric     | 5       | Calculated metric if available         |
| Type of content being watched| Categorical | sports  | The kind of content being used         |
| Device type                  | Categorical | Mobile  | Mobile, TV, tablet                     |

## RAAIDD LOG

| Category | Details |
|----------|---------|
| **Risks** | Subscriber data may contain missing values and duplicates. Not enough historical churn data may be available to train a reliable model. |
| **Actions** | Collect and validate the required data, clean and prepare the datasets, analyse churn patterns, build and test a predictive model, and present retention recommendations to stakeholders. |
| **Assumptions** | Historical subscriber behaviour contains patterns that can predict churn. Subscriber IDs can be used to link all datasets, and at least 36 months of historical data is available. |
| **Issues** | Historical churn records may be incomplete or inconsistent, making it difficult to accurately identify subscribers who have previously cancelled their subscription. |
| **Decisions** | The project will focus on STADIOstream subscribers because reducing streaming churn is a key business priority and retaining customers is a primary objective. |
| **Dependencies** | Data must be collected before it can be cleaned and analysed. Data preparation must be completed before model development, and the model must be tested before retention recommendations can be made. |
