# Introduction
A store wants to analyse their diwali sales using the data they generated using sales to better unnderstand their customer behavior so as to provide improve customer experience and in return help their business grow.

# Tools I Used
- Pandas : For data cleaning & manipulation
- Seaborn : For data visualization

# The analysis

### 1. Gender vs count
```python
ax = sns.countplot(x = 'Gender',data = df)

for bars in ax.containers:
    ax.bar_label(bars)
```
![Gender vs count](images/gender.png)

### 2. Gender vs total amount
```python
sales_gen = df.groupby(['Gender'], as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False)

sns.barplot(x = 'Gender',y= 'Amount' ,data = sales_gen)
```
![Gender vs total amount](images/gender%20vs%20amount.png)

### 3. Age group
```python
ax = sns.countplot(data = df, x = 'Age Group', hue = 'Gender')

for bars in ax.containers:
    ax.bar_label(bars)
```
![Age group](images/age%20group.png)

### 4. Total amount vs age group
```python
sales_age = df.groupby(['Age Group'], as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False)

sns.barplot(x = 'Age Group',y= 'Amount' ,data = sales_age)
```
![Total amount vs age group](images/total%20amount%20vs%20age%20group.png)

### 5. Total order - Top 10 states
```python
sales_state = df.groupby(['State'], as_index=False)['Orders'].sum().sort_values(by='Orders', ascending=False).head(10)

sns.set(rc={'figure.figsize':(15,5)})
sns.barplot(data = sales_state, x = 'State',y= 'Orders')
```
![Total order - Top 10 states](images/total%20orders%20-%20top%2010%20states.png)

### 6. Marital status
```python
ax = sns.countplot(data = df, x = 'Marital_Status')

sns.set(rc={'figure.figsize':(7,5)})
for bars in ax.containers:
    ax.bar_label(bars)
```
![Marital status](images/marital%20status.png)

### 7. Occupation
```python
sns.set(rc={'figure.figsize':(20,5)})
ax = sns.countplot(data = df, x = 'Occupation')

for bars in ax.containers:
    ax.bar_label(bars)
```
![Occupation](images/occupation.png)


