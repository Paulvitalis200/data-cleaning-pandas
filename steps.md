# Steps
1. Create a copy of the original dataframe
2. Choose method of cleaning data
   i. Drop erroneous data
   ii. Infer the data
    
    In each case, we introduce a certain amount of error in the data

# Cleaning string Data
1. Drop missing values in a main column. In our case, we will drop the missing values in the Client column (drop_na)
2. Drop potential duplicate records in all columns except the transaction ID column which is not unique . (drop_duplicates)
3. Fix the formating issues such as weird characters in words. In this case the characters in the client column e.g *,-, we use regex for this. First get all the
non alphanumeric characters. cleaned_df["Client"].str.replace("[a-zA-Z0-9 ]", "", regex=True).unique(). Replace the current column with a new version
where we strip out any non alpha numeric characters from the string. If any is remaining within the string, just replace it using .replace()
4. Standardize the values of the columns to either uppercase or lowercase

Cleaning numeric data
1. Imput or infer what the missing value should be. Common method, replace the missing values with some
form of statistic eg mean or median. To get even more exciting, we can use a ML algorithm.
We can visualize the distribution of our amountusd data. We can use matplotlib for this.
Also we can measure the difference between the mean and median and the mean and the mean value which
we can calculate to see which one gives us less of an error.
2. Infer the values on the client Tier. We can infer the Mode. e.g if Gold occurs most frequently,
we will use that as the mode