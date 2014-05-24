getcleaningproject
==================

This repo was made to deliver all the thing that(i think) the project of the course Get and Cleaning Data from Coursera asked.


##Code for the analysis
It is also on the file run_analysis.R

##Put your working directory here that contains the folder UCI_HAR_Dataset
setwd("c://Users//a42664//Desktop//Coursera//WD_R")
wdatual<-getwd()

set_dir <- function(directory){
    if (directory == "raiz") {setwd(paste(wdatual,"/UCI_HAR_Dataset/",sep=""))} else {
        setwd(paste(wdatual,"/UCI_HAR_Dataset/",directory,"/",sep=""))}
}

##Merges the training and the test sets to create one data set.

set_dir("raiz")
features <- read.table("features.txt", header=FALSE)
nomes_coluna=NULL
nomes_coluna[1]="Subject"
nomes_coluna[2]="Activity"

set_dir("test")
test <- read.table("X_test.txt", header=FALSE)
colnames(test)<-features[,2]
pessoas_test <- read.table("subject_test.txt", header=FALSE)
atividades_test <- read.table("y_test.txt", header=FALSE)
TEST <- cbind(pessoas_test,atividades_test,test)
colnames(TEST)[1]<-nomes_coluna[1]
colnames(TEST)[2]<-nomes_coluna[2]

set_dir("train")
train <- read.table("X_train.txt", header=FALSE)
colnames(train)<-features[,2]
pessoas_train <- read.table("subject_train.txt", header=FALSE)
atividades_train <- read.table("y_train.txt", header=FALSE)
TRAIN <- cbind(pessoas_train,atividades_train,train)
colnames(TRAIN)[1]<-nomes_coluna[1]
colnames(TRAIN)[2]<-nomes_coluna[2]

set_dir("raiz")
one_data_set <- rbind(TEST,TRAIN)

##Uses descriptive activity names to name the activities in the data set
##Appropriately labels the data set with descriptive activity names. 

set_dir("raiz")
labels_activities <- read.table("activity_labels.txt", header=FALSE)
colnames(labels_activities)=c("Activity","Activity_Label")

one_data_set_labels<-merge(one_data_set,labels_activities,all=TRUE)

##Extracts only the measurements on the mean and standard deviation 
##for each measurement.

one_data_set_means_std <- cbind(one_data_set_labels[,2],one_data_set_labels[,564],
                               one_data_set_labels[,grep("mean", colnames(one_data_set_labels))],one_data_set_labels[,grep("Mean", colnames(one_data_set_labels))],one_data_set_labels[,grep("std", colnames(one_data_set_labels))])

colnames(one_data_set_means_std)[1]<-nomes_coluna[1]
colnames(one_data_set_means_std)[2]<-"Activity_Label"

#Reasoning to extract: I extracted all the variables that contains means and standard deviation in its names.



##Creates a second, independent tidy data set with the average of each variable for 
##each activity and each subject.
library(reshape2)
head(melt(one_data_set_means_std,id=c("Subject","Activity_Label"),measure.vars=colnames(one_data_set_means_std)[3:88]))

almost_tidy <- melt(one_data_set_means_std,id=c("Subject","Activity_Label"),measure.vars=colnames(one_data_set_means_std)[3:88])
tail(almost_tidy)

tidy<- dcast(almost_tidy, Subject + Activity_Label ~ variable, fun.aggregate=mean)


