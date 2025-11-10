# Global Renewable Energy Analysis

This repository contains all of the files and documentation associated with the **Global Renewable Energy Analysis** project. The aims are to provide data insights in the form of analyses and an interactive dashboard to be used as a tool for stakeholders in order to meet their business requirements, as detailed below.

# Contents

# Project Links
* [ReadMe](https://github.com/KMarsh-code/global-renewable-energy-analysis/blob/main/README.md)
* [Kanban Board](https://github.com/users/KMarsh-code/projects/5)
* [Datasets](https://github.com/KMarsh-code/global-renewable-energy-analysis/tree/main/data)
* [Jupyter Notebooks](https://github.com/KMarsh-code/global-renewable-energy-analysis/tree/main/jupyter_notebooks)
* [Dashboard](https://github.com/KMarsh-code/global-renewable-energy-analysis/tree/main/dashboard)

## Dataset Content
The Global Renewable Energy dataset is freely available on [Kaggle](https://www.kaggle.com/datasets/pralabhpoudel/world-energy-consumption), and is maintained by [Our World in Data](https://ourworldindata.org/energy). This dataset contains a collection of key metrics on energy production and consumption from different sources for countries around the world dating from 1900-2022 (world_energy_consumption_raw.csv). For the purposes of this project, this dataset underwent preprocessing including extraction of key metrics, and was limited to 1982-2022. After this preprocessing, the dataset contained 45 columns and 8508 rows, with one row per country per year (world_energy_consumption_cleaned.csv). Data on production and consumption of solar, wind, hydro, biofuel, nuclear and fossils (coal, oil and gas combined) were used in the analyses and visualisations. A description of each column in the 'cleaned' dataset is available [here](). In addition, a summary dataset of averages and totals over the last five years per country was created for use in analyses and dashboard creation (world_energy_consumption_last5_summary.csv).

## Business Requirements
An environmental NGO is running a campaign for sustainable futures, with the aim of increasing awareness of the state of the renewable energy market globally. This project will create a report on global trends in renewable energy, revealing global leaders in the green energy transition and predicting future trends. This will be in form of an interactive tool that will be shared with the public for engagement and awareness, as well as machine learning models to predict future trends.

## Hypotheses and validation

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


## The rationale to map the business requirements to the Data Visualisations
* List your business requirements and a rationale to map them to the Data Visualisations

## Analysis techniques used
* List the data analysis methods used and explain limitations or alternative approaches.
* How did you structure the data analysis techniques. Justify your response.
* Did the data limit you, and did you use an alternative approach to meet these challenges?
* How did you use generative AI tools to help with ideation, design thinking and code optimisation?

## Summary of findings


## Ethical considerations
* Were there any data privacy, bias or fairness issues with the data?
* How did you overcome any legal or societal issues?

## Dashboard Design
* List all dashboard pages and their content, either blocks of information or widgets, like buttons, checkboxes, images, or any other item that your dashboard library supports.
* Later, during the project development, you may revisit your dashboard plan to update a given feature (for example, at the beginning of the project you were confident you would use a given plot to display an insight but subsequently you used another plot type).
* How were data insights communicated to technical and non-technical audiences?
* Explain how the dashboard was designed to communicate complex data insights to different audiences. 

## Unfixed Bugs
* Please mention unfixed bugs and why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation are not valid reasons to leave bugs unfixed.
* Did you recognise gaps in your knowledge, and how did you address them?
* If applicable, include evidence of feedback received (from peers or instructors) and how it improved your approach or understanding.

## Development Roadmap
* What challenges did you face, and what strategies were used to overcome these challenges?
* What new skills or tools do you plan to learn next based on your project experience? 


## Main Data Analysis Libraries
* Here you should list the libraries you used in the project and provide an example(s) of how you used these libraries.


## Credits 

* In this section, you need to reference where you got your content, media and extra help from. It is common practice to use code from other repositories and tutorials, however, it is important to be very specific about these sources to avoid plagiarism. 
* You can break the credits section up into Content and Media, depending on what you have included in your project. 

### Content 

- The text for the Home page was taken from Wikipedia Article A
- Instructions on how to implement form validation on the Sign-Up page was taken from [Specific YouTube Tutorial](https://www.youtube.com/)
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/)

### Media

- The photos used on the home and sign-up page are from This Open-Source site
- The images used for the gallery page were taken from this other open-source site



## Acknowledgements (optional)
* Thank the people who provided support through this project.