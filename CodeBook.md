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

-   **activities** - 6 observations (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) of 2 variables. 
-   **MergedData** - Data sets with merged training and test sets. 10299 observations of 563 variables.
-   **Data** - Data of only the measurements on the mean and standard
    deviation for each measurement, has descriptive activity names. 10299 observations of 88 variables.
-   **TidyData** - Data set with means of each variable grouped by
    activity and subject. 180 observations of 88 variables:
    
        [1] "activity"                                       
        [2] "subject"                                       
        [3] "TimeBodyAccelerometermeanX"                     
        [4] "TimeBodyAccelerometermeanY"                     
        [5] "TimeBodyAccelerometermeanZ"                     
        [6] "TimeGravityAccelerometermeanX"                  
        [7] "TimeGravityAccelerometermeanY"                  
        [8] "TimeGravityAccelerometermeanZ"                  
        [9] "TimeBodyAccelerometerJerkmeanX"                 
        [10] "TimeBodyAccelerometerJerkmeanY"                 
        [11] "TimeBodyAccelerometerJerkmeanZ"                 
        [12] "TimeBodyGyroscopemeanX"                         
        [13] "TimeBodyGyroscopemeanY"                         
        [14] "TimeBodyGyroscopemeanZ"                         
        [15] "TimeBodyGyroscopeJerkmeanX"                     
        [16] "TimeBodyGyroscopeJerkmeanY"                     
        [17] "TimeBodyGyroscopeJerkmeanZ"                     
        [18] "TimeBodyAccelerometerMagnitudemean"
        [19] "TimeGravityAccelerometerMagnitudemean"          
        [20] "TimeBodyAccelerometerJerkMagnitudemean"         
        [21] "TimeBodyGyroscopeMagnitudemean"                 
        [22] "TimeBodyGyroscopeJerkMagnitudemean"             
        [23] "FrequencyBodyAccelerometermeanX"                
        [24] "FrequencyBodyAccelerometermeanY"                
        [25] "FrequencyBodyAccelerometermeanZ"                
        [26] "FrequencyBodyAccelerometermeanFreqX"            
        [27] "FrequencyBodyAccelerometermeanFreqY"            
        [28] "FrequencyBodyAccelerometermeanFreqZ"            
        [29] "FrequencyBodyAccelerometerJerkmeanX"            
        [30] "FrequencyBodyAccelerometerJerkmeanY"            
        [31] "FrequencyBodyAccelerometerJerkmeanZ"            
        [32] "FrequencyBodyAccelerometerJerkmeanFreqX" 
        [33] "FrequencyBodyAccelerometerJerkmeanFreqY"        
        [34] "FrequencyBodyAccelerometerJerkmeanFreqZ"        
        [35] "FrequencyBodyGyroscopemeanX"                    
        [36] "FrequencyBodyGyroscopemeanY"                    
        [37] "FrequencyBodyGyroscopemeanZ"                    
        [38] "FrequencyBodyGyroscopemeanFreqX"                
        [39] "FrequencyBodyGyroscopemeanFreqY"                
        [40] "FrequencyBodyGyroscopemeanFreqZ"                
        [41] "FrequencyBodyAccelerometerMagnitudemean"        
        [42] "FrequencyBodyAccelerometerMagnitudemeanFreq"    
        [43] "FrequencyBodyAccelerometerJerkMagnitudemean"    
        [44] "FrequencyBodyAccelerometerJerkMagnitudemeanFreq"
        [45] "FrequencyBodyGyroscopeMagnitudemean"            
        [46] "FrequencyBodyGyroscopeMagnitudemeanFreq"        
        [47] "FrequencyBodyGyroscopeJerkMagnitudemean"        
        [48] "FrequencyBodyGyroscopeJerkMagnitudemeanFreq"    
        [49] "AngleTimeBodyAccelerometerMeanGravity"          
        [50] "AngleTimeBodyAccelerometerJerkMeanGravityMean"  
        [51] "AngleTimeBodyGyroscopeMeanGravityMean"          
        [52] "AngleTimeBodyGyroscopeJerkMeanGravityMean"      
        [53] "AngleXGravityMean"     
        [54] "AngleYGravityMean"                              
        [55] "AngleZGravityMean"                              
        [56] "TimeBodyAccelerometerstdX"                      
        [57] "TimeBodyAccelerometerstdY"                      
        [58] "TimeBodyAccelerometerstdZ"                      
        [59] "TimeGravityAccelerometerstdX"                   
        [60] "TimeGravityAccelerometerstdY"                   
        [61] "TimeGravityAccelerometerstdZ"                   
        [62] "TimeBodyAccelerometerJerkstdX"                  
        [63] "TimeBodyAccelerometerJerkstdY"                  
        [64] "TimeBodyAccelerometerJerkstdZ"                  
        [65] "TimeBodyGyroscopestdX"                          
        [66] "TimeBodyGyroscopestdY"                          
        [67] "TimeBodyGyroscopestdZ"                          
        [68] "TimeBodyGyroscopeJerkstdX"                      
        [69] "TimeBodyGyroscopeJerkstdY"                      
        [70] "TimeBodyGyroscopeJerkstdZ"                      
        [71] "TimeBodyAccelerometerMagnitudestd"              
        [72] "TimeGravityAccelerometerMagnitudestd"           
        [73] "TimeBodyAccelerometerJerkMagnitudestd"          
        [74] "TimeBodyGyroscopeMagnitudestd"                  
        [75] "TimeBodyGyroscopeJerkMagnitudestd"              
        [76] "FrequencyBodyAccelerometerstdX"                 
        [77] "FrequencyBodyAccelerometerstdY"                 
        [78] "FrequencyBodyAccelerometerstdZ"                 
        [79] "FrequencyBodyAccelerometerJerkstdX"             
        [80] "FrequencyBodyAccelerometerJerkstdY"             
        [81] "FrequencyBodyAccelerometerJerkstdZ"             
        [82] "FrequencyBodyGyroscopestdX"                     
        [83] "FrequencyBodyGyroscopestdY"                     
        [84] "FrequencyBodyGyroscopestdZ"                     
        [85] "FrequencyBodyAccelerometerMagnitudestd"         
        [86] "FrequencyBodyAccelerometerJerkMagnitudestd"     
        [87] "FrequencyBodyGyroscopeMagnitudestd"             
        [88] "FrequencyBodyGyroscopeJerkMagnitudestd"
