# sales-analysis
bar plot and count plot of the sales of shop data (orders,amount,state) 
import pandas as pd 
import requests
import matplotlib.pyplot as plt # visualizing data
import seaborn as sns

f=df = pd.read_csv(r"C:\Users\ashish thakral\OneDrive\Desktop\Diwali Sales Data.csv",encoding='unicode_escape')
f.shape
f.head()
#f.info()
f.drop(['Status', 'unnamed1'], axis=1, inplace=True)
#f.info()
pd.isnull(f).sum()
f.dropna(inplace=True)
f['Amount'] = f['Amount'].astype('int')
f['Amount'].dtypes
f.columns
#f.rename(columns= {'Marital_Status':'Shaadi'})
#f[['Age', 'Orders', 'Amount']].describe()
#ax = sns.countplot(x = 'Gender',data = f)

#for bars in ax.containers:
 #   ax.bar_label(bars)
#plt.show()

#sales_gen=f.groupby(['Gender'],as_index=False)['Amount'].sum().sort_values(by='Amount',ascending=False)
#sns.barplot(x='Gender',y='Amount',data=sales_gen)
#plt.show()
#ax = sns.countplot(data=f,x = 'Age Group', hue='Gender')
#for bars in ax.containers:
 #   ax.bar_label(bars)
#plt.show()

#sales_age=f.groupby(['Age Group'],as_index=False)['Amount'].sum().sort_values(by='Amount',ascending=False)
#sns.barplot(x='Age Group',y='Amount',data=sales_age)
#plt.show()

#sales_state = f.groupby(['State'], as_index=False)['Orders'].sum().sort_values(by='Orders', ascending=False).head(10)

#sns.set(rc={'figure.figsize':(15,5)})
#sns.barplot(data = sales_state, x = 'State',y= 'Orders')
#plt.show()

#ax = sns.countplot(data = f, x = 'Marital_Status')

#sns.set(rc={'figure.figsize':(7,5)})
#for bars in ax.containers:
 #   ax.bar_label(bars)
#plt.show()

#sales_state = df.groupby(['Marital_Status', 'Gender'], as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False)

#sns.set(rc={'figure.figsize':(6,5)})
#sns.barplot(data = sales_state, x = 'Marital_Status',y= 'Amount', hue='Gender')
#plt.show()

#sns.set(rc={'figure.figsize':(20,5)})
#ax = sns.countplot(data = f, x = 'Occupation')

#for bars in ax.containers:
#    ax.bar_label(bars)
#plt.show()

#sales_occu = f.groupby(['Occupation'], as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False)

#sns.set(rc={'figure.figsize':(20,5)})
#sns.barplot(data = sales_occu, x = 'Occupation',y= 'Amount')
#plt.show()
#sns.set(rc={'figure.figsize':(20,5)})
#ax = sns.countplot(data = f, x = 'Product_Category')

#for bars in ax.containers:
#    ax.bar_label(bars)
#plt.show()
fig1, ax1 = plt.subplots(figsize=(12,7))
f.groupby('Product_ID')['Orders'].sum().nlargest(10).sort_values(ascending=False).plot(kind='bar')
plt.show()



#conclusion
#Married women age group 26-35 yrs from UP, Maharastra and Karnataka working in IT, Healthcare and Aviation are more likely to buy products from Food, Clothing and Electronics category
