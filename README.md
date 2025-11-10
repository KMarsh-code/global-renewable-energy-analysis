# Global Renewable Energy Analysis

This repository contains all of the files and documentation associated with the **Global Renewable Energy Analysis** project. The aims are to provide data insights in the form of analyses and an interactive dashboard to be used as a tool for stakeholders in order to meet their business requirements, as detailed below.

# Contents

* [Dataset Content](#dataset-content)
* [Business Requirements](#business-requirements)
* [Hypotheses and Validation](#hypotheses-and-validation)
* [Project Plan](#project-plan)
* [Rationale](#the-rationale-to-map-the-business-requirements-to-the-data-visualisations)
* [Analysis Techniques](#analysis-techniques-used)
* [Conclusions and Further Insights](#conclusions-and-further-insights)
* [Ethical Considerations](#ethical-considerations)
* [Dashboard Design](#dashboard-design)
* [Unfixed Bugs](#unfixed-bugs)
* [Development Roadmap](#development-roadmap)
* [Main Libraries](#main-libraries)
* [Credits](#credits)
* [Acknowledgements](#acknowledgements)

# Project Links
* [ReadMe](https://github.com/KMarsh-code/global-renewable-energy-analysis/blob/main/README.md)
* [Kanban Board](https://github.com/users/KMarsh-code/projects/5)
* [Datasets](https://github.com/KMarsh-code/global-renewable-energy-analysis/tree/main/data)
* [Jupyter Notebooks](https://github.com/KMarsh-code/global-renewable-energy-analysis/tree/main/jupyter_notebooks)
* [Dashboard](https://github.com/KMarsh-code/global-renewable-energy-analysis/tree/main/dashboard)

## Dataset Content
The Global Renewable Energy dataset is freely available on [Kaggle](https://www.kaggle.com/datasets/pralabhpoudel/world-energy-consumption), and is compiled and maintained by [Our World in Data](https://ourworldindata.org/energy). This dataset contains a collection of key metrics on energy production and consumption from different sources for countries around the world dating from 1900-2022 (world_energy_consumption_raw.csv). For the purposes of this project, this dataset underwent preprocessing including extraction of key metrics, and was limited to 1982-2022. After this preprocessing, the dataset contained 45 columns and 8508 rows, with one row per country per year (world_energy_consumption_cleaned.csv). Data on production and consumption of solar, wind, hydro, biofuel, nuclear and fossils (coal, oil and gas combined) were used in the analyses and visualisations. A description of each column in the 'cleaned' dataset is available [here](). In addition, a summary dataset of averages and totals over the last five years per country was created for use in analyses and dashboard creation (world_energy_consumption_last5_summary.csv).

## Business Requirements
An environmental NGO is running a campaign for sustainable futures, with the aim of increasing awareness of the state of the renewable energy market globally. This project will create a report on global trends in renewable energy, revealing global leaders in the green energy transition and predicting future trends. This will be in form of an interactive tool that will be shared with the public for engagement and awareness, as well as machine learning models to predict future trends.

## Hypotheses and Validation

**H1: Historical growth in renewables is linked to a country's gross domestic product (GDP)**. Countries with higher GDP have slower growth in fossil fuel consumption (they already peaked) and faster growth in renewables. In contrast, emerging economies (those with lower GDP) still show strong growth in fossil fuel consumption.

Testing and visualisations:

- Jupyter Notebook: Scatterplot of fossil and renewable energy percentage annual growth against GDP per country (averaged over the last 5 years). OLS regression to test hypothesis of fossil/renewable growth relationship with GDP.

- Dashboard: Dynamic scatterplot of fossil fuel consumption against GDP per sub-region, with a play axis of year to show changes over time.

**H2: Leaders and laggers in the green energy transition**. Renewable production has increased over the last decade, accelerating the transition to green energy. The rate of this growth varies geographically, with some countries leading the way in the green energy transition and other countries falling behind.

Testing and visualisations:

- Jupyter Notebook: Histograms of share of electricity production per energy type (averaged over the last 5 years per country). Identification of outlier countries, and barplots of 'leaders' and 'laggers' per energy type.

- Dashboard: Barplots of percentage share of energy production per country (averaged over the last 5 years), showing all countries (not just leaders/laggers).

**H3: Forecasting renewable production for the next decade**. Renewables have been rising over the last two decades, with growth in some renewables like solar and wind especially fast in the last 10 years. Production of renewables will continue to increase over the next ten years, accelerating the shift from fossil to green energy. 

Testing and visualisations:

- Jupyter Notebook: Forecasting global trends in energy production per renewable type over the next 10 years using machine learning methods (Recurrent Neural Network). 

- Dashboard: Piechart of percentage share in energy production per energy source (including fossil fuel). Line graph of energy production over time per renewable type. 

## Project Plan

* **Data cleaning and preprocessing** was conducted in Python to improve the relevance and quality for downstream analyses. The code for this is available [here](https://github.com/KMarsh-code/global-renewable-energy-analysis/blob/main/jupyter_notebooks/1_renewable_energy_data_cleaning_eda.ipynb), the cleaned dataset is stored [here](https://github.com/KMarsh-code/global-renewable-energy-analysis/blob/main/data/world_energy_consumption_cleaned.csv) and the 5-year summary dataset is [here](https://github.com/KMarsh-code/global-renewable-energy-analysis/blob/main/data/world_energy_consumption_last5_summary.csv).
* **Exploratory Data Analysis (EDA)** was performed in Python to provide key summary statistics per vairable, to understand their distributions and to obtain initial insights of variable correlations and broad patterns. The code for this is available [here](https://github.com/KMarsh-code/global-renewable-energy-analysis/blob/main/jupyter_notebooks/1_renewable_energy_data_cleaning_eda.ipynb).
* **Hypothesis testing** was performed in Python, which enabled advanced tools such as machine learning (RNN) for forecasting to be used to meet business requirements. The code for these analyses is available [here](https://github.com/KMarsh-code/global-renewable-energy-analysis/blob/main/jupyter_notebooks/2_renewable_energy_hypothesis_testing.ipynb).
* A **Dashboard tool** was created using PowerBI, in order to meet the business requirements of public engagement. PowerBI was chosen as it is a popular dashboarding tool, with advanced but intuitive data storytelling facilities. The dashboard is publicly available on the PowerBI platform [here](https://app.powerbi.com/groups/me/reports/e044f3b9-ae9e-41b9-8a21-ea4ddea0c84e/914eeb55aceefcad59e5?experience=power-bi).


## Rationale
The business requirements were two-fold: **1)** forecast future trends in global renewables and **2)** create an interactive tool providing insight into the state of the global energy market aimed at increasing public awareness. 

The following visualisations were used to meet these business requirements:
* Line graphs show historic trends and 10-year forecasts in global energy production per renewable type (predictions from machine learning models).
* Piechart showing share of electricity production per energy source (including fossil fuel) gives an overview of the state of the energy market.
* Barplots highlight the countries that are 'leaders' in the green energy transition.
* Scatterplots show the relationship between a country or region's economic state (GDP) and investment in renewables, giving additional context.

## Analysis Techniques
All data analyses were performed in Python (version 3.12.10) via VScode. 

Data Analysis Methods:
- OLS regression was used to test Hypothesis 1 (growth in renewables/fossils vs GDP). 
- Identification of outliers was done by calculating 1.5*interquartile range per energy type
- Forecasting renewable production was done using Recurrent Neural Networks, specifically long short-term memory (LSTM) models which are particularly suited to time series forecasts as they retain memory over longer periods. 

Data Limitations:

A lot of data was missing for certain years and/or countries. The analyses and dashboard therefore focussed on years with more complete records (1980's onwards), and for some analyses (e.g. forecasts) global trends were considered by summing available data across countries.

Generative AI (Copilot) was used for code completion and in-line fixes of errors. The chat function was used to provide suggestions for optimising forecast models.

## Conclusions and Further Insights

**H1:** The analyses show that growth in fossil and renewable energy is not strongly linked to a country's GDP (in terms of averages per country over the last 5 years). Some countrys show more overall growth in fossil/renewables than others. For instance, Indonesia and Vietnam have shown the highest average growth in fossil fuel over the last 5 years (between 5-6% per annum on average). Indonesia also has some of the higest average annual growth in renewables of over 20%, along with countries such as Israel, Iraq and Netherlands.

**H2:** Different sets of countries were identified as leaders in the transition to green energy, depending on the type of renewable (based on the average share of energy production per country over the last 5 years). The leaders for each energy type were; The Cook Islands (Solar), Denmark (Wind), Eswatiti (Biofuel), France (Nuclear). Multiple countries were 100% reliant on hydropower for their energy production (Bhutan, Central African Republic, Lesotho, Paraguay, Democratic Republic of Congo, Albania and Nepal).

**H3:** There has been an increase in renewable energy production over the last two decades, with this growth set to continue over the next 10 years. The models built here predict growth in each renewable type, despite sudden drops in production for all renewables between 2021-2022 (possibly covid-related). Hydropower is dominant, with production set to increase to approximately 240,000 kWh by 2032. Wind production is predicted to overtake nuclear power, with estimates of 150,000 kWh for wind vs 63,000 kWh for nuclear in 2032. This is due to the decrease in nuclear production since the early 2000's, which will take the next 10 years to recover. Biofuel production has been steadily increasing since 1990, and will continue this gradual increase to approxiamte 25,000 kWh by 2032. In contrast, solar production has grown exponentially since 2010 and will overtake biofuel production with estimates of 90,000 kWh production by 2032.

**Further Insights**

The link between growth in fossil/renewables and GDP (H1) could be further explored by testing if this relationship depends on sub-region. This could highlight the differences between developed and emerging economies in terms of the link between energy consumption/growth and GDP.

The forecast models (H3) could provide further insights by adding the following to the analyses:
- Further model optimisation to capture most recent trends. Perhaps removing the last year (2022) if it is an anomaly due to covid (this would require further investigation and validation).
- Add more independent variables to the models to aid predictions, such as predicting growth per sub-region.
- Combine growth in production of all renewables into a multiple time series to improve forecasts.

Further insights could be provided by obtaining data on renewable policies and targets per country, as well as investment for building capacity. 


## Ethical Considerations

The data is publicly available on Kaggle and does not contain any personally identifiable data.

During data cleaning, a dictionary of countries with the continent and sub-region they belong to was created according to the UN classification (https://unstats.un.org/unsd/methodology/m49/). These groupings are for statistical purposes and do not imply any political affiliations. 

## Dashboard Design

**1. Main Dashboard**
* Title: Global Renewable Energy 1982-2022
* Cards: Average % annual growth in each energy source
* Piechart: % share of electricity generation per energy source
* Scatterplot: Fossil fuel consumption vs GDP per sub-region. Includes a play axis of year for enhanced understanding of the temporal dynamics of this relationship.
* Barplots: Average % share of total energy production per country, per energy source.
* Line chart: Energy production per capita over time, with one line for each renewable. Includes buttons to show trends per continent.
* Filters: Year slider and drop-down selection of continent/sub-region to allow drill-down.
* Reset button to remove all filters and selections


**2. Fossil fuel vs. GDP**

Focus: Displays the correlation between fossil fuel consumption (kWh) per capita and GDP per geographic sub-region.

Elements: Scatter plot with play axis of year, datapoints coloured and labelled by sub-region. GDP is log-transformed to enhance visibility. 

**3. Green Leaders**

Focus: Shows which countries are leading in terms of % share of their energy production coming from each type of renewable.

Elements: Barplots, one per renewable type, showing % share of total energy production per country (averaged over the last 5 years). Bars are coloured by renewable type and ordered by decreasing % share.

**4. Renewable Growth**

Focus: Shows trends in renewables over time (energy production per capita).

Elements: Line chart with trendlines per renewable type. Colour= renewable type. Buttons allow drill-down to see trends per continent.

**5. Geographic Patterns**

Focus: Shows % share of electricity production per energy source, including fossil fuels.

Elements: Piechart of % share in electricity production. Colour=energy source. Drop-down selection of continent and sub-region and a slider for year allows drill-down of geographic and temporal patterns.

**Communication Strategy:**

The dashboard was designed with a clear flow of information, consistent colour scheme, clear titles per section and filters to allow drill-down. The charts on the main dashboard were split into separate pages to allow the audience to focus on one at a time, for a clearer viewing experience. Cards were placed at the top of the main dashboard to give quick summary statistcs in an easy-to-see position.

## Unfixed Bugs

The dashboard design initially included a global map showing share of energy production from renewables, with a play axis of year to visualise spatio-temporal trends. However, map features were not enabled on the PowerBI account and therefore were not accessible. Instead, a piechart of share in energy production was combined with a drop-down selection of geographic area and a slider for year.

In addition, the dahsboard line chart of renewable production over time had multiple lines, one for each renewable. This meant that forecasting trends on the dashboard tool was not included, as forecasting with multiple lines is not yet possible on PowerBI. However, line charts showing the forecast predictions from the RNN models were generated using Python visualisations, and therefore the business requirements were still met.

## Development Roadmap
* What challenges did you face, and what strategies were used to overcome these challenges?
* What new skills or tools do you plan to learn next based on your project experience? 

Optimisation of the RNN models proved challenging as this was a new technique. A combination of Copilot suggestions and web searches was used to try to optmise the models. In the future, I would like to make further improvements to these models, and learn how to build a model of multiple time series using renewables combined together. 

## Main Libraries

Data cleaning and EDA:
- pandas
- numpy

Visualisations:
- matplotlib
- seaborn
- plotly

Machine learning:
- scikitlearn
- pytorch

## Credits 

- Code institute learning materials were used as a basis for the data analyses in this project. In addition, Code Institute GitHub repository template was used to form the basis of this repository.
 - This tutorial was followed for time series forecasting with RNN in Pytorch: https://www.geeksforgeeks.org/data-analysis/time-series-forecasting-using-pytorch/
 - This page was followed for hyperparameter tuning: https://stackoverflow.com/questions/77007252/how-to-perform-hyperparameter-tuning-of-lstm-using-gridsearchcv
- Further optimisations for each forecast model were done using Copilot chat suggestions.

## Acknowledgements

Thank you to the Code Institute instructors and fellow coursemates for their encouragement and companionship during this process.
