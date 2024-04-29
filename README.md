# Los Angeles Crime Analysis 🚨

## Overview 🌆

This repository contains an analysis of crime data provided by the Los Angeles Police Department (LAPD). Our objective is to uncover patterns in criminal behavior across Los Angeles, enabling the LAPD to allocate resources more effectively to combat various crimes in different areas.

Los Angeles, a city known for its warm weather and Hollywood glamor, also faces significant challenges related to crime. By leveraging data science 🧑‍💻, we aim to provide insights that help in understanding and addressing these challenges more effectively.

## Dataset 📊

The dataset used in this project (`crimes.csv`) is a modified version of the original data available from Los Angeles Open Data. Below is a brief overview of the data columns:

- `DR_NO`: Division of Records Number - an official file number.
- `Date Rptd`: The date on which the crime was reported.
- `DATE OCC`: The actual date of the crime occurrence.
- `TIME OCC`: Time of the crime in 24-hour military format.
- `AREA NAME`: Name of the LAPD's 21 Geographic Areas or Patrol Divisions.
- `Crm Cd Desc`: Description of the crime committed.
- `Vict Age`: Age of the victim.
- `Vict Sex`: Sex of the victim (F: Female, M: Male, X: Unknown).
- `Vict Descent`: Descent of the victim, with specific codes representing different descents.
- `Weapon Desc`: Description of the weapon used (if applicable).
- `Status Desc`: Current status of the crime investigation.
- `LOCATION`: Street address where the crime occurred.

## File Structure 📁

- `crimes.csv`: The dataset file.
- `analysis.ipynb`: Jupyter notebook containing the data analysis.

## Analysis 🔍

Initial analysis includes identifying the most common times for crimes, the areas with the highest frequency of night crimes, and the distribution of victim ages across different crime types.

To explore the findings, please refer to the Jupyter notebook `analysis.ipynb` in this repository.

## Visualization 📈

We use Python libraries such as Pandas, NumPy, Matplotlib, and Seaborn for data manipulation and visualization. Here's a sample analysis conducted in the project:

```python
#Identifying the number of crimes committed against victims of different age groups.
#Creating age bins
bins = [0, 17, 25, 34, 44, 54, 64, np.inf]
labels = ["0-17", "18-25", "26-34", "35-44", "45-54", "55-64", "65+"]
# Add a new column using pd.cut() to bin values into discrete intervals
#setting right to true to include the upper limit on all defined bins
crimes['Age Group'] = pd.cut(crimes['Vict Age'], bins=bins, labels=labels, right=True)
victim_ages = crimes['Age Group'].value_counts().sort_index()

