The script written in "run_analysis.R" performs the 5 steps defined in the project requirement and gets the desired dataset.

**Download dataset:**

The dataset was downloaded and extracted manually in the folder.

**Extracting data to variables:**

features <- features.txt : 561 rows, 2 columns

Features present in this database come from the accelerometer and gyroscope 3-axial raw signals.

activities <- activity_labels.txt : 6 rows, 2 columns

This variable contains the list of activities performed when the corresponding measurements were taken and its corresponding codes (labels)

subject_test <- subject_test.txt : 2947 rows, 1 column

Contains code to the corresponding subjects of test data.

x_test <- X_test.txt : 2947 rows, 561 columns

Contains the test data.

y_test <- y_test.txt : 2947 rows, 1 columns

Contains activities code labels for test data.

subject_train <- subject_train.txt : 7352 rows, 1 column

Contains code to the corresponding subjects of train data.

x_train <- X_train.txt : 7352 rows, 561 columns

Contains the train data.

y_train <- y_train.txt : 7352 rows, 1 columns

Contains activities code labels for train data.

**Merging of the sets:**

The train and test sets are merged by using rbind() function to create X, Y and subject datasets.

merged_data is created by combining all the binded data sets with cbind() function.

**Extracting the measurements on the mean and standard deviation:**

TidyData is created by only keeping those columns from merged_data which has either "mean" or "std" in its name. 

**Descriptive activity names to name the activities in the data set:**

Column names in TidyData are renamed in the following way:

"code"->activities

All "Acc"->Accelerometer

All "Gyro"->Gyroscope

All "BodyBody"->Body

All "Mag"->Magnitude

Starting with character "f"->Frequency

Starting with character "t"->Time

**From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject:**

"NewTidySet" is created by using group_by function on "TidySet" with the parameters of subject and activity. Then "summarise_all" is used to calculate the mean of every variable based on the grouping. 

Then finally, the achieved dataset is exported to txt file.

