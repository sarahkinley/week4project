Codebook for run_analysis.R 

The following codebook describes the run_analysis.R script, which performs the steps described in John Hopkins' Getting and Cleaning Data Week 4 course project assignment

1. Download the Dataset
- Dataset was downloaded from UCI HAR Dataset provided by John Hopkins

2. Assign data frames
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

3. Merging data sets (training and test)
- x created by merging x_train and x_test using rbind() function
- y created by merging y_train and y_test using rbind() function
-Subject created by merging subject_train and subject_test using rbind()function
-Merged_Data created by merging Subject, Y, and X using cbind()function

4. Extract mean and standard deviation for each measurement
- TidyData is created by subsetting Merged_Data, selecting only columns: subject, code, and to the measurements on the mean and standard deviation for each measurement

5. Name activities in the data set
- Numbers in the code column of the TidyData replaced with corresponding activity taken from second column of the activities variable

6. Label dataset with descriptive variable names
- code column in TidyData renamed into activities
- All Acc in column’s name replaced by Accelerometer
- All Gyro in column’s name replaced by Gyroscope
- All BodyBody in column’s name replaced by Body
- All Mag in column’s name replaced by Magnitude
- All start with character f in column’s name replaced by Frequency
- All start with character t in column’s name replaced by Time

7. From TidyData, create an independent tidy data set with avg. of each variable for each activity and each subject
- SarahData was created by summarizing TidyData taking the means of each variable for each activity and each subject, after it was grouped for subject and activity
- Exported SarahData into a SarahData.txt file, as instructed in this course
