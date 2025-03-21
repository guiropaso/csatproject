# Project Background and Overview
Customer satisfaction (CSAT) is a key performance indicator in the contact center industry, directly impacting customer retention, brand reputation, and operational efficiency. This project leverages advanced analytics and machine learning to provide **actionable insights into CSAT trends, agent performance, and customer sentiment.**

A dataset of real post-interaction surveys with scores varying from 1 to 5 from an e-commerce business was used, identifying **key drivers of Customer Satisfaction (CSAT) scores** through **exploratory data analysis (EDA)**, performed correlation studies, developed a **predictive model** to forecast CSAT scores and conducted **sentiment analysis** on customer remarks to extract qualitative insights.

Additionally, an **interactive dashboard** was created to empower operations teams with real-time visibility into agent performance, resolution times, and satisfaction trends, enabling data-driven strategies to enhance customer experiences.

Caveats: For this project a good survey (promoter) is a survey with a score of 4 or 5, while a bad survey (detractor) is a survey with a score from 1 to 3.

CSAT% score formula = sum of promoters / (sum of promoters + sum of dectractors)

See technical analysis notebook here

Check the live CSAT dashboard here

# Objectives
The primary objective of this project is to conduct an in-depth analysis of CSAT trends and patterns within an e-commerce surveys dataset. By leveraging data analytics and machine learning, we aim to uncover insights that drive **service quality improvements, agent performance optimization, and enhanced customer experiences.**

Specifically, this project focuses on:
- **Exploring CSAT Trends:** Analyzing overall customer satisfaction levels, identifying recurring patterns, and detecting operational fluctuations.
- **Understanding Key Drivers:** Investigating how factors such as **agent tenure, shift schedules, resolution time, and issue categories** impact CSAT scores.
- **Segmenting Performance:** Comparing CSAT scores across **agents, supervisors, issue categories, support channels, etc.** to identify high and low-performing areas.
- **Predictive Modeling:** Training a **machine learning model** to forecast CSAT scores based on historical data and operational metrics.
- **Sentiment Analysis:** Extracting qualitative insights from **customer remarks** to understand sentiment trends and common pain points.
- **Actionable Recommendations:** Providing **data-driven recommendations** to improve customer satisfaction and streamline contact center operations.
- **Operational Dashboard:** Designing an **interactive dashboard** to enable real-time monitoring of CSAT performance and empower management teams with actionable insights.

# Data Description
he dataset used in this analysis captures customer satisfaction survey responses over a one-month period for an e-commerce platform, referred to as Shopzilla (a pseudonym). It contains key operational and transactional details related to customer support interactions, providing a comprehensive view of factors influencing CSAT performance.

Key Features:

- **CSAT Score:** Customer satisfaction rating on a scale of 1 to 5.
- **Agent Details:** Agent name, **supervisor, manager, tenure, and shift schedule**.
- **Interaction Details:** **Category and sub-category** of the customer issue.
- **Timestamps:** Issue **reported date & time** and **responded date & time** for calculating response time.
- **Customer Remarks:** Open-text feedback from customers, enabling **sentiment analysis**.

This dataset enables a multi-dimensional analysis of customer satisfaction, allowing us to correlate operational metrics with CSAT scores and identify opportunities for service improvement.


# Executive Summary
**CSAT trends have been improving**, with a **+240 basis point increase from Week 31 to Week 34**, while **response volume remained steady in the last 3 weeks**. The most **critical driver is response time: 84% of issues were responded within 2 hours and this percentage consistently showed an upward weekly trend,** this increase in response time speed positively influenced all other categorical features like tenure groups, shifts, issue categories, etc. The most important categories are **Returns-related inquiries which performed above target (85.2% CSAT), and Order-Related issues which lagged (78.6%) and presents an opportunity**. 

**92% of surveys with positive remarks result in a promoter rating**. However, **only 33% of all surveys contain remarks**, presenting an opportunity to encourage more **positive feedback generation** as a potential lever for improving overall CSAT scores. **Inbound calls account for 80% of total surveys**, making it the primary channel focus for CSAT improvements. The majority of the volume occur between **10 AM to 9 PM** being **Tuesdays though Thursdays** the most important days of the week. Supervisors and managers with lower survey volumes showed greater CSAT volatility, reinforcing the need for a more even distribution of workload.

# Insights Deep Dive

