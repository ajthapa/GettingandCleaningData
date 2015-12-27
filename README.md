## run_analysis() 

-------------------------------------------------------------------------------

The following points explain the process on how the *tidy_data.txt* file is obtained by running **run_analysis()** function

1. If data.table and reshape2 packages are unavailable, the two packages are installed. The two packages are included in the code.
2. Loads activity labels and column names
3. Column names with mean and std are only selected in extract_features
4. For train and test data:

    * x_test, y_test, x_train, y_train, subject_test, subject_train files are loaded into respective variables
    * Only mean and standard deviations are selected and reassigned to X_test and X_train files
    * y_test and y_train column two are extracted in to variables and are assigned header names Activity_ID and Activity_Label.
    * subject_test variable name is assigned as subject
    * Column binds subject_test, y_test,x_test into test_data and likewise subject_train, y_train and y_train into tidy_data
    * Row binds test_data and tidy_data into data and assigns column names.
    * Use melt function to convert data into molten data frame and assign to melt_data
    * melt_data is casted into data frame and is written into a file tidy_data.txt
    