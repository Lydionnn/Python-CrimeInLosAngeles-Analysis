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

We use Python libraries such as Pandas, NumPy, Matplotlib, and Seaborn for data manipulation and visualization.

## Key Findings 🌟

Our in-depth analysis of the Los Angeles crime data has yielded several important insights that provide a nuanced understanding of the dynamics of criminal activities in the city. Here are the enhanced key findings:

### Peak Crime Times
- **Unexpected Midday Peak**: Contrary to common perceptions that associate higher crime rates with nightfall, our data reveals that the peak hour for crime occurs at noon, with 6,462 reported incidents. This midday spike might be linked to the bustling urban activity during lunch hours when streets are crowded, and people are less vigilant, presenting ample opportunities for crimes such as theft and pickpocketing. Businesses and law enforcement may need to consider bolstering their presence and surveillance during these hours to mitigate these risks.

### Night-Time Crime Hotspot
- **Central LA's Elevated Risk**: The Central area of Los Angeles reports the highest frequency of crimes during the nighttime window of 10 PM to 4 AM, with 3,312 incidents. This region, likely dense with nightlife and commercial activities, demands targeted interventions. Enhanced street lighting, increased patrols, and community policing initiatives could be effective in reducing crime rates during these vulnerable hours.

### Demographic Vulnerabilities
- **Age-Specific Risk Profiles**: Our analysis highlights that adults in their late twenties to early forties (26-34 and 35-44 years old) experience the highest frequencies of crime, with 47,470 and 42,157 incidents respectively. This vulnerability may be attributed to this demographic's active engagement with public life, including nightlife, commuting, and social activities. Public safety campaigns and preventive measures could be tailored to raise awareness and protect these age groups, potentially integrating technology solutions like safety apps or emergency response features.

### Predominant Crime Types
- **Rising Concern of Identity Theft**: Strikingly, identity theft dominates the crime landscape for the 26-34 and 35-44 age groups, with over 6,000 cases reported in each. The digitalization of personal transactions and the prevalence of online financial activities may be exacerbating this trend. Efforts to combat this crime could include wider education on digital safety, robust cyber security measures for personal data, and stronger regulatory frameworks to protect personal information.

### Most Frequent Night-Time Crime
- **Assault Patterns After Dark**: 'BATTERY - SIMPLE ASSAULT' emerges as the predominant crime committed after dark, recording 6,177 instances. This pattern indicates a pressing need for strategies focused on preventing violent crimes during night hours. Initiatives could include setting up safe zones, enhancing public transportation security during late hours, and running community engagement programs that focus on conflict resolution and violence prevention.

By delving deeper into these findings, we aim to not only understand the "where" and "when" of crime occurrences but also to spark actionable strategies that could significantly enhance the safety and quality of life for Los Angeles residents. The data drives home the importance of adaptive public safety strategies that respond dynamically to the identified patterns and challenges.




## Featured Analysis: Night-Time Crime Hotspot 📈

One critical aspect of our project is understanding the spatial and temporal dynamics of crime. Below is a sample analysis that illustrates how we identify geographic areas most affected by crime during specific night hours. This snippet is part of a larger suite of tools and analyses used throughout our project to derive actionable insights.

```python
import pandas as pd

# Load and prepare the dataset
crimes = pd.read_csv("crimes.csv", parse_dates=["Date Rptd", "DATE OCC"], dtype={"TIME OCC": str})

# Filter the data to include only crimes that occurred between 10 PM and 3:59 AM
filtered_time_df = crimes[(crimes['TIME OCC'] >= '2200') | (crimes['TIME OCC'] <= '0359')]

# Count occurrences by area within the specified time window
area_counts = filtered_time_df['AREA NAME'].value_counts()

# Identify the area with the highest frequency of night crimes
most_common_area = area_counts.idxmax()
most_common_count = area_counts.max()

print(f"The most common area during 22:00 to 03:59 is {most_common_area} with {most_common_count} occurrences.")

