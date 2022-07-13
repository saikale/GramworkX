# GramworkX

Imported libraries like numpy for multidimensional arrays and libraries built on it like pandas,matplotlib.
Seaborn used for plotting graphs and inline to display these graphs below desired code block.

EDA
1. Data Sourcing

Importing the given Expenses dataset(.csv)file.

About the dataset:

The dataset contains 1338 rows and 7 columns. The columns present in the dataset are ‘age’,’ sex’,’bmi’, ’children’, smoker’, ’region’, and ‘charges’. 

Here I have taken the 'charges' column as the target column and the rest others are independent columns predicting the outcome.

The first column is 'age'. Age is an important factor for predicting expenses because younger people are generally more healthy than old ones,hence having lesser 
expenses than the old ones.

The second column is 'sex'.It has two Categories: Male and Female. The sex of the person can also play an important role in predicting expenses.

Next is the ‘bmi’ column, then BMI is Body Mass Index.

In general,for most adults, an ideal BMI is in the 18.5 to 24.9 range.For children and young people aged 2 to 18.The BMI calculation takes into account age and 
gender as well as height and weight. 

The fourth column is the ‘children’ column, which contains information on numbr of children they have.Expenses vary according to this factor as well because more the 
children more expenses because of their responsibility.

The fifth is the ‘smoker’ column. This is also one of the most important factors as it has a direct and chronic impact on health thus increasing the expenses.

Last one is the ‘region’ column.The cleanliness of the region determines the expenses if that indivisual.

2.Data Cleaning

To get rid of irregular data in the dataset.

1.Finding missing values in the columns in dataset

There are no missing values in the dataset.

Checking for datatypes

In the current dataset there are 3 categorial columns sex,smoker and region.

Converting these numeric values in the column sex and smoker to strings using the 'map' function for dictionary.

OneHotEncoder basically is used to convert categorical data in the form of a numerical values to be given to the ML algos for performing better prediction.

Using OneHotEncoder for transforming the region column into a matrix form.

This matrix maps 0 and 1 to respective regions to the rows in the dataset.

3.Dropping unnecessary columns

Dropping the region column as it is not necessary.

axis=1: specifies the entire column is to be dropped i.e.;both rows and columns.

inplace=True:Permanently removes this column from the df.

Concating both the df using 'concat' function by pandas.

To concat,passing the two df in a list and axis=1 for only column concatenation.

Splitting the data into X and Y.

Storing the predictor,dependent variable 'charges' in Y and independent other variables(except charges) in X.

This is end of EDA part.

ML MODEL

4.Train-Test Split

Using 'Linear Regression' for predicting the 'charge' values.

For predicting class labels Classification is used.

Splitting into Training and Testing using train test funcions and passing the X,Y parameters with testing size 15% and hence changing training size to 85%.

Using Linear Regression to find correlation between columns.

Visualizing the correlation using matplotlib functions by plotting correlation heatmap.

sns is seaborn and passing corr to heatmap and annot=True denotes all the columns age,sex,bmi,...etc.

styling is set to coolwarm and line width=2 gives enough spaces for clear visualisation.

In the heatmap,the scale at the right denotes the correlation,so the data as we go from bottom to top is more correlated.

All the 1 values are correlated to themselves,eg age correlated to age,etc.

'Smoker is correlated with charges'.

Since charges and smoker are correlated plotting them.

Using matplotlib libraries for plotting the charges based on smoker.

figsize: gives appropriate size.

scatter:for scatter plot passing X as smoker and Y.

labeling the axis.

From the scatter plot,The non-smokers have charges ranging from 0-38k(approx) and smokers have spending of about 12k-above 60k.It forms a polynomial.

Making use of this data to build model.

Using Train test split to feed the Linear Regression model.

Training the model:

The fit method trains model depending on the X,Y value passed.Since I am doing it on training data passing all the train parameters(x.y).

Predicting X for the testing data.

The r2 score denotes accuracy of the model.

Accuracy is 79%

This accuracy is good but less hence to improve the accuracy using the Polynomail regression since it has some polynomail features.

Using 'Polynomial Regression' for increasing accuracy

Conversion to second dregree polynomial

Using transform function to change X variable to second degree polynomial.

After using train test spilt again using the PX variable.

Accuracy is 87%.This is much better than Linear Regression.


Performing Cross Validation.This is basically used to check if my model is not overfitted.

Import cross_val_score.Pass reg,X,Y and number of samples to divide the data into and I want it to be 4.

Mean is 81%

Now converting polynomial to third degree polynomial for better accuracy by just changing degree=3.

Accuracy remains same 87% but mean changes to 82%

CONCLUSION:

Accuracy using Linear Regression is : 79%

Accuracy using Polynomial Regression is : 87%

Hence Polynomial is preferred than Linear Regression Model.

From the scatter plot,The non-smokers have charges ranging from 0-38k(approx) and smokers have spending of about 12k-above 60k.














