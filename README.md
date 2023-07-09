## Predicting Walmart Store Sales Data

This notebook, is an analysis and prediction task related to Walmart store sales. The goal is to develop a predictive model that can forecast a store's sales based on various factors such as holidays, temperature, fuel price, CPI (consumer price index), unemployment, and past store sales.

### Dataset
The dataset used in this analysis is the "Walmart Stores sales Dataset" obtained from Kaggle. The dataset contains historical sales data for different Walmart stores, with each row representing the weekly sales data for a specific store. The columns in the dataset are as follows:

- `Store`: The store number.
- `Date`: The week of sales in the format DD-MM-YYYY.
- `Weekly_Sales`: Sales for the given store in the specified week.
- `Holiday_Flag`: A binary flag indicating whether the week is a special holiday week (1 – Holiday week, 0 – Non-holiday week).
- `Temperature`: The temperature on the day of sale.
- `Fuel_Price`: The cost of fuel in the region.
- `CPI`: The prevailing consumer price index.
- `Unemployment`: The prevailing unemployment rate.

The original dataset can be accessed at [Walmart Dataset - Retail](https://www.kaggle.com/datasets/rutuspatel/walmart-dataset-retail).

### Approach
The analysis in this notebook follows these key steps:

1. Data Loading and Preprocessing:
   - The dataset is loaded using the pandas library.
   - The 'Date' column is converted to the datetime format to ensure correct handling of dates.
   - The data is sorted by the 'Date' column to establish a chronological order.
   - The index is reset to maintain a consistent indexing structure.
   - Missing values are checked for, and fortunately, no missing values are found.

2. Exploratory Data Analysis (EDA):
   - Visualizations are created to better understand the relationships between different variables and their impact on weekly sales.
   - Plots generated include:
     - Weekly sales over time (line plot)
     - Weekly sales grouped by holiday or non-holiday weeks (box plot)
     - Weekly sales in relation to temperature, fuel price, CPI, and unemployment (scatter plots)

3. Model Development and Evaluation:
   - A linear regression model is built to predict store sales based on the provided variables.
   - The model includes features such as Store, Holiday_Flag, Temperature, Fuel_Price, CPI, Unemployment, and lagged Weekly_Sales (previous week's sales).
   - The data is split into training and testing sets.
   - The model is trained using the training set and evaluated using the testing set.
   - The evaluation metric used is the root mean squared error (RMSE), which measures the average prediction error of the model.

### Results
The linear regression model achieves an RMSE value of approximately $532,957.85 on the test set. This indicates the average prediction error of the model in terms of weekly sales. Given the magnitude of weekly sales, this error might be considered high.

### Future Improvements
To enhance the model's performance, the following steps can be considered:
- Incorporating more sophisticated techniques like time series analysis to capture seasonality and trends in sales data.
- Fine-tuning the model's parameters to improve its predictive capabilities.
- Exploring datasets with individual product data to analyze the predictive potential of variables such as temperature and CPI for specific product categories.
