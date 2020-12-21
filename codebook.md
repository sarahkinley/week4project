Codebook for run_analysis.R 

The following codebook describes the run_analysis.R script, which performs the steps described in John Hopkins' Getting and Cleaning Data Week 4 course project assignment

1. Download the Dataset
- Dataset was downloaded from UCI HAR Dataset provided by John Hopkins

2. Assign each data to variables
features <-features.txt 
#from accelerometer and gyroscope 3-axial raw signals
activities <-activity_labels.txt 
#list of activities performed when the corresponding measurements were taken and its codes (labels) 
subject_test<-test/subject_test.txt 
#test data of volunteer test subjects observed
x_test <- test/X_test.txt
#test data recorded features
y_test <- test/y_test.txt
#test data of activities’code labels
subject_train <- test/subject_train.txt
#train data of volunteer subjects being observed
x_train <- test/X_train.txt
#recorded features train data
y_train <- test/y_train.txt
#train data of activities’code labels

3. Merging the two data sets (training and test sets) 
- x created by merging x_train and x_test using rbind() function
- y created by merging y_train and y_test using rbind() function
-Subject created by merging subject_train and subject_test using rbind()function
-Merged_Data created by merging Subject, Y, and X using cbind()function


