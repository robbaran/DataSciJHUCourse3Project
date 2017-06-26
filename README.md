# CleaningDataCourseProject

The script run_analysis.R reshapes accelerometer data from Galaxy smartphones (found in the 'UCI HAR Dataset' subdirectory of the working directory) into two data.frame objects named 'df.txt' and 'aggdf.txt', described below. 

NOTE: run_analysis.R requires the directory 'UCI HAR Dataset' to be in the working directory.
  Run the following R code (on MAC OS) to download and unzip the necessary data, creating the directory 'UCI HAR Dataset', BEFORE running run_analysis.R:
  ```
  download.file('https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip','smartphone.zip','curl')
  DateDownloaded <- Sys.Date()
  unzip('smartphone.zip')
  ```
* df.txt is a data.frame with 10,299 observations of 69 variables.
    * Each observation consists of a subject noted by 'subject_id', 66 various measurements from the subject's smartphone's accelerometer, and a label indicating the activity in which the subject was engaged during the measurements (denoted by 'activity' and 'activity_code'). 
    * The 66 measurements in df are a subset of the total 561 measurements available from the data source, corresponding to only the mean values or standard deviations of measurements. These are noted with 'mean()' and std()', respectively, in the files features.txt and features_info.txt.
  
* aggdf.txt is a data.frame with 180 observations of 68 variables.
    * The first two columns of aggdf denote an activity and subject_id and the last 66 columns correspond to smartphone measurements as mentiond above in the description of df.
    * Each observation in aggdf denotes the mean measurement value of each measurement for a given activity and subject.
    * There are (30 x 6) = 180 observations because the data contain measurements from 30 subjects engaging in 6 activities.