### **Weekly CSAT Performance**

- A **notable improvement of +240 basis points** in CSAT was observed from **Week 31 to Week 34**, while **volume remained constant**—indicating an actual performance uplift rather than a volume-driven fluctuation.

### **Response Time: The Key CSAT Driver**

- **Response time had the highest impact on CSAT** according to the feature importance model implemented (See Jupyter Notebook file).
- **84% of all issues were resolved within 2 hours**, and this performance improvement spills over into other categorical factors like tenure, shift, category, channel, etc.
- The overall trend is **positive**, with more issues being resolved **within 2 hours** week over week which drives CSAT scores higher.

### **Customer Remarks & Sentiment Analysis**

- There is a strong correlation between customer remarks sentiment and CSAT scores—**92% of surveys with positive remarks result in a promoter rating**. However, **only 33% of all surveys contain remarks**, presenting an opportunity to encourage more **positive feedback generation** as a potential lever for improving overall CSAT scores.

### **Survey Volume Patterns: Weekly & Hourly Trends**

- The majority of interactions (**48%**) occur between **Tuesday and Thursday**.
- A **clear peak in customer interactions** is observed daily from **10 AM to 9 PM**, with volume during these hours being **10x higher** than late-night hours.
- No seasonal variations were observed within the analyzed period, suggesting a **consistent weekly demand pattern**.

### **CSAT by Manager**

- Agent distribution among managers is **imbalanced**:
    - John Smith oversees nearly **1/3** of all agents, while three managers have each **less than 15%** of the workforce assigned.
- CSAT Performance by Manager:
    - **4 out of 6** managers achieved **passing scores (above 80%)**, while the remaining two scored **79%** but had **low survey volume**  (**<15%** combined).
    - Best-performing manager: **Emily Chen (86.07%)**, exceeding the next best manager (John Smith) by **+290** basis points.

### **CSAT by Tenure**

- All tenure groups met the 80% target.
- **On-Job Training (OJT) agents** generated **30%** of surveys, reflecting their large representation (**38%**) in the agent population.
- **Tenured agents** outperformed **OJT agents (83.2% vs. 80% CSAT)**, though both are trending positively WoW.

### **CSAT by Issue Category & Sub-Category**

- **Returns (45%)** and **Order-Related (33%)** account for **78%** of total surveys.
- Low-volume categories (Others, Offers & Cashback, Onboarding-Related) contribute <0.1% each.
- **Order-Related CSAT (78.6%)** is **below target**, while **Returns CSAT (85.2%)** exceeds expectations—both categories show an **upward weekly trend**.

### **CSAT by Supervisor**

- **8 out of 40** supervisors (**20%**) scored below 80%.
- Low survey volume among some underperforming teams (≈0.5% of total surveys per team).
- Zoe Yamamoto’s team (4.1% of total surveys) had a **77%** CSAT, but only met the target in the last week of the period.

### **CSAT by Shift**

- Morning shift (48% of agents) and evening shift (39% of agents) handle most of the survey volume, **both showing an uptrend in CSAT scores**.
- Afternoon and split shifts (11% of total volume combined) are on target but trending downward.
- Night shift (1.5% of total volume) is statistically insignificant.

### **Channel Breakdown**

- **Inbound calls** account for **80%** of total survey responses, making this channel the **primary driver of survey generation**.
- Outbound calls (17%) and emails (4%) contribute marginally to survey generation.
- Despite channel differences, the **overall CSAT trend is positive across all channels**.



# Recommendations
Based on the insights gathered, the following strategic recommendations are proposed to optimize CSAT performance:

- **Rebalance agent distribution**: Adjust the allocation of agents under supervisors and managers to ensure a more even distribution of survey volume. This will provide a more accurate and actionable assessment of leadership performance.
- **Encourage customer remarks generation**: Given the strong correlation between positive remarks and CSAT scores, frontline teams should be coached to prompt customers for feedback during successful interactions. This can serve as a lever for improving overall satisfaction.
- **Prioritize response time improvements**: Since response time under 2 hours is the most influential driver of CSAT, operational efforts should focus on reducing resolution time, particularly in high-volume intervals.
- **Target high-impact areas**: Implement CSAT optimization strategies specifically during peak contact periods, with a strong emphasis on inbound calls and the Order Related & Returns categories, as they account for the majority of customer interactions.
