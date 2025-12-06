Car Market Data Analysis Project

  Project Overview

This project analyzes a vehicle dataset to uncover business-relevant insights related to pricing, mileage, fuel efficiency, and inventory composition. Using Python and pandas, we answer key questions that could help a dealership, manufacturer, or market analyst make data-driven decisions.

The analysis focuses on:

Transmission types and vehicle usage

Brand pricing strategies

Inventory distribution by brand

Electric vehicle adoption

High-mileage vehicle prevalence

Dataset Description

The dataset used for this project is car_price_prediction_.csv.

Columns Used
Column Name	Description
Brand	Vehicle manufacturer
Year	Model year
Engine Size	Engine displacement (proxy for fuel efficiency)
Fuel Type	Petrol, Diesel, or Electric
Transmission	Manual or Automatic
Mileage	Total miles driven
Condition	Vehicle condition
Price	Vehicle price
Model	Vehicle model

🛠 Tools & Libraries

Python 3

pandas – data manipulation

matplotlib – data visualization

numpy – numeric operations

🔍 Analysis Questions & Methodology
1️⃣ What is the average mileage for each transmission type?

Business relevance:
This insight helps determine whether manual or automatic vehicles tend to experience more wear and usage.

Approach:

Group data by Transmission

Calculate the mean of Mileage

df.groupby("Transmission")["Mileage"].mean()


Visualization was used to communicate results clearly to non-technical audiences.

2️⃣ What is the average price of cars by brand?

Business relevance:
Understanding brand pricing helps identify premium vs. budget manufacturers.

Approach:

Group by Brand

Calculate average Price

df.groupby("Brand")["Price"].mean().sort_values()


This allows brand-level price comparison and supports pricing strategy analysis.

3️⃣ Which brands produce the most vehicles in the dataset?

Business relevance:
Brands with high representation may indicate strong market presence or higher inventory volume.

Approach:

Count occurrences of each Brand

df["Brand"].value_counts()


This provides a quick view of brand dominance within the dataset.

4️⃣ How many electric vehicles does each brand have, and what is their average engine size?

Business relevance:
This measures:

Electric vehicle adoption by brand

Fuel efficiency using engine size as a proxy

Approach:

Filter dataset for electric vehicles

Count electric vehicles per brand

Calculate average engine size per brand

electric_count = df[df["Fuel Type"] == "Electric"].groupby("Brand").size()
avg_engine = df.groupby("Brand")["Engine Size"].mean()


A clustered column chart was used to compare both metrics side-by-side.

5️⃣ What percentage of cars are above a certain mileage threshold (e.g. 100,000 miles)?

Business relevance:
High-mileage vehicles may require more maintenance and affect resale value.

Approach:

Define mileage threshold (100,000 miles)

Calculate percentage of vehicles exceeding it

threshold = 100000
percentage = (df["Mileage"] > threshold).mean() * 100


This converts a logical condition into a clear, actionable percentage.

📊 Visualization Strategy

The project uses:

Column charts for categorical comparisons

Clustered columns for multi-metric brand analysis

Labeled bars to clearly display numeric values

All visuals are designed to support business presentations and reporting, not just technical exploration.

✅ Key Insights (Example)

Automatic vehicles tend to show different mileage patterns than manual ones.

Certain brands consistently command higher prices.

Electric vehicles are concentrated among specific brands.

A meaningful percentage of vehicles exceed 100,000 miles, which impacts inventory strategy.

📁 Project Structure
📦 car-market-analysis
 ┣ 📄 car_price_prediction_.csv
 ┣ 📄 analysis.py
 ┣ 📄 README.md

🚀 Conclusion

This project demonstrates how Python and data analysis can be applied to real-world business questions using a structured process:

Define the question

Select relevant columns

Apply grouping or filtering

Visualize results

Interpret findings in business terms

These techniques are transferable to marketing analytics, operations, pricing strategy, and sustainability reporting.
