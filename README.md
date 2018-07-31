# gettingandcleaningdata1
# Libraries Used
The libraries used in this operation are data.table and dplyr. We prefer data.table as it is efficient in handling large data as tables. dplyr is used to aggregate variables to create the tidy data.
Read Supporting Metadata
The supporting metadata in this data are the name of the features and the name of the activities. They are loaded into variables featureNames and activityLabels.
Format training and test data sets
Both training and test data sets are split up into subject, activity and features. They are present in three different files.

Read training data
Read test data

Part 1 - Merge the training and the test sets to create one data set
We can use combine the respective data in training and test data sets corresponding to subject, activity and features. The results are stored in subject, activity and features.

Naming the columns
The columns in the features data set can be named from the metadata in featureNames
Merge the data
The data in features,activity and subject are merged and the complete data is now stored in completeData.

Part 2 - Extracts only the measurements on the mean and standard deviation for each measurement
Extract the column indices that have either mean or std in them.
Add activity and subject columns to the list and look at the dimension of completeData
We create extractedData with the selected columns in requiredColumns. And again, we look at the dimension of  requiredColumns.

Part 3 - Uses descriptive activity names to name the activities in the data set
The activity field in extractedData is originally of numeric type. We need to change its type to character so that it can accept activity names. The activity names are taken from metadata activityLabels.
We need to factor the activity variable, once the activity names are updated.

Part 4 - Appropriately labels the data set with descriptive variable names
Here are the names of the variables in extractedData
By examining extractedData, we can say that the following acronyms can be replaced:

Acc can be replaced with Accelerometer

Gyro can be replaced with Gyroscope

BodyBody can be replaced with Body

Mag can be replaced with Magnitude

Character f can be replaced with Frequency

Character t can be replaced with Time
Here are the names of the variables in extractedData after they are edited

Part 5 - From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
Firstly, let us set Subject as a factor variable.

We create tidyData as a data set with average for each activity and subject. Then, we order the enties in  tidyData and write it into data file Tidy.txt that contains the processed data.
