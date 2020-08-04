Data:
-----

The data for the project was downloaded from:
<a href="http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones" class="uri">http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones</a>

Processing
----------

### Step 1: Merge training and test sets to create one data set

Data was downloaded from the source files and read in with names
corresponding to the source files. Test set data were combined with
train set data using *rbind()*. Merged data set was then created using
*cbind()*. Variable created: **Merged\_Data**

### Step 2: Extract only measurements on mean and standard deviation

**Data** variable was created. This variable was subsetted to include
only the subject, activity, and variables that included mean and
standard deviation (std).

### Step 3: Use descriptive activities names for activity measurements

The coded values for activity were changed to the activity name.

### Step 4: Appropriately Label the Dataset with Descriptive Variable Names

The column names of **Data** were changed to be descriptive. Capital
letters were introduced, punctuation was removed, abbreviations “t” and
“f” were changed to time and frequency using *gsub()*.

### Step 5: Create tidy data set with average of each variable, by activity, by subject

**Data** from the end of Step 4 was grouped by subject, then by
activity, and summarized so that the observations in each row were the
means of the variable columns, for that subject/activity. This was
accomplished by applying the dply package verbs *group\_by()* and
*summarise\_each()*. The resulting tidy data set was written to a file
called **TidyData.txt**.

Variables
---------

-   **MergedData** - Data sets with merged training and test sets.
-   **Data** - Data of only the measurements on the mean and standard
    deviation for each measurement, has descriptive activity names.
-   **TidyData** - Data set with means of each variable grouped by
    activity and subject.