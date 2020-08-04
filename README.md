# Getting-and-Cleaning-Data-Project
Coursera Data Science Specialization Course Project

## Project Description
This project is an exercise in acquiring and cleaning data. The project uses data from the UCI Machine Learning Repository: [Human Activity Recognition and Smart Phone Data site](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones). Data for the project can be downloaded [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip).

# Project Files
## Data Processing Script: run_analysis.R
The R script [run_analysis.R](https://github.com/ASteshina/Getting-and-Cleaning-Data-Project/blob/master/run_analysis.R) prepares tidy data that can be used for later analysis. It reads the data files and merges them into one full data file. The full set of variables is reduced to a subset that involve means and standard deviations. Variable names are changed to be descriptive.

## Tidy Data Output: TidyData.txt
The data is grouped by subject and activity, and summarized by each variable’s mean. The end result is a tidy data set, conforming to Hadley Wickham’s tidy data principles Tidy Data. The tidy data set is written to the file TidyData.txt.

## Data Processing Description and Variable Names: CodeBook.md
The file [CodeBook.md](https://github.com/ASteshina/Getting-and-Cleaning-Data-Project/blob/master/CodeBook.md) describes the processing steps and variables used in run_analysis.R  and supplements the README.txt included in the original downloaded archive.
