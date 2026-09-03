**Apollo Healthcare Appointment Analytics**

**Author: Sudiksha Singhvi**

Project Type: Data Analytics

Tools: Python, Pandas, Matplotlib, Jupyter Notebook

**📌Project Overview**

This project analyzes Apollo healthcare appointment data to understand
appointment trends, patient no-show behavior, engagement effectiveness,
financial performance, doctor utilization, and service quality.

The analysis combines appointment-level data with doctor-level
information to generate business-focused insights that can support
better appointment management, patient engagement, revenue optimization,
and operational decision-making.

**🎯Project Objectives**

The main objectives of this project are to:

Analyze appointment volume trends across years and quarters.

Understand the distribution of appointment outcomes.

Identify the booking channels generating the highest appointment
volume.

Analyze factors associated with patient no-shows.

Evaluate the effectiveness of appointment reminders.

Study the relationship between previous no-show behavior and future
attendance.

Compare attendance behavior of Apollo members and repeat patients.

Segment no-show behavior by demographics and visit reasons.

Analyze revenue loss associated with no-shows.

Compare revenue across specialties, appointment types, and cities.

Understand the effect of insurance coverage on patient out-of-pocket
expenses.

Evaluate doctor utilization and patient waiting times.

Explore the relationship between consultation duration and patient
satisfaction.

Examine the relationship between doctor experience and consultation
fees.

**📂Dataset**

The project uses two datasets.

1. Apollo Appointments Fact Table

File: apollo_appointments_fact.csv

75,000 rows

52 columns

One row represents one appointment event.

Important fields include:

appointment_id

patient_id

doctor_id

appointment_date

appointment_day

appointment_month

appointment_quarter

appointment_year

appointment_hour

booking_date

booking_lead_days

booking_channel

appointment_type

specialty

city

state

hospital_name

patient_age

age_group

patient_gender

apollo_member

reminder_type

patient_prior_visits

patient_prior_no_shows

appointment_status

no_show_flag

consultation_fee

actual_fee_charged

insurance_coverage

insurance_covered_amount

patient_out_of_pocket

revenue_realized

wait_time_minutes

consultation_duration_min

patient_satisfaction_score

doctor_utilization_pct

2. Apollo Doctors Dimension Table

File: apollo_doctors_dim.csv

320 rows

15 columns

One row represents one doctor.

Important fields include:

doctor_id

doctor_name

specialty

qualification

experience_years

city

state

hospital_name

consultation_fee

rating

total_reviews

available_days

avg_slot_duration_min

accepts_insurance

teleconsult_enabled

🔗 Data Preparation

The appointment fact table and doctor dimension table are joined using:

doctor_id

The project also prepares analysis-ready datasets by:

Loading both CSV files using Pandas.

Handling selected missing categorical values.

Converting appointment and booking dates to datetime format.

Checking duplicate records.

Checking missing values.

Merging appointment and doctor information.

Creating a resolved appointment dataset by excluding Scheduled
appointments where appropriate for outcome/no-show analysis.

Creating a completed appointment dataset for financial and
service-quality analysis.

📊 Analysis Performed

Section 1 --- Appointment Overview

Q1. Appointment Volume Trend

Analyzes how appointment volume changes across years and quarters from
2022 to 2024.

Q2. Appointment Outcomes

Examines the split between:

Completed

No-Show

Cancelled

Scheduled

Q3. Booking Channel Mix

Identifies which booking channels generate the highest appointment
volume and examines the overall channel mix.

Section 2 --- No-Show Analysis

Q1. Specialty and City No-Show Rates

Identifies specialties and cities with higher and lower no-show rates.

Q2. Booking Lead Time

Analyzes how the number of days between booking and appointment affects
no-show probability.

Q3. Time and Lead-Time Effects

Examines whether evening appointments, weekends, and longer-lead
bookings are associated with higher dropout.

Q4. Appointment Type and Booking Channel Risk

Compares no-show risk across different appointment types and booking
channels.

Section 3 --- Reminder & Engagement Effectiveness

Q1. Reminder Effectiveness

Compares no-show rates across different reminder types, including
patients who received no reminders.

Q2. Prior No-Show History

Studies whether a patient's previous no-show history is associated with
future no-show behavior.

Q3. Membership and Repeat Visits

Compares attendance behavior between:

Apollo members and non-members

Repeat patients and first-time patients

Section 4 --- Patient & Demographic Segmentation

