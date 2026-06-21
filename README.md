# Pokemon-Classification-and-Regression
ML classification and regression tasks performed on a Pokemon dataset


The dataset info 
                #      Total          HP      Attack     Defense     Sp. Atk  \
count  800.000000  800.00000  800.000000  800.000000  800.000000  800.000000   
mean   362.813750  435.10250   69.258750   79.001250   73.842500   72.820000   
std    208.343798  119.96304   25.534669   32.457366   31.183501   32.722294   
min      1.000000  180.00000    1.000000    5.000000    5.000000   10.000000   
25%    184.750000  330.00000   50.000000   55.000000   50.000000   49.750000   
50%    364.500000  450.00000   65.000000   75.000000   70.000000   65.000000   
75%    539.250000  515.00000   80.000000  100.000000   90.000000   95.000000   
max    721.000000  780.00000  255.000000  190.000000  230.000000  194.000000   

          Sp. Def       Speed  Generation  
count  800.000000  800.000000   800.00000  
mean    71.902500   68.277500     3.32375  
std     27.828916   29.060474     1.66129  
min     20.000000    5.000000     1.00000  
25%     50.000000   45.000000     2.00000  
50%     70.000000   65.000000     3.00000  
75%     90.000000   90.000000     5.00000  
max    230.000000  180.000000     6.00000  


Training Data Shape: (640, 51)
Testing Data Shape: (160, 51)
mse: 219.54887875
r2: 0.47133155939493965 
This are the metrics after dropping total otherwise the metrics are improved because Total = Sum of 6 individual stats so predicting with total intacts is basically guarenteed right answer.

I dont require type for predicting the HP but have still kept it in one hot encoding form

The result for the classicifaction problem 


--------------------------CLASSIFICATION-----------------------------------

[14]
#Classificaiton of legendary pokemon

#Reading the theory I assume the best model will be decision trees as it asks questions whether the total is above 580 or not and 
#a higher total is almost guaranteed a legendary 

#I Have one hot encoded legendary ehich i need to remove 

X = df.drop(columns=['Legendary_True', 'Legendary_False' ,'Name', 'Generation', '#'])

y = df['Legendary_True']

Training Data Shape: (640, 50)
Testing Data Shape: (160, 50)
Logistic Regression Accuracy: 0.93125
SVM Accuracy: 0.925
LDA Accuracy: 0.9125
Decision Tree Accuracy: 0.9125
Random Forest Accuracy: 0.925
Logistic Regression Precision: 0.6666666666666666
SVM Precision: 0.5
LDA Precision: 0.4166666666666667
Decision Tree Precision: 0.4166666666666667
Random Forest Precision: 0.5
Logistic Regression Recall: 0.16666666666666666
SVM Recall: 0.16666666666666666
LDA Recall: 0.4166666666666667
Decision Tree Recall: 0.4166666666666667
Random Forest Recall: 0.3333333333333333

Interesting thing to note is while the accuracy is high for the training dataset about 93% pokemon are normal and rest are legendary so even if model predicts normal for each and every pokemon it still gets 93% accuracy, its not like sports where each team has roughly 50% winning odds so accuracy is irrelevant here


