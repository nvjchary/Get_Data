Get_Data
========
Contains the code for programming assignment 2 Run_analysis.R



Unzip the source ( https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip )into a folder on your local drive, say D:\Coursera\Get_Data\Assignment\2

Place run_analysis.R to "D:\Coursera\Get_Data\Assignment\2"

open  RStudio:

Type following codes in the new R_script

setwd("D:\Coursera\Get_Data\Assignment\2")
source("run_analysis.R")

Select these two lines and press Run.


This will run R script. It will import/ read the dataset and write these files:

merged_tidy_data.txt : a 10299x68 data frame

dataset_averages.txt :0.225 Mb, a 180x68 data frame

