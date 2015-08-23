# GetData-031_Assignments
Repository for the assignments of the Get and Cleaning Data Course
This file contains the script used to create the dataset for de 
Course Project
#------------------------------------------------------------#
# Getting and Cleaning Data - Course Project   getdata-031   # 
#                                                            #
#----------------------------------------------------C.W.----#
#   1 - Merges the training and the testes sets              #
#       to create one data set                               #
#------------------------------------------------------------#
#
#   a - read the X_train.txt using read.fwf
#   b - read the X_test.txt using read.fwf
#   c - create Xall using rbind
#   
#   d - create XOK extracting  from Xall the columns with mean and std measurements
#
#   e - read the Y_train.txt using read.csv
#   f - read the Y_test.txt using read.csv
#   g - create Yall using rbind
#
#   h - read the subject_train.txt using read.csv
#   i - read the subject_test.txt using read.csv
#   j-  create Sall using rbind
#
#   k - create Data_all using cbind Sall, Yall e XOK as dataframe(Aux_all)
#


X_train<-read.fwf("C:/Coursera/03_GeCD/UCI HAR Dataset/train/X_train.txt", widths=c(rep(16,561)), header=FALSE, row.names=NULL)
X_test<-read.fwf("C:/Coursera/03_GeCD/UCI HAR Dataset/test/X_test.txt", width=c(rep(16,561)), header=FALSE,row.names=NULL)
Xall<-rbind(X_train, X_test)

#------------------------------------------------------------------------------------#
#   2 - Extracts only the measurements on the mean and standard 
#       deviation for each measure
#------------------------------------------------------------------------------------#
#    using an auxiliar vector that contains the number of the coluns with mean and std measurements
selms<-c(1, 2 ,  3,   4,   5,   6,  41,  42,  43,  44,  45,  46,  81,  82,  83,  84,  85,  86, 121, 122, 123, 124, 125, 126, 161, 162, 163, 164, 165, 166, 201, 202, 214, 215, 227, 228, 240, 241, 253, 254, 266, 267, 268, 269, 270, 271, 345, 346, 347, 348, 349, 350, 424, 425, 426, 427, 428, 429, 503, 504, 516, 517, 529,
530, 542, 543)

#   select columns for the new file

for (count in 1:length(selms)){
   if (count==1){X_OK<-Xall[selms[count]]}
   else{
     X_OK<-cbind(X_OK,Xall[selms[count]])
   }
}

#create Yall
Y_train<-read.csv("C:/Coursera/03_GeCD/UCI HAR Dataset/train/Y_train.txt", header=FALSE)
Y_test<-read.csv("C:/Coursera/03_GeCD/UCI HAR Dataset/test/Y_test.txt", header=FALSE)
Yall<-rbind(Y_train, Y_test)

#-----------------------------------------------------------------------------------#
#   3 - use descriptive activity names to neme activities inthe data set
#-----------------------------------------------------------------------------------#
# change characters for numbers in activity columnS

names<-c("WALK", "WALKUP", "WALKDWN", "SIT", "STND", "LAY")
Ynames<-Yall

for (j in 1:length(Yall)){
  Ynames[j] <-names[Yall[[j]]]
}

#crete Sall
S_train<-read.csv("C:/Coursera/03_GeCD/UCI HAR Dataset/train/subject_train.txt", header=FALSE)
S_test<-read.csv("C:/Coursera/03_GeCD/UCI HAR Dataset/test/subject_test.txt", header=FALSE)
Sall<-rbind(S_train, S_test)


#create Data_all
Data_all<-cbind(Sall, Ynames, X_OK)
Data_all<-data.frame(Data_all)

#-----------------------------------------------------------------------------------#
#  4 - Appropriately labels the data set with descriptive variables names
#-----------------------------------------------------------------------------------#

All_labels<-read.csv("C:/Coursera/03_GeCD/UCI HAR Dataset/features.txt", header=FALSE, dec=".", sep=" ")
labelsok<-colnames(Data_all)
labelsok[1]=c("Subjects")
labelsok[2]=c("Activities")

for (k in 3:(length(selms)+2)){
    message (k)
    message(All_labels[selms[[k-2]],2])
    labelsok[k]<-as.character(All_labels[selms[[k-2]],2])
}
colnames(Data_all)<-labelsok

#-----------------------------------------------------------------------------------
# 5 - From the Dataset in step 4, creates a second, independent tidy dataset 
#     with the average of each variable for each activity ans each subject
#-----------------------------------------------------------------------------------
#    sort the dataset by Subject and Activity
#
Data_sorted<-Data_all[order(Data_all$Subjects, Data_all$Activities),]
#
#  creates Data_final calculating the average for each subject and activity 
#
SubAnt<-"0"
ActAnt<-""
j<-0
for (i in 1:length(Data_sorted)){
  Data_aux<-Data_sorted[i,]
  SubAtu<-Data_aux[1]
  ActAtu<-Data_aux[2]
  if (i == 1){
    j=j+1
    Data_final<-Data_aux
  }else{
    if (SubAtu==SubAnt & ActAtu == ActAnt){
      Data_acc<-Data_acc+Data_aux}
    else{
      Data_final[]
      
      
    }  
  }
}