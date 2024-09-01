# Global Agricultural Production and Population Analysis

## Overview

This project analyzes global agricultural production relative to population data over time. It uses Python to process data on agricultural production by category, region, and country, as well as global and continental population data. The goal is to visualize trends and relationships between food production and population growth.

## Table of Contents

- [Overview](#overview)
- [Data Sources](#data-sources)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
  - [1. Loading the Data](#1-loading-the-data)
  - [2. Data Cleaning and Preparation](#2-data-cleaning-and-preparation)
  - [3. Data Visualization](#3-data-visualization)
- [Key Features](#key-features)
- [File Descriptions](#file-descriptions)
- [License](#license)

## Data Sources

The project uses the following datasets which are stored in the Resource folder:

1. **World Population Data**: `world_population_data.csv`
2. **Agricultural Production Data**: `Production_Crops_Livestock_E_All_Data.csv`
3. **World Population by Year**: `API_SP.POP.TOTL_DS2_en_csv_v2_3401680.csv`
4. **Agricultural Categories Mapping**: `Lists_test.csv`

Links to data
- https://www.kaggle.com/datasets/sazidthe1/world-population-data 
- https://www.fao.org/faostat/en/#data/QCL 
- https://www.census.gov/data-tools/demo/idb/#/dashboard?COUNTRY_YEAR=2024&COUNTRY_YR_ANIM=2024&menu=countryViz&CCODE_SINGLE=**


## Requirements

- Python 3.8+
- The following Python libraries are required:
  - pandas
  - matplotlib
  - numpy
  - pathlib
  - prophet
  - datetime
  - seaborn
  - from scipy.stats import pearsonr, spearmanr
  - ipywidgets
  - jupyter (optional, for interactive widgets)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Corey-Holton/Project1.git
   cd your-repository
## Usage
## 1. Loading the Data
Load the required datasets using pandas:

import pandas as pd
from pathlib import Path

## Load datasets
    world_population = pd.read_csv(Path("Resources/world_population_data.csv"))
    agri_data = pd.read_csv(Path("Resources/Production_Crops_Livestock_E_All_Data.csv"), encoding='ISO-8859-1', low_memory=False)
    world_population_all_years = pd.read_csv(Path("Resources/API_SP.POP.TOTL_DS2_en_csv_v2_3401680.csv"))
    category_ag_data = pd.read_csv(Path("Resources/Lists_test.csv"))

## 2. Data Cleaning and Preparation
-   Data Cleaning: Drop unnecessary columns, rename columns for consistency, and filter data based on specific units and categories.
-   Mapping Categories: Use a mapping file to group agricultural items into categories such as Dairy, Meat, Vegetables, etc.
-    Continent Mapping: Merge datasets to add continent information to the agricultural data.
## 3. Data Visualization
The project uses Matplotlib to generate various plots, including:

1. Agricultural Production by Continent: Visualizes production by category over time for each continent.

    plt.plot(data['Year'], data['Value'], marker='o', label=continent)
    plt.title(f'{category} Production by Continent')
2. Production by Category for Selected Countries: Displays production trends by category for specific countries.

    plt.plot(data['Year'], data['Value'], marker='o', label=category)
    plt.title(f'Production by Category for {selected_country}')
3. Top 5 Items Production Over Time: Shows the top 5 items for a selected category and country.

4. World Population vs. Total Food Production: A dual-axis plot showing global population and food production trends over time.

    fig, ax1 = plt.subplots(figsize=(14, 8))
    ax1.plot(final_merge['Year'], final_merge['Total_Population'], color='blue', marker='o', label='World Population')
    ax2.plot(final_merge['Year'], final_merge['Total_Production'], color='green', marker='x', label='Total Food Production')
# Key Features
- Dynamic Filtering: Easily filter data by category, continent, or country.
- Interactive Dropdowns: Utilize IPython widgets to select and visualize specific data segments interactively.
- Extensive Data Cleaning: Automated processing of large datasets to prepare them for analysis and visualization.
-Historical Trend Analysis: Examine historical trends in agricultural production and compare them to population changes.
## File Descriptions
- world_population_data.csv: Contains country-wise and continent-wise population data.
- Production_Crops_Livestock_E_All_Data.csv: Comprehensive data on agricultural production for various crops and livestock.
- API_SP.POP.TOTL_DS2_en_csv_v2_3401680.csv: Additional population data used to enrich the main dataset.
- Lists_test.csv: Contains mapping of agricultural items to their respective categories.
## Results
The analysis reveals that global agricultural production is heavily influenced by regional factors such as climate, technological advancements, and cultural dietary preferences. While meat, particularly chicken, and egg production are dominant across all continents, other agricultural outputs vary significantly, reflecting the unique environmental and economic conditions of each region. North and South America lead in grain production, driven by large-scale mechanized farming, while Asia demonstrates diversity in crop production, catering to local dietary needs. The concentration of production in a few key commodities, such as chicken, eggs, and staple grains, underscores both the strengths and vulnerabilities of the global food system. As population growth continues and environmental challenges intensify, there is a critical need for sustainable agricultural practices and policies that address these regional disparities and promote resilience in food production. Understanding these global and regional dynamics is essential for shaping future agricultural strategies that can ensure food security and adapt to changing global demands.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

This README provides a comprehensive guide to understanding and using the project. If you have any questions or need further assistance, feel free to contact the repository maintainer.

## Contributers
Corey Holton,
Elena Gehle,
Domenic Guerrer, and
Roberta Chandler

## Resources
Mulitple resources were used to generate this code, thanks to the group of original contributers for coming up with the ideas and locating the datasets. Metin and staff for oversight and direction on this project. Xpert Learning assistant anoconda assist for debugging the code. Class materaial which was invaluable when searching for ways to re-structure data and making axis on charts. Along with chat gpt in assistance with writing the readme file.





