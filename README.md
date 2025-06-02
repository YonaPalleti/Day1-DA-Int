# Day1-DA-Int
Cleaning Steps Performed
1. Corrected File Reading

Specified the correct delimiter (\t) while reading the dataset using:

pd.read_csv('Customer_Personality_Analysis.csv', sep='\t')
3. Column Name Normalization

Removed leading/trailing spaces
Converted column names to lowercase
Replaced spaces with underscores

df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')
4. Missing Values
Identified columns with missing values using:

df.isnull().sum()

Dropped rows containing any missing values:

df = df.dropna()

5. Duplicate Records
Checked and removed duplicate rows:

df = df.drop_duplicates()

7. Date Formatting
Converted the dt_customer column to proper datetime format:

df['dt_customer'] = pd.to_datetime(df['dt_customer'], dayfirst=True)

9. Text Standardization
Cleaned and standardized text columns like education and marital_status:

df['education'] = df['education'].str.strip().str.title()

df['marital_status'] = df['marital_status'].str.strip().str.upper()

11. Data Type Fixes
    
Ensured numerical columns are of correct type:

df['year_birth'] = df['year_birth'].astype(int)

df['income'] = df['income'].astype(float)
13. Saved Cleaned Dataset

Exported the final cleaned dataset:

df.to_csv('cleaned_customer_personality.csv', index=False)

Cleaned Dataset: cleaned_customer_personality.csv

Format: Comma-separated values

Ready for analysis and modeling

