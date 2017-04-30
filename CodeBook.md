# Codebook

## Variables

tidy_data

|Variable|Comments|
| ------------- |-------------| 
|activityId|	name of activity|
|subjectId| subject performed (LAYING,SITTING,STANDING,WALKING,WALKING_DOWNSTAIRS,WALKING_UPSTAIRS)|
|timeBodyAccelerometerMeanX	| mean oftBodyAcc-mean()-X|
|timeBodyAccelerometerMeanY	| mean oftBodyAcc-mean()-Y|
|timeBodyAccelerometerMeanZ	| mean oftBodyAcc-mean()-Z|
|timeBodyAccelerometerStdX	| mean oftBodyAcc-std()-X|
|timeBodyAccelerometerStdY	| mean oftBodyAcc-std()-Y|
|timeBodyAccelerometerStdZ	| mean oftBodyAcc-std()-Z|
|timeGravityAccelerometerMeanX	| mean oftGravityAcc-mean()-X|
|timeGravityAccelerometerMeanY	| mean oftGravityAcc-mean()-Y|
|timeGravityAccelerometerMeanZ	| mean oftGravityAcc-mean()-Z|
|timeGravityAccelerometerStdX	| mean oftGravityAcc-std()-X|
|timeGravityAccelerometerStdY	| mean oftGravityAcc-std()-Y|
|timeGravityAccelerometerStdZ	| mean oftGravityAcc-std()-Z|
|timeBodyAccelerometerJerkMeanX	| mean oftBodyAccJerk-mean()-X|
|timeBodyAccelerometerJerkMeanY	| mean oftBodyAccJerk-mean()-Y|
|timeBodyAccelerometerJerkMeanZ	| mean oftBodyAccJerk-mean()-Z|
|timeBodyAccelerometerJerkStdX	| mean oftBodyAccJerk-std()-X|
|timeBodyAccelerometerJerkStdY	| mean oftBodyAccJerk-std()-Y|
|timeBodyAccelerometerJerkStdZ	| mean oftBodyAccJerk-std()-Z|
|timeBodyGyroscopeMeanX	| mean oftBodyGyro-mean()-X|
|timeBodyGyroscopeMeanY	| mean oftBodyGyro-mean()-Y|
|timeBodyGyroscopeMeanZ	| mean oftBodyGyro-mean()-Z|
|timeBodyGyroscopeStdX	| mean oftBodyGyro-std()-X|
|timeBodyGyroscopeStdY	| mean oftBodyGyro-std()-Y|
|timeBodyGyroscopeStdZ	| mean oftBodyGyro-std()-Z|
|timeBodyGyroscopeJerkMeanX	| mean oftBodyGyroJerk-mean()-X|
|timeBodyGyroscopeJerkMeanY	| mean oftBodyGyroJerk-mean()-Y|
|timeBodyGyroscopeJerkMeanZ	| mean oftBodyGyroJerk-mean()-Z|
|timeBodyGyroscopeJerkStdX	| mean oftBodyGyroJerk-std()-X|
|timeBodyGyroscopeJerkStdY	| mean oftBodyGyroJerk-std()-Y|
|timeBodyGyroscopeJerkStdZ	| mean oftBodyGyroJerk-std()-Z|
|timeBodyAccelerometerMagMean	| mean oftBodyAccMag-mean()|
|timeBodyAccelerometerMagStd	| mean oftBodyAccMag-std()|
|timeGravityAccelerometerMagMean	| mean oftGravityAccMag-mean()|
|timeGravityAccelerometerMagStd	| mean oftGravityAccMag-std()|
|timeBodyAccelerometerJerkMagMean	| mean oftBodyAccJerkMag-mean()|
|timeBodyAccelerometerJerkMagStd	| mean oftBodyAccJerkMag-std()|
|timeBodyGyroscopeMagMean	| mean oftBodyGyroMag-mean()|
|timeBodyGyroscopeMagStd	| mean oftBodyGyroMag-std()|
|timeBodyGyroscopeJerkMagMean	| mean oftBodyGyroJerkMag-mean()|
|timeBodyGyroscopeJerkMagStd	| mean oftBodyGyroJerkMag-std()|
|frequencyBodyAccelerometerMeanX	| mean offBodyAcc-mean()-X|
|frequencyBodyAccelerometerMeanY	| mean offBodyAcc-mean()-Y|
|frequencyBodyAccelerometerMeanZ	| mean offBodyAcc-mean()-Z|
|frequencyBodyAccelerometerStdX	| mean offBodyAcc-std()-X|
|frequencyBodyAccelerometerStdY	| mean offBodyAcc-std()-Y|
|frequencyBodyAccelerometerStdZ	| mean offBodyAcc-std()-Z|
|frequencyBodyAccelerometerJerkMeanX	| mean offBodyAccJerk-mean()-X|
|frequencyBodyAccelerometerJerkMeanY	| mean offBodyAccJerk-mean()-Y|
|frequencyBodyAccelerometerJerkMeanZ	| mean offBodyAccJerk-mean()-Z|
|frequencyBodyAccelerometerJerkStdX	| mean offBodyAccJerk-std()-X|
|frequencyBodyAccelerometerJerkStdY	| mean offBodyAccJerk-std()-Y|
|frequencyBodyAccelerometerJerkStdZ	| mean offBodyAccJerk-std()-Z|
|frequencyBodyGyroscopeMeanX	| mean offBodyGyro-mean()-X|
|frequencyBodyGyroscopeMeanY	| mean offBodyGyro-mean()-Y|
|frequencyBodyGyroscopeMeanZ	| mean offBodyGyro-mean()-Z|
|frequencyBodyGyroscopeStdX	| mean offBodyGyro-std()-X|
|frequencyBodyGyroscopeStdY	| mean offBodyGyro-std()-Y|
|frequencyBodyGyroscopeStdZ	| mean offBodyGyro-std()-Z|
|frequencyBodyAccelerometerMagMean	| mean offBodyAccMag-mean()|
|frequencyBodyAccelerometerMagStd	| mean offBodyAccMag-std()|
|frequencyBodyBodyAccelerometerJerkMagMean	| mean offBodyBodyAccJerkMag-mean()|
|frequencyBodyBodyAccelerometerJerkMagStd	| mean offBodyBodyAccJerkMag-std()|
|frequencyBodyBodyGyroscopeMagMean	| mean offBodyBodyGyroMag-mean()|
|frequencyBodyBodyGyroscopeMagStd	| mean offBodyBodyGyroMag-std()|
|frequencyBodyBodyGyroscopeJerkMagMean	| mean offBodyBodyGyroJerkMag-mean()|
|frequencyBodyBodyGyroscopeJerkMagStd	| mean offBodyBodyGyroJerkMag-std()|

