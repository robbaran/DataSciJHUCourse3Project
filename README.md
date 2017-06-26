# CleaningDataCourseProject

The script **run_analysis.R** reshapes accelerometer data from Galaxy smartphones (found in the 'UCI HAR Dataset' subdirectory of the working directory) into two data.frame objects named '**df.txt**' and '**aggdf.txt**', described below. 

NOTE: **run_analysis.R** requires the directory 'UCI HAR Dataset' to be in the working directory.
  Run the following R code (on MAC OS) to download and unzip the necessary data, creating the directory 'UCI HAR Dataset', BEFORE running run_analysis.R:
  ```
  download.file('https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip','smartphone.zip','curl')
  DateDownloaded <- Sys.Date()
  unzip('smartphone.zip')
  ```
## df.txt and aggdf.txt
* The data in **df.txt** and **aggdf.txt** produced by run_analysis.R are tidy because each row represents a separate observation of a subject's smartphone's test measurements, with each column representing a separate variable being measured in each observation. The two data tables report on the same features/columns, but **df.txt**'s rows represent indivual test observations of those features, whereas **aggdf.txt**'s rows represent the mean measurement for each feature aggregated by subject and activity type.
### Same Columns
* df.txt and aggdf.txt both have 68 columns whose names are listed in '**modified_features.txt**' and whose derivations are explained in '**modified_features_info.txt**'.
  * The 1st column displays the subject_id, which is the identifier of a particular test subject for a measurement.
  * The 2nd through 67th columns display 66 measurements, corresponding to only the mean() and std() values of the original 561 features in the total dataset.
  * The last and 68th column displays the name of the activity in which the subject was engaged during a test.
### Different Rows
* df.txt and aggdf.txt represent different observations
    * **df.txt** contains all 10,299 observations of the measurements and labels.
    * **aggdf.txt** contains 180 rows, each of which contains the mean value of each of the 66 measurements for a given activity and subject. There are (30 x 6) = 180 observations because the data contain measurements from 30 subjects engaging in 6 activities.
