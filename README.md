# Getting-and-Cleaning-Data
Course Project

Explains how scripts work and and how they are connected.

The output file is: https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/tidy_data.csv

The script to process the files is: https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/run_analysis
This generates the above output file.

You need to download the following files to your computer:

https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/subject_train.txt
https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/subject_test.txt

https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/y_train.txt
https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/y_test.txt

https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/X_test.zip
https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/X_train.zip

The above two, you need to decompress and then load into R.

Once loaded, you need to merge all 6 files together to form one matrix. You can follow in the run_analysis.R script, but essentially, test and train sit on top of each other for X, y and subject. Then you combine the matrices for all three.

Then, you need to load the features file from your computer after pulling from here: https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/features.txt

You can exclude all columns in the new merged dataset which refer to anything that is not "mean" or "std" from the X matrices.

You would then need to load the activity_labels from your computer after pulling from here: https://github.com/Wegawoo/Getting-and-Cleaning-Data/blob/master/activity_labels.txt

You need to amend the merged dataset so that column from the y matrix has values corresponding to activity name, rather than number based on the activity labels dictionary.

The run_analysis.R script then goes through steps to generate the output file noted at the start.
