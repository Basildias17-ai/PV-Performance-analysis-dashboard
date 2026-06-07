# PV-Performance-analysis-dashboard

Project Overview
This Power BI dashboard analyzes quality control performance for a pharmacovigilance-style case review process. The goal is to help operations and quality leaders monitor case volume, identify critical and non-critical error trends, find associates below accuracy thresholds, and understand which error categories are driving the majority of quality risk.

The report is designed around a simple business question:

Are teams, associates, and reviewers maintaining the expected quality standards, and where should leadership focus corrective action first?

This is not just a static KPI dashboard. It combines executive-level performance tracking, Pareto analysis, associate defaulter monitoring, reviewer detection metrics, and accuracy segmentation into one report.

Why This Dashboard Is Useful
Quality teams often track total cases and error counts, but that alone does not explain where operational risk is coming from. This dashboard helps convert raw quality data into action by answering:

Which quality metrics are improving or declining month over month?
Which associates are below the required accuracy thresholds?
Which error classifications contribute most to quality failures?
Are critical and non-critical accuracy moving in the right direction?
Are certified associates performing differently from non-certified associates?
Which reviewers are detecting the highest rate of errors?
Which associates are safe performers versus risk-zone performers?
For a quality manager, this dashboard supports faster coaching decisions, better prioritization of audits, and stronger visibility into process risk.

Business Context
The dashboard is built around case-level quality review data. Each case can be evaluated for:

Critical errors
Non-critical errors
Admin errors
No-error/pass status
Associate ownership
Reviewer ownership
Team, location, report type, and date
The dashboard uses accuracy-based performance thresholds:

Critical Accuracy threshold: 80%
Non-Critical Accuracy threshold: 50%
Associates below either threshold are treated as risk/defaulter cases for performance follow-up.

Dashboard Pages
1. Executive Overview
The Executive Overview page gives leadership a quick view of overall quality performance.

Key areas covered:

Total case volume
Critical accuracy
Non-critical accuracy
Pass rate
Defaulter count
Month-over-month and week-over-week movement
Monthly case volume versus critical errors
Quality performance comparison
Error event breakdown
This page is useful for quickly understanding whether quality is stable, improving, or deteriorating.

2. Pareto Analysis
The Pareto Analysis page identifies which error classifications contribute most to total quality issues.

Key areas covered:

Top error classifications driving the majority of issues
Cumulative Pareto contribution
Critical and non-critical error trends over time
Error classification frequency by month and week
Error distribution using supporting visuals such as treemap and donut chart
This page supports root-cause prioritization. Instead of treating all errors equally, it helps focus on the few error types creating the largest quality impact.

3. Associates Performance
The Associates Performance page focuses on associate-level performance and defaulter monitoring.

Key areas covered:

Count of associates below critical accuracy threshold
Count of associates below non-critical accuracy threshold
Certified versus non-certified critical fail rate gap
Top QCer detection rate
Associate performance/defaulter list
Conditional formatting for associates below accuracy thresholds
Top/Bottom associate filtering through the main table setup
This page is useful for coaching, performance reviews, and identifying associates who need targeted intervention.

4. Associate Scatter
The Associate Scatter page compares critical accuracy and non-critical accuracy at associate level.

Scatter logic:

X-axis: Critical Accuracy %
Y-axis: Non-Critical Accuracy %
Bubble: Associate/CPer
Bubble size: Case volume
Bubble color: Team
Safe zone: Critical Accuracy >= 80% and Non-Critical Accuracy >= 50%
Danger zone: Any associate missing either threshold
This page helps quickly identify associates who are strong in both dimensions, weak in both dimensions, or failing one specific accuracy dimension.

Key Metrics Explained
Total Cases
Total number of reviewed cases in the selected filter context.

Critical Errors
Cases where a critical error was identified. Critical errors are high-risk failures and have the highest operational importance.

Critical Accuracy %
Measures how often cases avoid critical errors.

Formula:

Critical Accuracy % = DIVIDE([Total Cases] - [Critical error], [Total Cases])
Non-Critical Errors
Cases where a non-critical error was identified. These errors may not be as severe as critical errors, but they still indicate quality gaps.

Non-Critical Accuracy %
Measures how often cases avoid non-critical errors.

Formula:

Non-Critical Accuracy % = 1 - DIVIDE([Non critical error], [Total Cases])
Pass Rate %
Measures the percentage of cases with no recorded error.

3-Month Defaulter
Identifies associates who remain below the critical accuracy threshold across three consecutive months. This is designed to separate one-off issues from persistent performance risk.

Pareto Error Contribution
Ranks error classifications by frequency and calculates cumulative contribution. This helps identify the top error types responsible for most quality issues.

Certified vs Non-Certified Critical Fail Rate Gap
Compares critical fail rates between certified and non-certified associates. This helps evaluate whether certification status is translating into better quality outcomes.

Top QCer Detection Rate
Identifies the reviewer with the strongest error detection rate in the selected context. This can be used to understand reviewer effectiveness and audit quality.

Data Model
The report is built using a star-schema style model.

Core fact table:

Fact_PV_QC_Cases
Dimension tables:

Dim_Date
Dim_CPer
Dim_QCer
Dim_Team
Dim_Location
Dim_Report_Type
Dim_Error
The model separates case-level review activity from descriptive dimensions, making the report easier to filter, analyze, and extend.

Recommended Slicers
The report works best with a consistent slicer structure across pages.

Recommended common slicers:

Month
Team
Location
Report Type
Recommended page-specific slicers:

Pareto Analysis: Error Classification
Associates Performance: Rank Type / Top-Bottom selector, Certification Status
Associate Scatter: Team, Month, Location
Avoid overloading each page with too many slicers. A professional dashboard should keep the filtering experience focused.

Key Insights This Dashboard Can Surface
This dashboard is designed to surface insights such as:

A team may have high case volume but declining critical accuracy.
A small number of error classifications may be responsible for most quality failures.
Some associates may pass non-critical accuracy but fail critical accuracy, creating hidden risk.
Certification may or may not be reducing critical fail rates.
Reviewers may vary in error detection effectiveness.
Persistent defaulters can be separated from temporary month-level dips.
These insights help leadership move from reporting numbers to taking action.

Business Value
This dashboard is valuable because it supports:

Quality risk monitoring
Associate coaching prioritization
Team performance comparison
Error root-cause analysis
Reviewer effectiveness tracking
Certification impact analysis
Executive reporting for quality operations
In a real quality operations environment, this type of report can reduce manual review effort, improve decision speed, and make performance conversations more evidence-based.

Tools and Skills Demonstrated
This project demonstrates:

Power BI report design
Star-schema data modeling
DAX measure development
Time intelligence analysis
Pareto analysis
Conditional formatting
Threshold-based KPI logic
Associate-level performance segmentation
Scatter plot risk analysis
Operational dashboard storytelling
