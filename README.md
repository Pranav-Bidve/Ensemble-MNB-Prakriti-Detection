
# AyurPredict

## This project addresses overlapping 'Prakriti' clusters  by analyzing multiple characteristics of individuals, clustering data into seven groups using the k-modes method.

Ayurveda, an ancient holistic medical science from the Indian subcontinent, classifies individuals based on 'doshas'—three fundamental energies governing the body and mind. Each person has a unique combination of these doshas, influencing their physical, mental, and emotional characteristics. This project expands the traditional three-segment classification of 'Prakriti' types into seven overlapping categories using k-modes clustering to better capture the intricate combinations of 'doshas'.

* 'Prakriti' in Ayurveda categorizes individuals into three primary types 'doshas'—'VATT-Dosha', 'PITT-Dosha', and 'KAPH-Dosha'.

* This project expands the three 'Prakriti' types into seven categories, including overlapping 'doshas' like 'VATT-PITT-Dosha' and 'PITT-KAPH-Dosha'.
  
* K-modes clustering groups individuals into seven overlapping categories, tailored for categorical data by considering the mode of each attribute.

## Model Description
![Model](https://github.com/Pranav-Bidve/ayurpredict/blob/main/img/model.png)

* The [dataset](https://github.com/skarifahmed/DeepAyurveda/blob/main/src/all_models/train_test.csv) used concsists of 133 attributes from 147 individuals, capturing various human body characteristics to avoid bias.
* Missing values are handled with forward-filling, efficiently substituting previous non-missing values for categorical data, followed by feature engineering.
* Chi-square test (sklearn) evaluates each attribute's contribution to predicting 'doshas' with f-scores and p-values.
* SelectKBest ranks features by significance, using ANOVA for numerical data and chi-square for categorical data.
* The multinomial naïve Bayes classifier uses Bayes' theorem to classify categorical values and predict the 'Prakriti' class for new instances by calculating the likelihood of each class.

# Results

* The dataset is split into 80% training and 20% testing subsets to avoid overfitting, with training data fitted into the model and testing data used to evaluate accuracy, precision, f-score, and recall.
* Two MNB classifier variants are considered: standard MNB and ensemble MNB, with evaluation considering testing dataset size and the number of attributes.
* Metrics provide insights into model performance, with test size adjusted regularly to ensure balanced training and testing, analyzing model behavior for test sizes of 40% and 60%.
* Performance is evaluated by gradually increasing test size from 0.2 to 0.5 and analyzing results using 40 and 60 features.

##  Performance of MNB classifier

* The MNB classifier achieved its best accuracy of 0.83 with 40 input features and a 20% test size.
* Accuracy and F-score decreased as the number of input features increased.
* The highest F-score recorded was 0.85, and the lowest was 0.67.

##  Performance of Ensemble MNB classifier

* The model outperformed the classical MNB classifier with better accuracy and reduced variance.
* Increasing the number of features from 40 to 60 showed an inverse relationship with accuracy, precision, f-score, and recall.
* Comparative analysis shows the ensemble model consistently performed better than the classical MNB classifier.

# Use Case

* Our findings differ from previous studies by classifying individuals into 7 'doshas' rather than 3, based on body features.
* This helps Ayurvedic practitioners quickly identify 'Prakriti' types and assess health conditions.
* Individuals can evaluate their health based on body characteristics and follow Ayurvedic guidance under professional supervision to maintain wellness.

