# COVID19-DataProject

## Installation

In order to pull the aggregate data, clone the git repository using

git clone https://github.com/ZooPhy/COVID19-DataProject.git

COVID19-DataProject requires some setup.
1. Make sure that pip and Python are both installed. Documentation for installing Python can be found at https://www.python.org/downloads/ and instructions for pip can be found at https://pip.pypa.io/en/stable/installing/.
2. Make sure that numpy, pandas, and sodapy are installed using the following commands
```
pip install pandas
pip install numpy
pip install sodapy
```
3. From within the folder `src`, run the command `python run.py` to execute the program and generate a file with the aggregated travel, climate, and covid-19 data. This data file with be titled based on the day that the data was pulled. For example, data pulled on December 10th 2020 will be named `20201210.csv`. The individual scripts can be found within their respective subdirectories

## Description of the program
### downloadClimateData.bash 
This bash script is used to download a sorted list of the climate data based on FIPS county code. This climate data comes from the Global Historical Climatology Network - Daily (GHCN-Daily) datasets. Both the maximum daily temperature and the daily total precipitation are added to our data set.

### climate.py
This is used to find the median and mean temperature and percipitation for each US county, starting from the beginning of 2020 to the current date.

### covid.py
Python script for downloading COVID-19 case and death data. The COVID-19 case and death data comes from the Johns Hopkins Whiting School of Engineering and their source code and be found here https://github.com/CSSEGISandData/COVID-19.

### travel.py
This python script is used to download travel data. The travel data is sourced from the Bureau of Transportation Statistics and their data source can be found here https://data.bts.gov/Research-and-Statistics/Trips-by-Distance/w96p-f2qv/data. 

### merge.py
This python script is used to merge the travel and case data. The output is a csv file titled with the current date. This is the complete aggregate data file.

## Dependencies
Below is a description of the dependencies needed for each of the scripts above.

### FIPSMetadata.csv
Data file with FIPS code for each US county. Needed for covid.py.

### StationMetadata.csv
Data file with Station Name and associated county. Needed for downloadClimateData.bash.

### us_census_2018_population_estimates_counties.csv
Information about population density comes from the 2018 USA Census and the data source is from the COVID tracking project that provides an online resource for population density download, which can be found here https://github.com/COVID19Tracking/associated-data/blob/master/us_census_data/us_census_2018_population_estimates_counties.csv. Needed for merge.py.

