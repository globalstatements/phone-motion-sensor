Study and Source Data
=====================

Data was obtained from a study that collected motion data from phone motion sensors.
The dataset "Human Activity Recognition Using Smartphones Data Set" is available from:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The dataset is used under the following license terms:

> Use of this dataset in publications must be acknowledged by referencing the following publication [1] 
>
> [1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. 
> Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine.
> International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012
>
> This dataset is distributed AS-IS and no responsibility implied or explicit can be 
> addressed to the authors or their institutions for its use or misuse. Any commercial use is prohibited.

Use of Source Data
==================

Eight source files were relevant for the purposes of this project, and among those,
seven are used as input in the R script. The original measurement data was
divided randomly into training and test groups, resulting in two sets of files. From each group I
used the motion vector files along with the separate activity code and subject ID files.
An additional file translated from numeric codes for activities to text descriptions, such as "WALKING".

The motion vector measurements, or features, are identified in a separate file. I used these names,
but with hyphens converted to underscores and other punctuation removed to create valid R object names.

Transformations
===============

R script actions are required to import each of the source files, then further actions were taken to
combine them. A simple column-bind action connects the three files of each group, then a row-bind
action combines the two groups to form a single set for study.

Only a small fraction of the features, those identified as mean and standard deviation of original
sensor values, were identified for use in this project. These feature names are listed in the
stat_measure object in the R script.

Analysis
========

The only analysis done was to compute the mean of each measure, split according to activity and subject.
This summary data is exported at the end of the R script.