## Transformations

1. Dataset was initially split into subject, activity, and features. 
Each of these were further split into test and train sets.  Merging was performed to get everything in one dataset.

2. Dataset activity variable was merged with the activity lookup table to yield descriptive activity name.

3. Features were filtered to only those matching mean() or std(). 
Dataset was merged with derived feature code lookup table to get featureName.

4. Datset was melted with subject, activity, and feature as id variables.

5. An average was added per group of subject, activity, and feature

6. Since this is a TIDY data set, 
new descriptive columns were created to represent specific variables from the single feature variable 
(Domain,Instrument,Acceleration,StatVariable,Jerk,Magnitude and Axis) using grepl. T
he original feature is now redundant and removed.

7. The dataset is then written to tidy_data.txt file

## Data

Copied from readme.txt in original dataset.

## The dataset consist of the next files


- 'features_info.txt': Shows information about the variables used on the feature vector
- 'features.txt': List of all features
- 'activity_labels.txt': Links the class labels with their activity name
- 'train/X_train.txt': Training set
- 'train/y_train.txt': Training labels
- 'test/X_test.txt': Test set
- 'test/y_test.txt': Test labels
- 'README.txt'.

The following files are available for the train and test data. Their descriptions are equivalent.

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30.|

- 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis.

- 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration.

- 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second.

Notes:

Features are normalized and bounded within [-1,1].
Each feature vector is a row on the text file.


