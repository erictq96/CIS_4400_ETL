# Indochina Countries Covid-19 Data Engineer Project

This project focuses on Covid-19 situation in Indochina countries, which are Cambodia, Laos, Myanmar, Thailand, and Vietnam.

## Description

Through this project, I'd like to understand how factors such as number of people vaccinated, GDP, unemployment rate, hospital beds, population are correlated with the cases that increase daily in these countries. Thus, we decided to segment the data demographically based on geography to get a picture of whether places with more vaccinated people, hospital beds, and wealthier show signs of decreasing daily cases. 

## Getting Started

### Dependencies

* Anaconda Navigator - Jupyter Notebook, Python 3.7 or above

### Installing

* Download & Install Anaconda Navigator then open Jupyter Notebook from there. (https://docs.anaconda.com/)
* Install Pandas from terminal in Jupyter Notebook
```
conda install pandas
```
*  Install Pandas to Big Query from terminal in Jupyter Notebook
```
conda install pandas-gbq -c conda-forge
```

### Executing program

* Import libraries
```
import pandas as pd
from pandas.io import gbq
```
* Read csv files into DataFrames
```
df = pd.read_csv("path to the file")
```
* Clean Data (view the code for more information)
```
df = df.fillna(-1) #fill NaN data with value -1
```
```
df = df[df["Code"].isin(["KHM", "LAO", "MMR", "THA", "VNM"])] # select Indochina countries only from the world data
```
* Load DataFrames onto Google Big Query
```
df.to_gbq(destination_table="your new table name", project_id="your project ID on Big Query", if_exists="replace")
```

## Help

Please contact me via emails or linkedin message (info below)

## Authors

* Hung "Eric" Tran
* erictq96@gmail.com or tranhu06@gmail.com
* https://www.linkedin.com/in/erictq96/

## References
* How To Load Dataframes Onto Big Query: https://www.youtube.com/watch?v=rpy-PiEapT8&t=51s
