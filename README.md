# MIST 4610 Group Project 2

## Team Name
4610Fa24Group7 - 10 Leading Causes of Death in the US

## Team Members

- Robin Rubchenko [@robinrubchenko](https://github.com/robinrubchenko)
- James Solomon [@jamessolomon03](https://github.com/jamessolomon03)
- Kylee Hobbs [@kylee-hobbs](https://github.com/kylee-hobbs)
- Madeline Dodson [@mpd62417](https://github.com/mpd62417)

## Dataset Description
Our dataset details the top ten causes of death in the United States from 1997 to 2017. There are 10,869 rows of data obtained by the National Center for Health Statistics (NCHS) based on information from death certificates. There are five columns in the dataset: Year, Cause of Death, State, Deaths, and Death Rate. Causes of death are classified by the International Classification of Diseases, and the top ten diseases in the United States were determined by the Tenth Revision (ICD–10).

1. Year – The year in which the death certificates were collected.
2. Cause – The name of the cause of death.
3. State – The state where the deaths were recorded.
4. Deaths – The total number of deaths from the specified cause in the given year and state.
5. Death Rate (per 100k Age Adj.) – The age-adjusted death rate (per 100,000 population) calculated using the U.S. census standard population to account for differences in age distribution.

# Question 1
### What are the leading causes of death in the US and do they differ by state?

<img width="1300" alt="1 1 Heatmap" src="https://github.com/user-attachments/assets/9a1dddf4-f63f-4c1a-945c-918e58129fbe">

### Heatmap Analysis & Results

This heatmap visualizes the causes of death that are responsible for the highest number of deaths among Americans. Heart disease and Cancer account for more than 50% of deaths among the top ten causes, with chronic lower respiratory disease (CLDR) following in third. It also allows us to recognize the disproportionately large impact that cancer and heart disease have on overall mortality. Based on these findings, we decided to primarily focus our analysis on these two.

<img width="1300" alt="1 2 Cancer Map" src="https://github.com/user-attachments/assets/2c9de95c-372f-4a3b-a1e3-f0742f1d5639">
<img width="1301" alt="1 2 HD Map" src="https://github.com/user-attachments/assets/8d4f8c23-1e02-4f94-a49d-1e3d7f6c1ef9">

### Area Map Analysis & Results
Our area maps of the United States visualize how the death rates of heart disease and cancer vary by each state in a given year. Shown above are varying death rates per 100k for cancer and heart disease per state in 2017. This was filtered by the cause, state, and year, and each color represents the severity of the death rate in each state. For heart disease, the dark red states like Oklahoma Alabama, and Mississippi, had the leading death rates in 2017. When looking at cancer, we see a similar overlap with the darker blue states like Mississippi and Oklahoma, which had the highest death rates in 2017 too. The purpose of these maps was to have a better understanding of which areas are grappling with these diseases the most.

<img width="1299" alt="1 3 Top 3 Bar Graph" src="https://github.com/user-attachments/assets/a11c094e-b8e5-452d-bbf6-ff21f321eb8a">

### Top Three Bar Graph Map Analysis & Results
Our final analysis is a bar graph depicting the top three yearly causes of death by rate in 3 states in the US. We chose Georgia, California, and New York, as they are three high-population states in different areas of the country. We did this through two calculated fields. The first calculated field we created was converting the number of deaths per year per 100k into a true percentage. This is why the percentages are so small in comparison to a traditional death rate, it is only calculating how many people are dying in a given year per 100k from these diseases in each state. We then created a calculated field and used the rank function to rank the leading causes of death per 100k. The formula for this was RANK(AVG([Death Rate per 100K -- Age Adj.]), 'desc'). The purpose of this graph is to visualize the death rates in a few states As you can see, there is a commonality in cancer and heart disease death rates which we found interesting and wanted to look further into.

### Overall Importance of Question 2
In conclusion, these three graphs give us a better understanding of the state of public health in America. This information could be useful for the government, health agencies, insurance companies, and doctors to promote general health awareness and understand which states to target with public health campaigns. Specifically, this can allow the government to target specific regions with high death rates for treatable diseases and best allocate regional funding for medical research.

# Question 2
### How are cancer and heart disease deaths and death rates trending, and how might they be related?

<img width="1300" alt="2 1 Cancer Trends" src="https://github.com/user-attachments/assets/690ccfa1-7d1c-48d1-9beb-7d15a19da8a2">

### Cancer Trends Analysis & Results
After analyzing the descriptive visualizations we created to answer question one, for question two we decided to focus on cancer and heart disease deaths and death rates as they consistently prove themselves to be the top two leading causes of death for the US as a whole and for each state individually. More specifically, looking at the deaths and death rate trends of cancer for the US as a whole from 1999 to 2017 revealed an interesting pattern. As a quick reminder, the age-adjusted death rate is a measure that adjusts the overall deaths for an aging population, offering a clearer view of trends over time. The light blue line represents this age-adjusted death rate and is decreasing over time, implying that improvements have been made to cancer prevention, treatment, and detection. However, total deaths over the same course of time increased, as represented by the dark blue line. Since the total deaths value is not age-adjusted, this tells us that although overall cancer death rates have declined, demographic factors, such as a growing and aging population, have led to a persistent increase in total deaths. This is primarily because there is a growing number of cancer cases among older populations. Overall, a decreasing age-adjusted death rate indicates that progress has been made in managing cancer relative to population age, but the contradictory increase in total deaths can be attributed to demographic factors, such as population growth and aging.

<img width="1300" alt="2 2 HD Trends" src="https://github.com/user-attachments/assets/b283a4d4-11fd-4064-a7c9-8653530fed8b">

### Heart Disease Trends Analysis & Results
We then created a parallel visualization for heart disease deaths and observed a decreasing death rate, represented by the light red line. Like the decline in cancer's age-adjusted death rate, this trend suggests that detection, prevention, and treatment measures for heart disease have significantly improved over time. Specifically, people may be leading healthier lifestyles with more exercise, improved diets, and reduced smoking, while also managing risk factors such as hypertension, high cholesterol, and diabetes more effectively. Notably, unlike the trends observed for cancer, the total number of heart disease deaths has also declined over the same period. This indicates that fewer people are developing heart disease in the first place due to better preventive measures. Even with an aging population, medical advancements have enabled individuals to live longer and manage heart disease more effectively. Improved treatments and technologies have extended lifespans and enhanced the quality of life for those with heart disease. Overall, heart disease is becoming both less prevalent and less fatal, reflecting significant progress in public health and medical care.

<img width="1300" alt="2 3 Correlation" src="https://github.com/user-attachments/assets/0f4234d3-0269-4efa-9a45-1c43a6b49b0a">

### Correlation Analysis & Results
We started by creating two calculated fields that isolated the death rates for both cancer and heart disease. For example, our formula for heart disease was IF [Cause] = "Heart disease" THEN [Death Rate per 100K -- Age Adj.] END. We then marked state labels, colored rates, and sized SUM(Deaths) to provide a rough population indicator. Analyzing the results, the spread along each line may imply systemic health disparities between states with those clustering in the upper-right having high rates for both. By comparing 1999 and 2017, we also see a general shift down the line over time, indicating that public health interventions, lifestyle changes, and or healthcare improvements have made an impact. With an r-squared of roughly 0.56 for both, this moderate correlation suggests that cancer and heart disease may be affected by common risk factors, underlying socioeconomic disparities, or environmental influences. For example, smoking, poor diet, physical inactivity, and alcohol consumption are risk factors for both diseases. Additionally, socioeconomic disparities such as reduced access to healthcare and healthy food can elevate death rates for both diseases. A poor diet of ultra-processed, unhealthy foods may heighten one’s risk for heart disease while simultaneously exposing them to chemicals that increase one’s risk of cancer. Environmentally, pollution and exposure to carcinogens and particulates as well as genetic predispositions can influence both rates as well. With this in mind, highlighting specific states allows policymakers to focus on correlation outliers and investigate localized factors. For example, Oklahoma may benefit from additional localized research since they are in the top right cluster for both years. Our analysis may suggest the need for integrated preventions and treatments, optimizing healthcare results. With more time, it may be beneficial to explore each possible combination of disease correlation to identify more potential opportunities for efficient treatment and research efforts. 

### Overall Importance of Question 2
While we recognize that cancer and heart disease are fundamentally different diseases with distinct treatments, they remain the two leading causes of death across the United States. This prompted us to explore how death rates from these diseases have evolved and how they compare to one another. By examining the progress made in reducing heart disease deaths, we can investigate whether similar strategies could be adapted to combat cancer, potentially reducing cancer-related deaths in the future. Additionally, analyzing the correlation between the two death rates at the state level over time highlights disparities in healthcare measures and treatments. This approach helps identify states where healthcare systems may be underperforming, offering opportunities to improve outcomes for their populations. 

## Manipulations Applied
We excluded the column “113 Cause Name” which seemed to represent some sort of ID for each cause. We also filtered out the “All Causes” cause to make it easier to filter by cause within each visualization. Otherwise, our data was already clean of any duplicates, redundancies, or null values. The three calculated fields we created are explained in their respective visualizations.

## Presentation File
[Project2_Presentation_11:20.pdf](https://github.com/user-attachments/files/17906337/Project2_Presentation_11.20.pdf)

## Tableau Packaged Workbook
File uploaded in eLC dropbox
