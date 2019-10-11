# ds_forest_fires

This ML project using and exploring different models in SciKit Learn using data on wildfires from the UCI Machine Learning repository located https://archive.ics.uci.edu/ml/datasets/forest+fires

The data set contains dates, current conditions (temp (Celcius), RH (relative humidity), wind speed, and rain), several different indexes that indicate for fuel moisture and wind, and area burned. To turn the problem into a classification problem, fire area was converted to ones and zeroes to indicate that absense or presence of fire. The target data was the presence/absense of fire.

This dataset is easy to work with as far as cleaning goes. However the small size of the dataset and the features made it difficult to build useful models with. I applied Logistic Regression, Support Vector Machine, and several different tree based models. I was hoping to build a good model with logistic regression, in order to evaluate fire risk for a particular day, but the best model ended up being a SVM model.

### Logistic Regression
First I tried logistic regression, as to use the .predict_proba() function to give a risk of fire for a particular day. The model turned out to have pretty terrible metrics, regardless of what solver I used ('newton-cg' ended up being the best). The accuracy was barely better that 50%, and given there were only two classes (1 or 0) this model was barely better than a naive guess.

### Support Vector Machines
I applied SVMs with almost no optimism after viewing the logistic regression metrics, but I was however pleasantly suprised that a few of the SVM models had slightly better metrics. The polynomial kernel produced an especially interested result as it had a minimal amount of false negatives, a high amount of false positives (which is a good thing for forest fire risk, better safe than sorry) and an accuracy over 60%. This ended up being the best model that I was able to produce with the data set.

Decision Trees, Random Forest, and Extra Trees classifiers
I applied a few different ensemble methods as they are considered some of the stronger models for classification. However the metrics ended up being worse than the other models that I tried

### Conclusion
I would really like to find a more robust data set and further explore this question. A strong LogReg model could be a very useful tool to determine fire risk, especially in the wary atmosphere of a fire scarred California. Deep learning methods could also be explored to answer this question, determining fuel density of a specific region using image recognition tools. I plan on finding better data and continuing to explore this issue