Q1. Demographic Factors

Analyzes no-show likelihood by:

Age group

Gender

Chronic condition status

Q2. Visit Reasons

Identifies the most common visit reasons and examines which reasons are
associated with higher dropout rates.

Q3. Age Distribution by Specialty

Examines patient age-group distribution within:

Paediatrics

Gynaecology

Psychiatry

Section 5 --- Financial Performance

Q1. Revenue Lost to No-Shows

Estimates revenue associated with appointments that resulted in no-shows
and identifies specialties with the highest loss.

Q2. Average Revenue

Compares average realized revenue across specialties and appointment
types for completed appointments.

Q3. City Revenue & Payment Mix

Identifies the highest revenue-generating cities and analyzes the
payment-mode mix.

Q4. Insurance & Out-of-Pocket Cost

Compares average patient out-of-pocket expenses based on insurance
coverage.

Section 6 --- Doctor Utilization & Service Quality

Q1. Doctor Utilization

Identifies specialties with the highest and lowest average doctor
utilization rates.

Q2. Patient Waiting Time

Analyzes waiting time by specialty and time of day.

Q3. Consultation Duration & Satisfaction

Tests the relationship between consultation duration and patient
satisfaction using correlation analysis and visualization.

Q4. Doctor Experience & Consultation Fee

Explores how consultation fees vary with doctor experience.

🔎 Key Findings

The analysis produced the following major findings from the 75,000 appointment records:

Appointment Trends

Appointment volume was highest in 2023 Q4, with 6,998 appointments.

Q4 consistently recorded the highest quarterly volume across the three years, while Q2 and Q3 were comparatively lower.

The quarterly volumes were 6,523 (2022 Q1), 6,487 (2023 Q1), and 6,538 (2024 Q1), showing a broadly stable Q1 pattern.

Appointment Outcomes

73.70% of appointments were Completed.

15.45% were No-Show.

7.72% were Cancelled.

3.13% were Scheduled.

Booking Channel

The Apollo App generated the highest appointment volume with 34,042 appointments (45.39%).

Website bookings contributed 24.73%, followed by Call Centre (14.93%), Walk-In (10.00%), and Partner App (4.95%).

No-Show Risk

Psychiatry had the highest specialty no-show rate at 24.52%, while Neurology had the lowest at 10.69% among the listed extremes.

Among cities, Lucknow had the highest no-show rate at 17.19%, while Pune had the lowest at 13.30%.

No-show probability increased from 15.82% for same-day bookings to 23.26% for appointments booked 30 days in advance.

Weekend appointments had a higher no-show rate (18.68%) than weekday appointments (14.84%).

Evening appointments had an 18.37% no-show rate compared with 13.73% in the morning.

Home Visits had the highest no-show risk (26.25%), followed by Video Consults (21.06%) and In-Clinic appointments (12.18%).

Walk-In bookings had the highest channel-level no-show rate at 20.88%.

Reminder & Engagement Effectiveness

Patients receiving no reminder had a 30.16% no-show rate.

This fell to 16.27% with SMS only, 13.51% with SMS + WhatsApp, and 11.41% with SMS + WhatsApp + Call.

Patients with more previous no-shows showed progressively higher future no-show rates: 15.15% with zero prior no-shows, increasing to 32.68% for patients with 3+ prior no-shows.

Apollo members had a lower no-show rate (12.66%) than non-members (16.89%).

The notebook analysis reported 8.59% for repeat patients versus 66.78% for the first-time/No repeat-visit group.

Patient Segmentation

The most common visit reasons were Follow-up (8,528), Routine Checkup (8,377), and Chronic Condition Management (8,117).

The highest dropout rates among visit reasons were Skin Issue (16.79%), Joint Pain (16.73%), and Cardiac Concern (16.29%).

Paediatrics was predominantly made up of children (68.28%) and teenagers (31.72%).

Financial Performance

The analysis reported ₹19,725,460 in revenue lost due to no-shows.

The specialties with the highest reported lost revenue were Dermatology (₹2,603,230), General Physician (₹2,475,640), and Psychiatry (₹2,336,685).

Among completed appointments, Home Visits generally generated higher average revenue than In-Clinic and Video Consult appointments across specialties.

The highest revenue-generating cities were Bengaluru (₹9,990,616), Delhi (₹9,958,247), and Mumbai (₹8,989,613).

Average patient out-of-pocket expense was ₹859.18 for insured patients versus ₹1,562.82 for uninsured patients.

