=========
# Source Files / Data
=========
Source data - https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

The source files are:

features_info.txt - Information about the variables used for the feature vector

features.txt - Measurement of the mean and standard deviation of measurements

activity_labels.txt - Connects the class labels with their activity names

train/X_train.txt - Training set

train/y_train.txt - Training labels

train/subject_train.txt - Identifies the train subject who performed the activity for each window sample

test/X_test.txt - Testing set

test/y_test.txt - Testing labels

test/subject_test.txt - Identifies the test subject who performed the activity for each window sample

merged_clean_data.txt - Data that's been cleansed and merged

tidydataset.txt - The final tidy data set with averages


# Variables
=========
train_temp - Temporary training data set

test_temp - Temporart testing data set

merge_x - Merges the training data set and the testing data set

merge_s - Merges the training and testing subject data

merge_y - Merges the training label and the testing label data

features - Reads the table "features.txt"

extract_data - Extraction of standard deviation

Activities - Reads the table "activity_labels.txt"

cleaned - Clean data set with descriptive activity name labels

unique_subject - identifies the unique subject data

length_subject - identifies the length of subjects

length_activities - identifies the length of activities

number_column - identifies the number of columns

new_data - new tidy data set with each activity and each subject

new_average - new tidy data set with the average of each variable for each activity and each subject


# Transformations
=========
1) Merge the training and test sets to create one data set. The result is a 10299 x 561 data frame.

2) From file features.txt, extract only the measurements on the mean and standard deviation for each measurement. The result is a 10299 x 66 data frame.

3) Reads activity_labels.txt and give descriptive activity names to the columns in the data set:

walking

walkingupstairs

walkingdownstairs

sitting

standing

laying


4) The script makes the following changes to the feature names: 
all feature names (attributes) and activity names are converted to lower case and underscores and brackets () are removed.

Then it merges the 10299x66 data frame  with 10299x1 data frames. The result is saved as merged_clean_data.txt. Names of the attributes are similar to the following:

tbodyacc-mean-x

tbodyacc-mean-y

tbodyacc-mean-z

tbodyacc-std-x

tbodyacc-std-y

tbodyacc-std-z

tgravityacc-mean-x

tgravityacc-mean-y


5) Finally, the script creates a second, independent tidy data set with the average of each measurement for each activity and each subject. The result is saved as tidydata.txt.