# AIM -
The Aim of this project is to make valuable predictions on **year over year growth** which is very essential in investment banking considering India, as investors usually want to see your year-over-year numbers before supplying you with business capital as well as YOY is a great statistic to use when you want to control the effects of volatility when comparing companies or economies.

# Algorithms Used :


# AdaBoost -
AdaBoost is best used to boost the performance of decision trees on binary classification problems.AdaBoost was originally called AdaBoost.M1 by the authors of the technique Freund and Schapire. More recently it may be referred to as discrete AdaBoost because it is used for classification rather than regression.AdaBoost can be used to boost the performance of any machine learning algorithm. It is best used with weak learners. These are models that achieve accuracy just above random chance on a classification problem.The most suited and therefore most common algorithm used with AdaBoost are decision trees with one level. Because these trees are so short and only contain one decision for classification, they are often called decision stumps.Each instance in the training dataset is weighted. The initial weight is set to:

**weight(xi) = 1/n**

Where xi is the i’th training instance and n is the number of training instances.
AdaBoost, short for “Adaptive Boosting”, is the first practical boosting algorithm proposed by Freund and Schapire in 1996. It focuses on classification problems and aims to convert a set of weak classifiers into a strong one. The final equation for classification can be represented as
<div>
<img src="https://miro.medium.com/max/294/1*B2987FKIw3QL2ClYR_OeuQ.jpeg" width="200"/>
</div>
where f_m stands for the m_th weak classifier and theta_m is the corresponding weight. It is exactly the weighted combination of M weak classifiers. The whole procedure of the AdaBoost algorithm can be summarized as follow.

AdaBoost algorithm
Given a data set containing n points, where


<div>
<img src="https://miro.medium.com/max/235/1*2fp-O3KfXqrdYEGU_RjY0w.jpeg" width="200"/>
</div>


Here -1 denotes the negative class while 1 represents the positive one.
Initialize the weight for each data point as:


<div>
<img src="https://miro.medium.com/max/273/1*IMHTVrXPKc2mVqDDK40k9w.jpeg" width="200"/>
</div>


**For iteration m=1,…,M:**
(1) Fit weak classifiers to the data set and select the one with the lowest weighted classification error:
<div>
<img src="https://miro.medium.com/max/194/1*C8-yNia8Oh44X-t0UxUCUA.jpeg" width="200"/>
</div>


(2) Calculate the weight for the m_th weak classifier:
<div>
<img src="https://miro.medium.com/max/206/1*jFpUGuxpGZuzpG6FlDAASw.jpeg" width="200"/>
</div>


For any classifier with accuracy higher than 50%, the weight is positive. The more accurate the classifier, the larger the weight. While for the classifer with less than 50% accuracy, the weight is negative. It means that we combine its prediction by flipping the sign. For example, we can turn a classifier with 40% accuracy into 60% accuracy by flipping the sign of the prediction. Thus even the classifier performs worse than random guessing, it still contributes to the final prediction. We only don’t want any classifier with exact 50% accuracy, which doesn’t add any information and thus contributes nothing to the final prediction.
(3) Update the weight for each data point as:
<div>
<img src="https://miro.medium.com/max/465/1*mqLcX8yookiPVZoAe6iwqA.jpeg" width="400"/>
</div>
where Z_m is a normalization factor that ensures the sum of all instance weights is equal to 1.
If a misclassified case is from a positive weighted classifier, the “exp” term in the numerator would be always larger than 1 (y*f is always -1, theta_m is positive). Thus misclassified cases would be updated with larger weights after an iteration. The same logic applies to the negative weighted classifiers. The only difference is that the original correct classifications would become misclassifications after flipping the sign.
After M iteration we can get the final prediction by summing up the weighted prediction of each classifier.


# TPOT :
TPOT is meant to be an assistant that gives you ideas on how to solve a particular machine learning problem by exploring pipeline configurations that you might have never considered, then leaves the fine-tuning to more constrained parameter tuning techniques such as grid search.So TPOT helps you find good algorithms. Note that it isn’t designed for automating deep learning — something like AutoKeras might be helpful there.
<div>
<img src="https://miro.medium.com/max/2000/0*iYQTbI4WVGUF1_F1.png" width="600"/>
</div>
TPOT is built on the scikit learn library and follows the scikit learn API closely. It can be used for regression and classification tasks and has special implementations for medical research.
TPOT is open source, well documented, and under active development. It’s development was spearheaded by researchers at the University of Pennsylvania. TPOT appears to be one of the most popular autoML libraries, with nearly 4,500 GitHub stars as of August 2018.TPOT has what its developers call a genetic search algorithm to find the best parameters and model ensembles. It could also be thought of as a natural selection or evolutionary algorithm. TPOT tries a pipeline, evaluates its performance, and randomly changes parts of the pipeline in search of better performing algorithms.
