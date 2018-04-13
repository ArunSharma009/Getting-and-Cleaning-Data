Code Book:

This code book gives the description of the  the data used in this project, as well as the detailed processing  steps required to create the resulting tidy data set.

Overview
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

Explanation of each file
* features.txt: Names of the 561 features. 
* activity_labels.txt: Names and IDs for each for the 6 activities. 
* X_train.txt: 7352 observations of the 561 features, for 21 of the 30 volunteers. 
* subject_train.txt: A vector of 7352 integers, which is  the ID of the volunteer related to each of the observations in X_train.txt. 
* y_train.txt: A vector of 7352 integers, which is the ID of the activity related to each of the observations in X_train.txt. 
* X_test.txt: 2947 observations of the 561 features, for 9 of the 30 volunteers. 
* subject_test.txt: A vector of 2947 integers, denoting the ID of the volunteer related to each of the observations in X_test.txt. 
* y_test.txt: A vector of 2947 integers, denoting the ID of the activity related to each of the observations in X_test.txt. 
Please find more information about the files in README.txt. More information about the features can be seen in features_info.txt.


Processing steps
1. Firstly,  the required data files were read into data frames, missing necessary column headers were added. Also the training and test sets were merged into a single data set.
2. Feature columns that did not contain string "mean()" or "std()" were removed, as a result only 66 feature columns were left. Also the subjectID and activity columns were retained.
3. The activity column was converted from a integer to a factor, using labels describing the activities.
4. A tidy data set was created which has the mean for each of the feature for every subject and  activity. Thus, subject 1 has 6 rows in the tidy data set  with each row containing the mean value for every of  66 features for that subject or activity combination. There is total of 180 rows.
5. The tidy data set obtained as output in a CSV file format.