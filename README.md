# HW1 GitHub username is bmthorpe

import pandas as pd

# Read the CSV file from Google Drive
file_path = 'https://drive.google.com/file/d/1YT9DwTMAnvVo9_3hKlEJMpdRHxQTm7JO/view?usp=drive_link'
medals = pd.read_csv(file_path)

#  How many rows, how many columns?
num_rows, num_columns = medals.shape
print(f"(a) The dataset has {num_rows} rows and {num_columns} columns.")

# Use the appropriate function 
print("\n(b) Data types for all columns:")
print(medals.dtypes)

# Find how many unique cities matches were held at
unique_cities = len(medals['Location'].unique())
print(f"\n(c) Number of unique cities where matches were held: {unique_cities}")

# Find how many medals the USA team won in total
usa_medals = medals[medals['Nationality'] == 'USA'].shape[0]
print(f"\n(d) Total medals won by the USA team: {usa_medals}")

# Find the total number of medals for each Nationality
medals_by_nationality = medals.groupby(by='Nationality').size()
print("\n(e) Total number of medals for each Nationality:")
print(medals_by_nationality)
