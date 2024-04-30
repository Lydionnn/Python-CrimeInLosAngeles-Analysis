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
- `crimes_la_analysis.ipynb`: Jupyter notebook containing the data analysis, including new insights on crime timing and distributions.

## Analysis 🔍

Initial analysis includes:
1. Identifying the most common times for crimes.
2. Determining the areas with the highest frequency of night crimes.
3. Analyzing the distribution of victim ages across different crime types.
4. Exploring the relationship between the types of crimes committed and the ages of the victims.
5. Assessing the most frequent crimes committed after sundown, to potentially redistribute resources for enhanced night-time policing.

Please refer to the Jupyter notebook `crimes_la_analysis.ipynb` in this repository to explore the detailed findings.

## Visualization 📈

We use Python libraries such as Pandas, NumPy, Matplotlib, and Seaborn for data manipulation and visualization. The analyses include:

### Hourly Crime Distribution
Exploring the distribution of crimes by hour to pinpoint peak crime times:

```python
# Visualization of crime frequency by hour
plt.figure(figsize=(12, 6))
hour_by_day_counts.plot(kind='bar', color='cyan')
plt.xlabel('Hour of the Day')
plt.ylabel('Number of Crimes')
plt.title('Crime Frequency by Hour')
plt.xticks(rotation=0)
plt.show()

