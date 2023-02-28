# CAPSTONE-PROJECT-3--CLASSIFICATION 
#Email Campaign Effectiveness Prediction

#Problem Statement
Most of the small to medium business owners are making effective use of Gmail-based Email marketing Strategies for offline targeting of converting their prospective customers into leads so that they stay with them in Business. 
The main objective is to create a machine learning model to characterize the mail and track the mail that is ignored; read; acknowledged by the reader.

#Project Description
Sending email is one of the alternatives used by Companies to tell and promote certain event sale to users. With the ability to be able to predict whether user is reading or not reading the email, enable Companies to evaluate their crew works during campaign period until event launch. This is because, when user is open the email, the possibility of that user know there is an event or promo will be highly increased and also increasing the possibility of that user do transaction during event period. Therefore, with the making of this model, hopefully Companies be able to build a strategy for future marketing.

#Attribute Information:-
Email_ID - This column contains the email ids of individuals.

Email_type - Email type contains 2 categories 1 and 2. We can assume that the types are like promotional email or sales email.

Subject_Hotness_Score - It is the subject-line effectiveness score.

Email_Source - It represents the source of the email like sales,marketing or product type email.

Email_Campaign_Type - Campaign type

Total_Past_Communications - This column contains the previous mails from the source.

Customer_Location - Categorical data which explains the different demographic location of the customers.

Time_Email_sent_Category - It has 3 categories: 1,2 and 3 which are considered as morning,evening and night time slot.

Word_Count - It contains the no.of words in the mail.

Total_Links - Total links in the email body.

Total_Images - The banner images in the email body.

Email_Status - It is the target variable which contains the characterization of the mail that is ignored; read; acknowledged by the reader.

 #conclusion:
 #Exploratory Data Analysis:

In the customer location feature we can find that irrespective of the location, the percentage ratio of emails being ignored, read and acknowledged are kind of similar. It does not exclusively influence our target variable. It would be better to not consider location as a factor in people ignoring, reading or acknowledging our emails.

In the Email Campaign Type feature, it seems like in campaign type 1 very few emails were sent but has a very high likelihood of getting read. Most emails were sent under email campaign type 2 and most ignored. Seems like campaign 3 was a success as even when less number of emails were sent under campaign 3, more emails were read and acknowledged.

Time email sent category cannot be considered as a relevant factor in classifying the emails. Both the feature importance showed this particular thing. If we consider Time email sent category 2 as middle of the of course they are going to be read and acknowledged more than morning and night.

Analyzing total past communications, we can see that the more the number of previous emails, the more it leads to read and acknowledged emails. This is just about making connection with your customers.

The more the words in an email, the more it has a tendency it has to get ignored. Too lengthy emails are getting ignored.

More images were there in ignored emails.

There are outliers in almost every continuous variable except Word Count and upon analyzing, it was found that outliers make up for more than 5% of the minority data and will influence the results either way, so it was better not to get rid of them.

#Modeling:

Imbalanced Class Handling techniques such as Undersampling and SMOTE were done after train-test split only on the training data, to make sure that the model doesn't catch up to the test set at all and it remains unknown which somewhat reduced our results.

It is observed that SMOTE worked considerably better than Random Undersampling, it may have led to loss of information. Decision Tree Model is overfitting. It is working really great on train data and worse on test data.

#XGBoost Algorithm worked in the best way possible with such imbalanced data with outliers, with F1 Score of 0.71 on the test set USING rus and 0.86 using SMOTE
