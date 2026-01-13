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