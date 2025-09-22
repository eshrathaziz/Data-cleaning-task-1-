import pandas as pd
# Replace 'your_dataset_name.csv' with the actual file name
df = pd.read_csv(r'C:\Users\eshra\Desktop\Datasets\netflix_movies (1).csv')
                # Display the first 5 rows of the DataFrame
print(df.head())

# Get information about the DataFrame, including data types and non-null values
print(df.info())
# Check for missing values in each column
print(df.isnull().sum())

# First, let's see what columns are available in the DataFrame
print("Available columns:", df.columns.tolist())

# Example: Fill missing values in a numerical column with the mean
# Replace 'your_actual_column_name' with a column that exists in your DataFrame
# For example, if you have a column named 'age':
# df['age'].fillna(df['age'].mean(), inplace=True)

# Or comment out the line if you're not sure which column to use yet
# df['your_actual_column_name'].fillna(df['your_actual_column_name'].mean(), inplace=True)

# Example: Drop rows with any missing values
df.dropna(inplace=True)
# Netflix Movies Data Cleaning Task
import pandas as pd

# 1. Load the dataset
df = pd.read_csv(r"C:\Users\eshra\Desktop\Datasets\netflix_movies (1).csv")

# 2. Quick look at data
print("Shape:", df.shape)
print(df.info())
print(df.head())

# 3. Handle missing values
print("Missing values before cleaning:\n", df.isnull().sum())

# Option 1: Drop rows with too many nulls
df = df.dropna(thresh=3)  # keep rows with at least 3 non-null values

# Option 2: Fill missing values (example: fill with 'Unknown' or median for numeric)
df = df.fillna({
    "director": "Unknown",
    "cast": "Unknown",
    "country": "Unknown"
})

# 4. Remove duplicates
print("Duplicates before:", df.duplicated().sum())
df = df.drop_duplicates()
print("Duplicates after:", df.duplicated().sum())

# 5. Standardize text values
# Example: convert all country names to lowercase
df['country'] = df['country'].str.strip().str.title()

# 6. Convert date format
if "date_added" in df.columns:
    df['date_added'] = pd.to_datetime(df['date_added'], errors='coerce')
    df['date_added'] = df['date_added'].dt.strftime("%d-%m-%Y")

# 7. Rename columns to be clean and uniform
df.columns = df.columns.str.strip().str.lower().str.replace(" ", "_")

# 8. Fix data types
if "release_year" in df.columns:
    df['release_year'] = df['release_year'].astype("Int64")

# 9. Save cleaned dataset
df.to_csv("netflix_movies_cleaned.csv", index=False)

# 10. Summary Report
print("\n Cleaning Completed!")
print("Final Shape:", df.shape)
print("Null values after cleaning:\n", df.isnull().sum())

df = df.dropna(thresh=3)  # drop rows with too many nulls

# Fill specific columns
df = df.fillna({
    "director": "Unknown",
    "cast": "Unknown",
    "country": "Unknown",
    "rating": "Not Rated",
    "duration": "Unknown"
})

# Convert date format (fix nulls too)
if "date_added" in df.columns:
    df['date_added'] = pd.to_datetime(df['date_added'], errors='coerce')
    df['date_added'] = df['date_added'].dt.strftime("%d-%m-%Y")
    df['date_added'] = df['date_added'].fillna("Unknown")

# 3. Remove duplicates
df = df.drop_duplicates()

# 4. Standardize text values
df['country'] = df['country'].str.strip().str.title()

# 5. Rename columns
df.columns = df.columns.str.strip().str.lower().str.replace(" ", "_")

# 6. Fix data types
if "release_year" in df.columns:
    df['release_year'] = df['release_year'].astype("Int64")

# 7. Save cleaned dataset
df.to_csv("netflix_movies_cleaned.csv", index=False)

# 8. Summary
print("\n Final Cleaning Completed!")
print("Final Shape:", df.shape)
print("Null values after cleaning:\n", df.isnull().sum())
# Save cleaned dataset locally
df.to_csv("netflix_movies_cleaned.csv", index=False)

print(" Cleaned dataset saved as netflix_movies_cleaned.csv")


