# Charity Deep Learning Model Overview

Some charity fundraisers are successful and others not. Why? Is it about the charty type, amount requested, use case, or something else?

By creating a deep learning neural network, we hope to create a model which predicts a charity's fundraising success using several criteria.

And by better understanding why some charitites are more successul fundraisers, perhaps other charities can learn a lesson from this data.

## The Data

34,294 charity fundraising applications were analyzed and the following factors were taken into consideration

* Application Type
* Affiliation
* Classification
* Use Case
* Organization
* Status
* Income Amount
* Special Considerations
* Ask Amount
* Success

By analyzing these factors, we hope to determine which criteria lead to success.

## Model Results

A neural network model provides some success in determining the expected success of a charity fundraising. To acheived this success, the model when through the following steps:

* Data Preprocessing

  * Target: "Is_Successful" column
  * Features:
    * Application Type
    * Affiliation
    * Classification
    * Use Case
    * Organization
    * Status
    * Income Amount
    * Special Considerations
    * Ask Amount
    * Success
  * Data removal: "EIN", "NAME", 'STATUS' and 'SPECIAL_CONSIDERATIONS' were removed because they were neither targets nor features
* Compiling, Training, and Evaluating the Model

  * A Keras Sequential model – with 5 layers and 191 nodes – run for 100 epochs was used to create the model. After significant trial an error, this combination gave the highest accuracy score
  * Model acheives 73% accuracy - less than the 75% target
  * In an effort to acheive 75% accuracy, I tried removing "affiliation", "use_case", "Organization", and "Status" columns seperately to see if performance improved. I put "Classification" and
    "Affiliation" in smaller bins, in case edge cases were important. I used a variety of diffferent activation methods for my hidden layers. I added hidden layers and nodes. Finally I added epochs. In the end, I was able to acheive the following accuracy:

    * Loss: 0.59
    * Accuracy: 0.73

## Summary

While not reaching the 75% accuracy threshold requested, this model is still reasonably effective in predicing charity fundraising success. It significantly beats the random guess and correctly identifies successful charities around 73% of the time.

It's not clear from the data what application type or classification are, and whether they're important. And with a 12 column dataset, there is a lot of noise. For future study, a PCA to determine the most important factors might be very beneficial before building a neural network. That way we'd only be evaluating the most relivant factors
