### Classification section

The goal of the classification section is to more or less confirm the analysis, done in the Analysis section of the project. The models are trained with the features that we have used throughout the analysis section, fed into the models, and the performance of the models will inform us about whether our analysis was in the right direction or not.

The notebooks for both the classification problems go in-depth into the entire pipeline from the data pre-processing to the training of the models and finally the performance analysis of each model. I recommned given them a look for a better understanding of the classification problems.

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