### Description

This Python script processes a dataset of UPI transaction details, performing data cleaning, feature engineering, and encoding to prepare the data for machine learning models.


### Key Features

1. **Data Loading and Preprocessing**:
   - Reads transaction data from an Excel file.
   - Strips whitespace from string columns and ensures proper data types.

2. **Feature Engineering**:
   - **Transaction ID Splitting**:
     - Separates the alphanumeric `TransactionID` column into two components: 
       - `Transaction_Obj`: Alphabetical part.
       - `Transaction_num`: Numerical part.
   - **Transaction Date Splitting**:
     - Extracts year, month, and day from the `TransactionDate` column.
   - **Bank Name Splitting**:
     - Separates `BankNameReceived` into two components based on space.

3. **Dropping Unnecessary Columns**:
   - Removes intermediary and redundant columns post-processing to streamline the dataset.

4. **Categorical Encoding**:
   - Applies **One-Hot Encoding (OHE)** to categorical features such as `Gender`, `Status`, `TransactionType`, `PaymentMethod`, and `PaymentMode`. The encoded columns are concatenated into the final DataFrame.
   - Uses **Label Encoding** for features like `BankNameSent`, `City`, `DeviceType`, `MerchantName`, `Purpose`, and `Currency`.

5. **Final Transformation**:
   - Combines the One-Hot Encoded DataFrame with the cleaned and encoded DataFrame to produce the final dataset (`Final_df`) ready for machine learning applications.

---

### Use Case

This script is ideal for:
- **Preparing transaction data for predictive modeling** in finance-related applications such as fraud detection, user behavior analysis, or payment pattern insights.
- **Data preprocessing and feature engineering** for machine learning tasks.

### Notes
- The script transforms raw categorical data into numerical formats, ensuring compatibility with machine learning models.
- It ensures no redundant information remains, resulting in an optimized dataset for training or analysis.

