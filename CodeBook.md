This ia a code book that describes the variables, the data, 
and any transformations or work that you performed to clean up the data.

Firstly download all relevant files for this analysis:

https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/run_analysis <<< This is the script to run the analysis

https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/X_train.zip
https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/X_test.zip
https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/y_train.txt
https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/y_test.txt
https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/subject_train.txt
https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/subject_test.txt

The above files need to be downloaded to your computer to be run in the run_analysis script, and form part of the merged dataset. You use the read.table command to load each file and call then x_train, x_test, y_train, y_test, subject_train, and subject_test respectively.

You then merge the files by using the rbind command the merge x_train and x_test, y_train and y_test, and subject_train and subject_test as to form 3 seperate matrices. Then you cbind the three matrices, and store in a variable called "m_1".

You then need to download the features file: https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/features.txt to your computer and load into R using the read.table command. You idenitfy the columns containing "mean" or "std" using the grep function to get the indices and add 2 to the indices and call the vector "indices", as you had combined y_train & test, subject_train and test vectors at the start. Then you remove these columns from m_1 and store in m_1.

The next step is to download the file to your computer and load into R using the read.table command: https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/activity_labels.txt and save as a vector called "activities"

You create a vector which uses the values in the y vector column of the m_1 matrix to index the activites vector, and then replace the column in the m_1 matrix.

You then set the colnames of m_1 to "Subject" for the subject vector of the m_1 matrix, "Activity" for the y vector of the m_1 matrix, and then index the features vector by the indices vector minus 2 (as the m_1 matrix X component starts from column 3), to get the column names from the features vector, so it is labelled as other than "V1...". 

The file identifies columns starting with "f" and replaces with the word "freq" to make it more descriptive, and does the same thing with "t" to "time". It uses the sub command to change the colnames of the m_1 matrix. It also identifies "Gyro" and "Acc" in the column names and replaces with "gyroscope" and "accelerometer" respectively. It uses the same sub function.

The final step is to load dplyr, and create a new matrix called "tidy_data" which uses the group_by function on the Subject and Activity columns to group the values in the other columns by them, and then uses the summarise_all function to apply the mean to the other column.

The resulting matrix is written to your drive using write.table, and loaded here: https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/tidy_data.txt

