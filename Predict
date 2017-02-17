import pandas as pd
import matplotlib.pyplot as plt
%matplotlib inline
from sklearn.tree import DecisionTreeClassifier
f_data = pd.read_csv('TargetPath\Data.csv')
# 0 is Red Wine, 1 is White Wine
f_data.corr()
clf = DecisionTreeClassifier(random_state=0)
redwine = df_winetype.loc[df_winetype['Wine_Type'] == 0].copy()
whitewine = df_winetype.loc[df_winetype['Wine_Type'] == 1].copy()
trainredwine = redwine.sample(n=1000).copy()
trainwhitewine = whitewine.sample(n=1000).copy()
traindata = pd.concat([trainredwine,trainwhitewine])
 
cross_val_score(clf, traindata.drop(['Wine_Type'],axis=1), traindata['Wine_Type'], cv=10)
#good scores were obtained array([ 0.965, 0.97 , 0.98 , 0.97 , 0.965, 0.985, 0.985, 0.975, 0.975, 0.975])
#Here, we fit the model
clf.fit( traindata.drop(['Wine_Type'],axis=1), traindata['Wine_Type'])
 
predicted_types = clf.predict(df_winetype.drop(['Wine_Type'],axis=1))
actual_types = df_winetype['Wine_Type'].copy()
correct = 0
false = 0
for i in range(0,len(predicted_types)):
if predicted_types[i] == actual_types[i]:
correct = correct + 1
else:
false = false + 1
print correct
print false
print 1.0 * correct / len(predicted_types)
print 1.0 * false / len(predicted_types)
 
"""
6386
111
0.982915191627
0.0170848083731
"""
#The following line can be used to see the decision tree !
tree.export_graphviz(clf,out_file='TargetPath\winetype.dot')