#English-like descriptive names for the measurings of the sensor
colnames(tidy)<-c(    "subject"	,	"activity"	,
                      "mean.of.t.bodyacc.x"	,	"mean.of.t.bodyacc.y"	,
                      "mean.of.t.bodyacc.z"	,	"mean.of.t.gravityacc.x"	,
                      "mean.of.t.gravityacc.y"	,	"mean.of.t.gravityacc.z"	,
                      "mean.of.t.bodyaccjerk.x"	,	"mean.of.t.bodyaccjerk.y"	,
                      "mean.of.t.bodyaccjerk.z"	,	"mean.of.t.bodygyro.x"	,
                      "mean.of.t.bodygyro.y"	,	"mean.of.t.bodygyro.z"	,
                      "mean.of.t.bodygyrojerk.x"	,	"mean.of.t.bodygyrojerk.y"	,
                      "mean.of.t.bodygyrojerk.z"	,	"mean.of.t.bodyaccmag.z"	,
                      "mean.of.t.gravityaccmag"	,	"mean.of.t.bodyaccjerkmag"	,
                      "mean.of.t.bodygyromag"	,	"mean.of.t.bodygyrojerkmag"	,
                      "mean.of.f.bodyacc.x"	,	"mean.of.f.bodyacc.y"	,
                      "mean.of.f.bodyacc.z"	,	"mean.of.f.bodyaccfreq.x"	,
                      "mean.of.f.bodyaccfreq.y"	,	"mean.of.f.bodyaccfreq.z"	,
                      "mean.of.f.bodyaccjerk.x"	,	"mean.of.f.bodyaccjerk.y"	,
                      "mean.of.f.bodyaccjerk.z"	,	"mean.of.f.bodyaccjerkfreq.x"	,
                      "mean.of.f.bodyaccjerkfreq.y"	,	"mean.of.f.bodyaccjerkfreq.z"	,
                      "mean.of.f.bodygyro.x"	,	"mean.of.f.bodygyro.y"	,
                      "mean.of.f.bodygyro.z"	,	"mean.of.f.bodygyrofreq.x"	,
                      "mean.of.f.bodygyrofreq.y"	,	"mean.of.f.bodygyrofreq.z"	,
                      "mean.of.f.bodyaccmag"	,	"mean.of.f.bodyaccmagfreq"	,
                      "mean.of.f.bodybodyaccjerkmag"	,	"mean.of.f.bodybodyaccjerkmagfreq"	,
                      "mean.of.f.bodybodygyromag"	,	"mean.of.f.bodybodygyromagfreq"	,
                      "mean.of.f.bodybodygyrojerkmag"	,	"mean.of.f.bodybodygyrojerkmagfreq"	,
                      "mean.of.bodyaccgravity.angle"	,	"mean.of.bodyaccjerkmeangravity.angle"	,
                      "mean.of.bodygyrogravity.angle"	,	"mean.of.bodygyrojerkmeangravity.angle"	,
                      "mean.of.xgravity.angle"	,	"mean.of.ygravity.angle"	,
                      "mean.of.zgravity.angle"	,	"meanstd.of.t.bodyacc.x"	,
                      "meanstd.of.t.bodyacc.y"	,	"meanstd.of.t.bodyacc.z"	,
                      "meanstd.of.t.gravityacc.x"	,	"meanstd.of.t.gravityacc.y"	,
                      "meanstd.of.t.gravityacc.z"	,	"meanstd.of.t.bodyaccjerk.x"	,
                      "meanstd.of.t.bodyaccjerk.y"	,	"meanstd.of.t.bodyaccjerk.z"	,
                      "meanstd.of.t.bodygyro.x"	,	"meanstd.of.t.bodygyro.y"	,
                      "meanstd.of.t.bodygyro.z"	,	"meanstd.of.t.bodygyrojerk.x"	,
                      "meanstd.of.t.bodygyrojerk.y"	,	"meanstd.of.t.bodygyrojerk.z"	,
                      "meanstd.of.t.bodyaccmag"	,	"meanstd.of.t.gravityaccmag"	,
                      "meanstd.of.t.bodyaccjerkmag"	,	"meanstd.of.t.bodygyromag"	,
                      "meanstd.of.t.bodygyrojerkmag"	,	"meanstd.of.f.bodyacc.x"	,
                      "meanstd.of.f.bodyacc.y"	,	"meanstd.of.f.bodyacc.z"	,
                      "meanstd.of.f.bodyaccjerk.x"	,	"meanstd.of.f.bodyaccjerk.y"	,
                      "meanstd.of.f.bodyaccjerk.z"	,	"meanstd.of.f.bodygyro.x"	,
                      "meanstd.of.f.bodygyro.y"	,	"meanstd.of.f.bodygyro.z"	,
                      "meanstd.of.f.bodyaccmag"	,	"meanstd.of.f.bodybodyaccjerkmag"	,
                      "meanstd.of.f.bodybodygyromag"	,	"meanstd.of.f.bodybodygyrojerkmag"	)


write.table(tidy,file="tidy_getcleaningprojet.txt")
