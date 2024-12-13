# Titanic: Machine Learning from Disaster

Hi there! Welcome to a **deep study** for the *Titanic - Machine Learning from Disaster* competition, hosted by **Kaggle**. You can find my original competition notebook in this [link](https://www.kaggle.com/code/fertmeneses/titanic-kaggle-full-analysis)👈🏽.

Here, I tell you the story, in simple terms, of how I've used **feature engineering**, **data edition** and **Machine Learning techniques** to train an algorithm that can predict whether a passenger survived the Titanic disaster based on many indicators such as their age, title and the fare they paid.

The progamming code is written in Python language, including well-known libraries like **pandas**, **numpy**, **matplotlib**, **sklearn** and **xgboost**.

## Introduction

<img src="assets/Titanic_colorized.png" width=100%>

The Titanic started its voyage in Southampton (UK) on 10 April 1912, made stops in Cherbourg (France), Queenstown (nowadays Cobh, Ireland) and then sailed to New York (US). Unfortunately, the ship never reached its destination but **sank in the Atlantic ocean on 15 April 1912, after colliding with in iceberg**.

The collision with the iceberg ocurred around 23:40, with most of the passengers already gone to bed, and the evacuation was carried out in a very disorganized way, with unequal treatment of passengers from different classes. **The 20 lifeboats carried by the ship could only accomodate 1,178 people, out of the 2,224 passengers and crew**. The vessel RMS Carpathia arrived about 2 hours after the sinking, rescuing all survivors at that time.

<img src="assets/Timeline_Titanic.png" width=100%>

## Machine Learning expectations

What do we expect from the Machine Learning approach in this challenge? Although we have much information available, **predicting whether a passenger survived the Titanic tragedy is not a deterministic problem**. Some passengers had a higher chance of survival than others, for example given their class or gender, but that didn't translate into certainty. Although the Machine Learning algorithm should easily find clear correlations between the dataset features and the survival chance, **the real challenge is to discover "hidden" information, those subtle within the data patterns that escape our human intuition and may improve the predictions**.

By July/2024, the Leaderboard for the Kaggle competition showed the results of 17,700 submissions, evaluated by the predictions' accuracy (from 0 to 1) on the testing dataset. More than half of the submissions scored between 0.75 and 0.80, with **more than 6,000 results between 0.7725 and 0.7775**. As a reference, the competition offers a very basic tutorial with a score of 0.7750. Based on these results, **achieving a score close to 0.80% is already a challenge**. As a curious fact, I will not neglect that some participants reached 1.00 (perfect) accuracy, but that's only because they are using a file with the solution, where all correct predictions can be manually copied and submitted!

<img src="assets/LB_Titanic_figure.png" width=100%>

## Feature engineering

The Titanic competition includes **two datasets: "train", with 891 entries** and explicit information about the passenger's survival; and **"test", with 418 entries** and missing survival information. Both datasets share the same features (other than "Survived"), although none of them are complete, meaning that they have scattered missing fields.

**Original features:**

- **Survival**: Whether a passenger survived (1) or not (0). [Only in training dataset]
- **Name**: Passenger full name, including their title.
- **Pclass**: Passenger class, either 1st (upper), 2nd or 3rd (lower) class.
- **Sex**: Female or male.
- **Age**: Age in years.
- **Sibsp**: Number of siblings and spouse aboard the Titanic.
- **Parch**: Number of parents and children aboard the Titanic.
- **Ticket**: Ticket number.
- **Fare**: How much the passenger paid for their ticket.
- **Cabin**: Cabin number.  
- **Embarked**: Port of embarkation (Cherbourg, Queenstown or Southampton)

Some features carry straight-forward information, such as Pclass, Sex or Age. Other features, for example Cabin or Name, are less obvious or have encoded information. Below, you will find the **original distribution and survival rates** for the Age and Sex features, as well as a WordCloud for the Cabin feature (listing all unique values). 

<img src="assets/Distribution_Rates_Sex.png" width=100%>
<img src="assets/Distribution_Rates_Age.png" width=100%>
<img src="assets/Cabin_Wordcloud_Original.png" width=100%>

In all cases, the missing values were filled according to carefully chosen criteria for each feature. Furthermore, **new features were engineered based on the original information**. For example, I generated the new Title feature from the Name data, which encodes information about the gender (Mr. vs Ms.), age (Master vs Mr., only for males) and marital status (Ms. vs Mrs., only for females). There were other titles such as Dr., Countess or Capt., much less frequent, which I grouped in the "Rare" category.

<img src="assets/Distribution_Rates_Title.png" width=100%>

Another example of feature engineering is the **heavy data edition for the Cabin feature, with 80% missing values!** Normally, such incomplete feature would be dropped, but in this case there is a high correlation between missing Cabin features and low survival rates, probably because the cabin data couldn't be retrieved from the victims. Therefore, I compute the missing values as "X", and additionally group the known values according to the deck level in the ship, named from "A" to "G" in descending order.

<img src="assets/Distribution_Rates_Cabin.png" width=100%>

CONTINUE FROM HERE






<img src="assets/Correlations_Training.png" width=80%>

- - - - - - - - - - - - - - - - - -

[Machine Learning exploration]

Chart with models:

Simple, Ensemble, Stacking.

Model exploration:

<img src="assets/ML_results_02.png" width=80%>

Final optimization:

<img src="assets/ML_results_03.png" width=80%>

Xxxx

- - - - - - - - - - - - - - - - - -

[Final comments]

Final submission.

Discussion.