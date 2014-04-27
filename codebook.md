##Description 

Describes the variables, the data, and any transformations or work that you performed to clean up the data

##Assumption

It is assumed that the Samsung data is unzipped into the working directory. The data therefore resides in the same folder as run_analysis.R

##Source

Source of the original data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip  

The attached R script (run_analysis.R) performs the following 

##A.Import of files and merge

1. Merges the training and test sets to create one data set, namely

X_test and X_train merged into X_data
Y_test and Y_Train merged into Y_data
subject_Test and subject_Train into Sub_Data


##B.Transformations

Appends the label to each of the file and then merge X_data_m_s, Y_data and Sub_Data to make it as single tidy data set.

Following steps follwed:

1.Reads file features.txt and extracts only the measurements on the mean and standard deviation for each measurement.
The result is stored in X_data_m_s a 10299 x 66 data frame, because only 66 out of 561 attributes are measurements on the mean and standard deviation. All measurements appear to be floating point numbers in the range (-1, 1).

2.Reads activity_labels.txt and applies descriptive activity names to name the activities in the data set:
 The script also appropriately labels the data set with descriptive names: all feature names (attributes) and activity names are converted to lower case, underscores and brackets () are removed.

3.Then it merges the 10299x66 data frame containing features with 10299x1 data frames containing activity labels and subject IDs.
 The result is saved as merged_tidy_data.txt, a 10299x68 data frame such that the first column contains subject IDs, the second column activity names, and the last 66 columns are measurements.



##C.Final Computation

Finally, the script creates a 2nd, independent tidy data set with the average of each measurement for each activity and each subject.
The result is saved as dataset_with_averages.txt, a 180x68 data frame, where as before, the first column contains subject IDs, the second column contains activity names (see below), and then the averages for each of the 66 attributes are in columns 3...68. There are 30 subjects and 6 activities, thus 180 rows in this data set with averages.
