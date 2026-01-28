# my-first-project1
# ==============================
# Retail Sales Analysis Project
# ==============================

# Import required libraries
# Pandas -> data handling
# Matplotlib -> data visualization
import pandas as pd
import matplotlib.pyplot as plt

# ------------------------------
# Load Dataset
# ------------------------------
# Reading CSV file from data folder
df = pd.read_csv("data/retail_sales.csv")

# Display first few rows to understand data
print("Dataset Preview:")
print(df.head())

# ------------------------------
# Basic Data Understanding
# ------------------------------
# Summary statistics of numerical columns
print("\nStatistical Summary:")
print(df.describe())

# ------------------------------
# Business KPIs Calculation
# ------------------------------
# Total Sales and Profit (Key Performance Indicators)
total_sales = df["Sales"].sum()
total_profit = df["Profit"].sum()

print("\nTotal Sales:", total_sales)
print("Total Profit:", total_profit)

# ------------------------------
# Sales Analysis by Category
# ------------------------------
# Grouping data to analyze which category performs best
category_sales = df.groupby("Category")["Sales"].sum()

# Bar chart for category-wise sales
category_sales.plot(kind="bar")
plt.title("Total Sales by Product Category")
plt.xlabel("Category")
plt.ylabel("Sales")
plt.tight_layout()
plt.show()

# ------------------------------
# Profit Analysis by Region
# ------------------------------
# Understanding which region is most profitable
region_profit = df.groupby("Region")["Profit"].sum()

# Pie chart for region-wise profit contribution
region_profit.plot(kind="pie", autopct="%1.1f%%")
plt.title("Profit Distribution by Region")
plt.ylabel("")  # Remove unwanted label
plt.tight_layout()
plt.show()
