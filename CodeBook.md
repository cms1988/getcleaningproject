##CodeBook for Get and Cleaning Data Course from Coursera

In this code book you'll find all the things you need to know about this tidy dataset and its variables.

#About the experiment that created the original Dataset

==================================================================
Human Activity Recognition Using Smartphones Dataset
Version 1.0
==================================================================
Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
Smartlab - Non Linear Complex Systems Laboratory
DITEN - Università degli Studi di Genova.
Via Opera Pia 11A, I-16145, Genoa, Italy.
activityrecognition@smartlab.ws
www.smartlab.ws
==================================================================

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. 
Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAyING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. from each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

for each record it is provided:
======================================

- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

#About the final Dataset:tidy
It was extracted all the variables that contained the terms "mean" and "std" on its names and calculated the mean for each combination of volunteer and activity.
There is 180 lines of observations with 88 columns of variables described as below:

* subject: identifier of the volunteers
* activity: identifier of the activiy perfomed by the volunteers
*	mean.of.t.bodyacc.x : Mean of time series Body Accelerometer on  X Coordinate
*	mean.of.t.bodyacc.y : Mean of time series Body Accelerometer on  Y Coordinate
*	mean.of.t.bodyacc.z : Mean of time series Body Accelerometer on  Z Coordinate
*	mean.of.t.gravityacc.x : Mean of time series Gravity Accelerometer on  X Coordinate
*	mean.of.t.gravityacc.y : Mean of time series Gravity Accelerometer on  Y Coordinate
*	mean.of.t.gravityacc.z : Mean of time series Gravity Accelerometer on  Z Coordinate 
*	mean.of.t.bodyaccjerk.x : Mean of time series Body Accelerometer Jerk Signal on X Coordinate
*	mean.of.t.bodyaccjerk.y : Mean of time series Body Accelerometer Jerk Signal Y Coordinate 
*	mean.of.t.bodyaccjerk.z : Mean of time series Body Accelerometer Jerk Signal Z Coordinate 
*	mean.of.t.bodygyro.x : Mean of time series Body Gyroscope X Coordinate
*	mean.of.t.bodygyro.y : Mean of time series Body Gyroscope Y Coordinate
*	mean.of.t.bodygyro.z : Mean of time series Body Gyroscope Z Coordinate
*	mean.of.t.bodygyrojerk.x : Mean of time series Body Gyroscope Jerk Signal X Coordinate
*	mean.of.t.bodygyrojerk.y : Mean of time series Body Gyroscope Jerk Signal Y Coordinate
*	mean.of.t.bodygyrojerk.z : Mean of time series Body Gyroscope Jerk Signal Z Coordinate
*	mean.of.t.bodyaccmag.z : Mean of time series Body Accelerometer Magnitude Z Coordinate
*	mean.of.t.gravityaccmag : Mean of time series Gravity Accelerometer Magnitude 
*	mean.of.t.bodyaccjerkmag : Mean of time series Body Accelerometer Jerk Signal Magnitude
*	mean.of.t.bodygyromag : Mean of time series Body Gyroscope Magnitude 
*	mean.of.t.bodygyrojerkmag : Mean of time series Body Gyroscope Jerk Signal Magnitude
*	mean.of.f.bodyacc.x : Mean of frequency Body Accelerometer  X Coordinate
*	mean.of.f.bodyacc.y : Mean of frequency Body Accelerometer  Y Coordinate
*	mean.of.f.bodyacc.z : Mean of frequency Body Accelerometer  Z Coordinate
*	mean.of.f.bodyaccfreq.x : Mean of frequency Body Accelerometer X Coordinate
*	mean.of.f.bodyaccfreq.y : Mean of frequency Body Accelerometer Y Coordinate
*	mean.of.f.bodyaccfreq.z : Mean of frequency Body Accelerometer Z Coordinate
*	mean.of.f.bodyaccjerk.x : Mean of frequency Body Accelerometer Jerk Signal X Coordinate
*	mean.of.f.bodyaccjerk.y : Mean of frequency Body Accelerometer Jerk Signal Y Coordinate
*	mean.of.f.bodyaccjerk.z : Mean of frequency Body Accelerometer Jerk Signal Z Coordinate
*	mean.of.f.bodyaccjerkfreq.x : Mean of frequency Body Accelerometer Jerk Signal X Coordinate
*	mean.of.f.bodyaccjerkfreq.y : Mean of frequency Body Accelerometer Jerk Signal Y Coordinate
*	mean.of.f.bodyaccjerkfreq.z : Mean of frequency Body Accelerometer Jerk Signal Z Coordinate
*	mean.of.f.bodygyro.x : Mean of frequency Body Gyroscope on  X Coordinate
*	mean.of.f.bodygyro.y : Mean of frequency Body Gyroscope on  Y Coordinate
*	mean.of.f.bodygyro.z : Mean of frequency Body Gyroscope on  Z Coordinate
*	mean.of.f.bodygyrofreq.x : Mean of frequency Body Gyroscope Frequency X Coordinate
*	mean.of.f.bodygyrofreq.y : Mean of frequency Body Gyroscope Frequency Y Coordinate
*	mean.of.f.bodygyrofreq.z : Mean of frequency Body Gyroscope Frequency Z Coordinate
*	mean.of.f.bodyaccmag : Mean of frequency Body Accelerometer Magnitude 
*	mean.of.f.bodyaccmagfreq : Mean of frequency Body Accelerometer Magnitude Frequency
*	mean.of.f.bodybodyaccjerkmag : Mean of frequency Body Accelerometer Jerk Signal Magnitude
*	mean.of.f.bodybodyaccjerkmagfreq : Mean of frequency Body Accelerometer Jerk Signal Magnitude Frequency
*	mean.of.f.bodybodygyromag : Mean of frequency Body Gyroscope Magnitude 
*	mean.of.f.bodybodygyromagfreq : Mean of frequency Body Gyroscope Magnitude Frequency
*	mean.of.f.bodybodygyrojerkmag : Mean of frequency Body Gyroscope Jerk Signal Magnitude
*	mean.of.f.bodybodygyrojerkmagfreq : Mean of frequency Body Gyroscope Jerk Signal Magnitude Frequency
*	mean.of.bodyaccgravity.angle : Mean of Gravity Body Accelerometer Angle 
*	mean.of.bodyaccjerkmeangravity.angle : Mean of Gravity Body Accelerometer Mean Angle
*	mean.of.bodygyrogravity.angle : Mean of Gravity Body Gyroscope Angle 
*	mean.of.bodygyrojerkmeangravity.angle : Mean of Gravity Body Gyroscope Jerk Signal MeanAngle
*	mean.of.xgravity.angle : Mean of Angle Gravity on X Coordinate  
*	mean.of.ygravity.angle : Mean of Angle Gravity on Y Coordinate  
*	mean.of.zgravity.angle : Mean of Angle Gravity on Z Coordinate  
*	meanstd.of.t.bodyacc.x : Mean of Standard Deviation of Body Accelerometer on  X Coordinate
*	meanstd.of.t.bodyacc.y : Mean of Standard Deviation of Body Accelerometer on  Y Coordinate
*	meanstd.of.t.bodyacc.z : Mean of Standard Deviation of Body Accelerometer on  Z Coordinate
*	meanstd.of.t.gravityacc.x : Mean of Standard Deviation of Gravity Accelerometer on  X Coordinate
*	meanstd.of.t.gravityacc.y : Mean of Standard Deviation of Gravity Accelerometer on  Y Coordinate
*	meanstd.of.t.gravityacc.z : Mean of Standard Deviation of Gravity Accelerometer on  Z Coordinate
*	meanstd.of.t.bodyaccjerk.x : Mean of Standard Deviation of Body Accelerometer Jerk Signal X Coordinate
*	meanstd.of.t.bodyaccjerk.y : Mean of Standard Deviation of Body Accelerometer Jerk Signal Y Coordinate
*	meanstd.of.t.bodyaccjerk.z : Mean of Standard Deviation of Body Accelerometer Jerk Signal Z Coordinate
*	meanstd.of.t.bodygyro.x : Mean of Standard Deviation of Body Gyroscope on  X Coordinate
*	meanstd.of.t.bodygyro.y : Mean of Standard Deviation of Body Gyroscope on  Y Coordinate
*	meanstd.of.t.bodygyro.z : Mean of Standard Deviation of Body Gyroscope on  Z Coordinate
*	meanstd.of.t.bodygyrojerk.x : Mean of Standard Deviation of Body Gyroscope Jerk Signal 
*	meanstd.of.t.bodygyrojerk.y : Mean of Standard Deviation of Body Gyroscope Jerk Signal Y Coordinate
*	meanstd.of.t.bodygyrojerk.z : Mean of Standard Deviation of Body Gyroscope Jerk Signal Z Coordinate
*	meanstd.of.t.bodyaccmag : Mean of Standard Deviation of Body Accelerometer Magnitude 
*	meanstd.of.t.gravityaccmag : Mean of Standard Deviation of Gravity Accelerometer Magnitude 
*	meanstd.of.t.bodyaccjerkmag : Mean of Standard Deviation of Body Accelerometer Jerk Signal Magnitude
*	meanstd.of.t.bodygyromag : Mean of Standard Deviation of Body Gyroscope Magnitude 
*	meanstd.of.t.bodygyrojerkmag : Mean of Standard Deviation of Body Gyroscope Jerk Signal Magnitude
*	meanstd.of.f.bodyacc.x : Mean of Standard Deviation of Body Accelerometer on  X Coordinate
*	meanstd.of.f.bodyacc.y : Mean of Standard Deviation of Body Accelerometer on  Y Coordinate
*	meanstd.of.f.bodyacc.z : Mean of Standard Deviation of Body Accelerometer on  Z Coordinate
*	meanstd.of.f.bodyaccjerk.x : Mean of Standard Deviation of Body Accelerometer Jerk Signal X Coordinate
*	meanstd.of.f.bodyaccjerk.y : Mean of Standard Deviation of Body Accelerometer Jerk Signal Y Coordinate
*	meanstd.of.f.bodyaccjerk.z : Mean of Standard Deviation of Body Accelerometer Jerk Signal Z Coordinate
*	meanstd.of.f.bodygyro.x : Mean of Standard Deviation of Body Gyroscope on  X Coordinate
*	meanstd.of.f.bodygyro.y : Mean of Standard Deviation of Body Gyroscope on  Y Coordinate
*	meanstd.of.f.bodygyro.z : Mean of Standard Deviation of Body Gyroscope on  Z Coordinate
*	meanstd.of.f.bodyaccmag : Mean of Standard Deviation of Body Accelerometer Magnitude 
*	meanstd.of.f.bodybodyaccjerkmag : Mean of Standard Deviation of Body Accelerometer Jerk Signal Magnitude
*	meanstd.of.f.bodybodygyromag : Mean of Standard Deviation of Body Gyroscope Magnitude 
*	meanstd.of.f.bodybodygyrojerkmag : Mean of Standard Deviation of Body Gyroscope Jerk Signal Magnitude