Doctor Utilization & Service Quality

Average doctor utilization was relatively consistent across specialties, ranging from approximately 76.18% to 77.26% among the reported extremes.

Gastroenterology had the highest reported average utilization (77.26%), while Psychiatry had the lowest (76.18%).

Ophthalmology had the longest average waiting time among the top five specialties at 12.02 minutes.

Average waiting time was 11.55 minutes across Morning, Afternoon, and Evening in the notebook output.

The correlation between consultation duration and patient satisfaction was -0.0035, indicating virtually no linear relationship in this dataset.

💡 Business Recommendations

Based on the analytical findings, the following actions could help improve appointment operations and patient engagement:

Strengthen reminder campaigns: Prioritize multi-channel reminders, especially SMS + WhatsApp + Call, for patients at higher risk of missing appointments.

Create a high-risk patient segment: Use prior no-show history to identify patients who may require additional confirmation or follow-up.

Focus on high-risk appointment types: Review operational processes for Home Visits and Video Consults, which showed higher no-show rates than In-Clinic appointments.

Improve weekend and evening attendance: Consider stronger confirmation workflows and targeted reminders for higher-risk time slots.

Target high-risk specialties and cities: Use localized interventions for specialties and locations with higher no-show rates.

Protect revenue from missed appointments: Prioritize no-show reduction in high-value specialties such as Dermatology, General Physician, and Psychiatry.

Leverage Apollo membership: The lower no-show rate among members suggests that membership engagement can be explored as part of patient-retention strategies.

Monitor waiting-time hotspots: Review specialties with longer waiting times to identify scheduling or capacity bottlenecks.

Do not rely on consultation duration alone for satisfaction: Since the observed correlation was nearly zero, patient satisfaction should be improved through broader service-quality factors rather than simply increasing consultation length.

Note: These recommendations are analytical interpretations of the results in this notebook and should be validated with operational context before implementation.

🛠️ Technologies & Libraries

Python

Primary programming language used for data analysis.

Pandas

Used for:

Data loading

Cleaning

Transformation

Grouping

Aggregation

Merging

Statistical calculations

Matplotlib

Used to create visualizations such as:

Line charts

Bar charts

Horizontal bar charts

Pie charts

Scatter plots

Stacked bar charts

Jupyter Notebook

Used as the main environment for executing the analysis and documenting
the workflow.

📈 Key Analytical Techniques

The project uses:

Data cleaning

Data validation

Missing-value handling

Duplicate checking

Datetime conversion

Data merging

GroupBy analysis

Aggregation

Percentage calculations

No-show rate analysis

Segmentation

Correlation analysis

Comparative analysis

Data visualization

📁 Repository Structure

Apollo-Healthcare-Appointment-Analytics/
│
├── Appllo.ipynb
├── apollo_appointments_fact.csv
├── apollo_doctors_dim.csv
├── Data Dictionary.docx
└── README.md

💡 Business Value

This project demonstrates how healthcare appointment data can be
converted into actionable business insights.

The analysis can help stakeholders understand:

When appointment demand is highest.

Which patient or appointment segments have higher no-show risk.

How reminders and patient engagement relate to attendance.

Where revenue may be affected by missed appointments.

Which cities and specialties contribute more revenue.

How insurance affects patient expenses.

Where doctor capacity is highly or less utilized.

How waiting time and consultation characteristics relate to service
quality.

🚀 How to Run the Project

1. Clone the repository

git clone <your-github-repository-url>

2. Open the project folder

cd Apollo-Healthcare-Appointment-Analytics

3. Install required libraries

pip install pandas matplotlib jupyter

4. Open the notebook

jupyter notebook Appllo.ipynb

Or open Appllo.ipynb directly in VS Code with the Jupyter extension.

5. Run the notebook

Run the cells from top to bottom so that the datasets, merged
DataFrames, and analysis variables are created in the correct order.

📌 Important Note

The analysis uses the provided Apollo appointment and doctor datasets.
Definitions of fields such as appointment_status, no_show_flag,
revenue_realized, patient_out_of_pocket, and
doctor_utilization_pct follow the project's data dictionary.

👩‍💻 Author

Sudiksha Singhvi

Data Analytics Apollo-Hostipal-Project

⭐ Project Highlights

This project showcases practical skills in:

Python → Data Cleaning → Data Transformation → Exploratory Data
Analysis → Business Analysis → Visualization → Insight Generation
