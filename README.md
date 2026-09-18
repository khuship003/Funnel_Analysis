#Product Funnel & Retention Analysis#

An end-to-end analysis of a purchase/checkout funnel, built to identify where users drop off between key stages and how retention evolves over time. The project covers the full pipeline: raw event data → SQL/Python cleaning & transformation → Power BI dashboard.

Project Overview

This project analyzes user behavior through a purchase funnel (e.g. view → add to cart → checkout → purchase) to answer:

Where in the funnel are users dropping off the most? What's the overall cart-to-purchase conversion rate? How does daily active user (DAU) volume trend over time? How well do users retain week-over-week after their first activity (Week 0–22 retention)? Tools & Tech Stack SQL – querying and aggregating raw event data (funnel stage counts, conversion calculations) Python – data cleaning, transformation, and preprocessing (pandas) Power BI – interactive dashboard for funnel visualization, DAU trends, and retention analysis Dashboard Preview

Key Components File/Folder Description data/cleaned/ Cleaned datasets used to power the dashboard (funnel stage counts, DAU by day, conversion rates, retention matrix) python/ Jupyter notebooks used for data cleaning and transformation sql/ SQL queries used to compute funnel and retention metrics funnel_analysis.sqbpro SQLite project file used during analysis funnel_dashboard.pbix Final Power BI dashboard file

Note: Raw and large intermediate data files (events.csv, events_clean.csv/.xlsx, funnel_analysis.db) are excluded from this repo via .gitignore due to GitHub's file size limits. See "Data" section below for how to reproduce them.

Overall conversion rate (view → purchase): 5.2% Cart-to-purchase conversion rate: 57.65% Largest drop-off: view → cart (~90.9% of users lost) — by far the biggest leak Week 1 retention: 3.1%, dropping to 0.65% by Week 4 DAU trend: rises to a peak (~4,300) around Nov–Dec 2020, then declines and levels off around 2,200–3,200

How to Reproduce Clone this repo Place raw event data in data/raw/ (see Data section) Run the notebooks in python/ to clean and transform the data Run the queries in sql/ to generate funnel and retention tables Open funnel_dashboard.pbix in Power BI Desktop to view/refresh the dashboard

The raw dataset used for this analysis is not included in this repo due to file size constraints. About Dataset - This file contains behavior data for 5 months (Oct 2019 – Feb 2020) from a large electronics online store.

Each row in the file represents an event. All events are related to products and users. Each event is like many-to-many relation between products and users.
