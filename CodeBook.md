#----------------------------------------------------------------------------#
#                                                                            #
#   Get and Cleaning Data - 031                                              #
#                                                                            #
#   Code Book for the Samsung data                                           #
#                                                                            #
#-----------------------------------------------Aug/22/2015----C.W.----------#
#

The features selected for this database comes from the complete dataset 
from accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ from
Samsung Galaxy Smartphone. Details from the experience and complementary informations
like full description and about the original dataset can be found in:

http://archive.ics.uci.edu/m/datasets/Human+Activity+Recognition+Using+Samartphones
 
The initial dataset from wich this was processed is available in 

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
 
The dataset has  unique pairs of variables Subject+Activity

---------------------------------------------------------------------------------------------

Subjects
--------
      
      identification for each one of the 30 persons that has participated of the study
  
      numbers 
         1 - 30

Activity
--------
      identification os the 6 activities played by the subjects

      characters

		WALK      - walking activity

        WALKUP    - walking up activity

        WALKDWN   - walking down activity
 
        SIT       - sitting

        STND      - standing

        LAY       - laying

----------------------------------------------------------------------------------------------

The following variables represents the average of the variables from the original dataset, 

grouped by Subjects and Activity.

** NOTE: the name of the columns remains the same as the original dataset but are the average 
** of the measurements from the original datase 

Mean calculated from the Body Acceleration mesurements, for each one of the three axis;
	 tBodyAcc-mean()-X
		numeric
	 tBodyAcc-mean()-Y
		numeric
	 tBodyAcc-mean()-Z
		numeric

Standard Deviation calculeted from the Body Acceleration mesurements, for each one of the three axis;
	tBodyAcc-std()-X
		numeric
 	tBodyAcc-std()-Y
		numeric
 	tBodyAcc-std()-Z
		numeric

	tGravityAcc-mean()-X
		numeric
 	tGravityAcc-mean()-Y
		numeric
 	tGravityAcc-mean()-Z
		numeric

 	tGravityAcc-std()-X
		numeric
 	tGravityAcc-std()-Y
		numeric
 	tGravityAcc-std()-Z
		numeric

 	tBodyAccJerk-mean()-X
		numeric
 	tBodyAccJerk-mean()-Y
		numeric
 	tBodyAccJerk-mean()-Z
		numeric
 	tBodyAccJerk-std()-X
		numeric
 	tBodyAccJerk-std()-Y
		numeric
 	tBodyAccJerk-std()-Z
		numeric

 	tBodyGyro-mean()-X
		numeric
 	tBodyGyro-mean()-Y
		numeric
 	tBodyGyro-mean()-Z
		numeric
 	tBodyGyro-std()-X
		numeric
 	tBodyGyro-std()-Y
		numeric
 	tBodyGyro-std()-Z
		numeric

 	tBodyGyroJerk-mean()-X
		numeric
 	tBodyGyroJerk-mean()-Y
		numeric
 	tBodyGyroJerk-mean()-Z
		numeric
 	tBodyGyroJerk-std()-X
		numeric
 	tBodyGyroJerk-std()-Y
		numeric
 	tBodyGyroJerk-std()-Z
		numeric


 	tBodyAccMag-mean()
		numeric
 	tBodyAccMag-std()
		numeric

 	tGravityAccMag-mean()
		numeric
 	tGravityAccMag-std()
		numeric

 	tBodyAccJerkMag-mean()
		numeric
 	tBodyAccJerkMag-std()
		numeric

