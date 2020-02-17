# Udacity-DS-Nanodegree_Project1: Writing a Data Science Blog Post
This is my first project in the Udacity Nanodegree, and the aim of this project is to use the CRISP-DM Methodology to provide answers to some business question and lastly, write a data science blog in non-technical terms off the answers.


# Libraries
The following libraries were used:
- Python 3
- Pandas
- Numpy
- Matplotlib


# Files in the repository 
- car_accidents.ipnyb - jupyter notebook that contains all the python codes
- data/drivingLegend.pdf - explains the dataset legend
- plots/ - contains saved plots from my python codes used in my data science blog post
- images/ - Photo by Artyom Kulakov from Pexels used in my data science plog post 
- readme.md


# Project Motivation
In 2017, the number of motor vehicles fatalities in Canada was 1841 and the number of serious injuries was 9960 (Government of Canada 2018). Each year in Canada, about 2000 people are killed and 165,000 are injured. 

The aim of this project is to understand some of the contributory factors to both Fatal and Non-Fatal accidents with the hope that more care would be excercised by road users:
- A Fatal accident is one that provides at least one fatality (death)
- A Non-Fatal accident is one that provides non-fatal injuries (non-death inducing accidents)

This project focuses on answering some business questions raised about fatal/non-fatal accidents. This is by no means an exhaustive use of this dataset. Subsequent projects would focus on applying Machine Learning techniques to this dataset


# CRISP DM Methodology
CRISP-DM stands for Cross-Industry Standard Process for Data Mining and it is an industry-proven way to guide data mining efforts. It is made up of six stages which are delved into below:

## Business Understanding
We seek for the answers to the following questions:
- What seasons of the year are more prone to accidents? And how does this change by accident severity?
- How does Sex and Age relate to accident severity?
- what Day of the week and what Hour of the day are the deadliest with regards to accident severity?

## Data Understanding
The Dataset used was gotten from Kaggle and it is a dataset of Canadian Car Accidents between 1994 – 2014 (https://www.kaggle.com/tbsteal/canadian-car-accidents-19942014). The dataset was too large to be included in my github commit, but it is available on Kaggle

Below are some details about my dataset:
- My dataset was made of 5860405 samples and 22 features.
- 20 of the features were of type object and 2 were int-64
- The column of interest (which is the y column) is the C_SEV column which has only 2 possible values – 1 for high severity and 2 for low severity
- Lastly, I had 3 missing fields, from the C_VEHS column

## Data Preparation
In preparing my data, I did the following:
- Since the NA rows were only 3, I dropped all NA values
- I noticed that although most of my columns were numerical, they were cast as objects and this was because some of the cells were strings representing either "Unknown" or "Not provided" values. These strings are ["U", "UU", "UUUU", "Q", "QQ", "QQQQ", "N", "NN", "NNNN"]. I replaced all these with NANs using numpy library
- Lastly, I recast these newly modified columns as numerical columns

Since there was no ML done for this project, this preparation was enough for my analysis


## Modelling
In answering my questions:
- I selected only the relevant columns and dropped all NA cells
- I re-ordered my data relative to the question. An example is for the question related to "Season of the year", I wrote a function to convert month to seasons
- After properly formatted, I grouped by data by relevant columns, summed and plotted as required


## Results
#### What seasons of the year are more prone to accidents? And how does this change by accident severity?
It was shocking to see that irrespective of the accident severity, *Summer* had the most number of accidents across the years and the order was Summer -> Fall -> Winter -> Spring

#### How does Sex and Age relate to accident severity?
Generally, *Males* get more involved in accidents than females and the most risky age band is *"15 - 24"*

#### what Day of the week and what Hour of the day are the deadliest with regards to accident severity?
The deadliest hour of the day for both fatal and non fatal accident is *16:00 to 16:59* while the deadliest Week Day for *Fatal accidents is Saturday* and for *Non Fatal accidents, Friday*

## Deploy
My results are presented as a blogpost on medium. Here is the link - https://medium.com/@osarugue.egharevba/some-interesting-insights-from-the-canadian-car-accidents-dataset-32f488f58a24



# Acknowledgement
1) CRSIP DM Help Overview, retrieved from https://www.ibm.com/support/knowledgecenter/SS3RA7_15.0.0/com.ibm.spss.crispdm.help/crisp_overview.htm
 on 2020.17.02 

2) Government of Canada (2018): Canadian Motor Vehicle Traffic Collision Statistics: 2017, retrieved from https://www.tc.gc.ca/eng/motorvehiclesafety/canadian-motor-vehicle-traffic-collision-statistics-2017.html on 2020.05.02
 
3) https://www.kaggle.com/tbsteal/canadian-car-accidents-19942014