###Coursera Course Project for "Getting and Cleaning Data"

This dataset includes a subset of the following original data set:
Human Activity Recognition Using Smartphones Data Set

More information about the original dataset can be found at:
[http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones]

This dataset representst a number of average mobile phone readings, grouped by the subject wearing the phone and the activity they are performing.
See the CodeBook.md file for reading specifics.

###Files include:
- **run_analysis.R** : R script used for the class project.  It will produce a "tidy" dataset containing the average of each (mean and standard deviation for each measurement) for each activity and each subject.<br>
- **CodeBook.md** : A codebook markdown document describing the data variables


###Example of how to read the tidyData.csv file:
source('./run_analysis.R', echo=FALSE)<br>
dataset<-read.csv("./tidyData.csv")<br>
names(dataset)<br>
str(dataset)<br>
head(dataset)<br>

###Steps the script perform:
1. Read the training and the test files into separate dataframes
2. Add the appropriate subject code file to the appropriate dataframe
3. Add the appropriate activity code file to the appropriate dataframe
4. Merge the test and train dataframes into a single dataframe
5. Extract only the mean and standard deviation values for each measurement.  Since the question asked for means and std of "each measurement", I chose not to include non-native measurement aggregates.
6. Add descriptive column names to the data.  This consisted of:<br>
  -removing brachets and dashes <br>
  -replace the f with freq (frequency) and the t with time to make the columns more descriptive<br>
  -made the columns camelcase for readibility (due to the length of the names)<br>
  -added the "ave" prefix, since the final dataset will include averages for each measurement value<br>
7. Sort by data by subject / activities
8. Group the data by subject / activities
9. Write the new dataset to tidyData.csv (including headers)
