# DDL Judicial Data Analysis

### Overview

This repository contains analysis done on the Judicial data set created by the Data Development Lab which contains information of almost 80 million cases from the year 2010 to 2018.

The project is divided into two parts: the Analysis part, where Analysis was done on the data, and various insights were derived from it, and Classification part, where classification problems were formulated, models were trained and their performance was analyzed.

### Environment and Libraries used

The analysis was done using Kaggle's workspaces as it is very easy to install various dependencies that were needed for the project. 

The following dependancy libraries were used in the project:

**Pandas** - used to read csv files, and too manipulate the dataframes

**Dask** - This library was used to read the large csv files, and to perform computations on them as the pandas library does have some limitations when it comes to datsets of this size

**Seaborn and Matplotlib** - Used for the plotting requirements in the project

**datetime** - used to engineer the 'time_taken` feature, which is one of the focal points of the analysis

**glob and gc** - Glob is used to get the list of the files to be read, while gc is used to force garbage collection

**Sklearn** - Sklearn was used for the ML requirements in the project, including the datapreprocessing and training the models

**yellowbrick** - This library was used to plot the ROC curve, which is an important indicator of the model's peformance

**b2zfile and pickle** - The pickle library is used to save the trained models. The b2zfile is used to compress the pickled file.

### Approach Followed

#### Analysis section
The main purpose of the analysis was to understand the time taken for a case to be concluded, from the time of filing of the case to the date of the decision. Each Analysis notebook tries to understand different aspects of this feature by looking at it's correlation with various other features. 

###### Analysis-1
In the first analysis notebook, the correlation between the time taken and the gender of the judge is analyzed. The time taken for both Male and Female judges given a case under a particular act and section is compared and the difference is further analyzed by looking at time taken in criminal and non-criminal cases. The analysis is done year wise from the years 2010 - 2018.

According to the most recent data from 2018,it was found that Female judges on average take a week longer than Male judges to decide a case. The analysis of the criminal and non-crimmnal cases are interesting. Male judges take 15 days less on average in dealing with criminal cases, while in non-criminal cases, it is women who ouutshine men, taking 12 days less thanmen on average. 

**Insights**
1. Criminal Cases are more frequently dealt with and take more time on average to conclude, and hence any Legal AI system built to augment the judicial process will be more valued in criminal cases

2. Female judges have rapidly caught up with Male judges in terms of the time taken to decide cases, and in fact are seen to decide non-crminal cases more quickly than male judges. This may show that Male judges in particular may need some help in deciding non-criminal cases, and may be more benefitted by a Legal AI system in these cases. Also, understanding the deeper reasons behind why female judges are dealing woth non-crminal cases more quickly could help in the building of such an AI system

###### Analysis-2
In the second analysis notebook, a state wise analysis is conducted to understand the average time taken for a case to be concluded in each state. The number of cases in each state in the year 2018 is also analyzed and with this information, the analysis tries to understand which states may need more resources poured into legal system.

Analysis was also done on the ratio of Female judges in each state, and it's correlation between the time taken to conclude a case. It was found that out of the 6 states that have the Female judge ratio of over 40 percent, in 5 of these states the average time raken is well below the national average.

**Insights**

1.West Bengal, Gujarat and the other states that were seen to be above or close to the national average in both No of cases and average time taken to handle cases are the places where resources are needed to help with the judicial system. These states also might be a startng to point to begin the implementation of a legal AI system to help augment the judicial process

2.The infusion of female judges into the judiciary seems to have a positive effect on the time taken to decide a case. While it is clearly not the only factor at play, understanding this correlation may help in improving the judicial syatem in India.

###### Analysis-3
In the third analysis notebook, the correlation between the time taken to and the gender of the both the judge and the defendant is analyzed. Furtherore, the analysis also dives into both Male and Female judges, and the tinme they take to conclude cases with defendants of both gender.

**Insights**
1. Both male and female judges seem to take more time to decide cases where the defendant is female. This insight points us in a direction where we can further analyze the time taken by judges and ways to reduce them.


###### Analysis-4
In analysis notebook 4, a new feature is introduced. "Tenure" of a judge which is the days of of experience the judge had at the time of decision.  The data was initially clustered using the k-means clustering algorithmn. These clusters were used for further analysis, and the correlation between the tenure of the judge and the time taken for a case to be concluded was analyzed.

**Insights**
1. Average tenure of judges dealing with non-criminal cases is higher than that of the judges dealing with criminal cases. This could be a contributing factor to the reduced time_taken to deal with non-criminal cases, which we have seen here and in more detail in Analysis-1.

2. The correlation between tenure and time_taken can again be seen when we observe the gender split. The tenure of Female judges can be seen to be less than that of Male judges on average, and this correlates to the time taken of Female judges greater than that of Male judges


#### Classification section

The goal of the classification section is to more or less confirm the analysis, done in the Analysis section of the project. The models are trained with the features that we have used throughout the analysis section, fed into the models, and the performance of the models will inform us about whether our analysis was in the right direction or not.

The noteboooks for both the classification problems go in-depth into the entire pipeline from the data pre-processing to the training of the models and finally the performance analysis of each model. I recommned given them a look for a better understanding of the classification problems.

###### Classification-1

In the first classification problem, the dataset is divided into 4 different classes, based on the gender of the judge and the defendant. 2 models were trained on the datset. The first was a OneVsOne SGD Classifier, which performed quite poorly, while the second model, which was a RandomForest Classifier, had an improved performance. While the performance of the RandomForest classifier was far from ideal, it did show some learning, which was encouraging.

**Insights**
1. The performance model shows us that there is some correlation between the provided features and the genders of both the judge and the defendant given.

2. While the model shows us that there is some correlation, the performance of the models were far from ideal and tells us that while the features do show some correlation, more information is needed for better analysis and results

3. From the first point we can infer that the analysis done in the Analysis notebooks in this project were in the right direction, drawing on the correlation between these features

A link to the RandomForest Classifier model is provided [here](https://drive.google.com/file/d/1NP-eFhkxEuwdglCp3BHP4h2ke3T3FxID/view?usp=sharing)

In order to use the model to be used, it first be decompressed as, due to its large size the b2zfile library in python was used to compress the pickled file.
The decompressed file can be obtained by using the following function:
```python
def decompress_pickle(file):
 data = bz2.BZ2File(file, ‘rb’)
 data = cPickle.load(data)
 return data
```

###### Classification-2
In this a case, a binary classificiation problem was framed based on the tenure feature. The dataset was split into 2 classes, Experienced Judges, who were the judges that had a tenure more than the overall median of the tenure featured, and Novice judges, who were the judges with a tenure below the median.

Three different models were trained on the data: a SGD Classfier, a RandomForest Classifier, and a Multilayer Perceptron Classifier. The performance of all three models were pretty decent, with all of them learning from the data. The performance of the MultiLayer Perceptron slightly edged out the performance of the other 2 classifiers.

**Insights**
1. From the analysis of the metrics for each model, we can see that there is a decent correlation between the features used and the tenure of the judge.

2. The performance of the model however, does leave a lot to be desired, and thus more relevant features would be required to train more accurate models

3. The correlation of the feature does confirm analysis done in the Analysis section of the project, especially the Analysis done in the Analysis-4 notebook

A link to the MultiLayer Perceptron Classifier model is provided [here](https://drive.google.com/file/d/1Qj1NPTzrmOw2GbLWULJqyg8mFyQpc_sH/view?usp=sharing)

Here the model has not been compressed and therefore can simply be accessed by using the following code snippet

```python
data = pickle.load(open(file_path, 'rb'))
```





