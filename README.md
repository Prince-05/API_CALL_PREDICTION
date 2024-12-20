# API Call Prediction

## Overview
This project focuses on building a time series prediction system for API call data. The goal is to identify the most frequently called APIs, build predictive models for them, and deploy these models to forecast future call frequencies. The workflow is divided into four major steps.

## Steps

### Step 1: Find Top 3 Most Called APIs
- Identify the top 3 APIs with the highest frequency of calls.
- Example: A8, A1, A7, etc.
- **Script**: `Top_3_apis.py`
  - Outputs the top 3 APIs based on call frequency.

### Step 2: Filter Data for Top APIs
- Extract data for the top 3 APIs and store each in a separate CSV file.
- Example: `A8.csv`, `A1.csv`, `A7.csv`, etc.
- **Script**: `create_top_3.py`
  - Generates individual CSV files for the top 3 APIs in the project directory.

### Step 3: Build Models for Each API
- Train multiple models (e.g., ARIMA, Exponential Smoothing, etc.) for each API dataset.
- Evaluate models and select the best one based on performance metrics (e.g., MAE, RMSE).
- Save the best model for each API as a pickle (`.pkl`) file.
- Example:
  - `A8_best_model.pkl`
  - `A1_best_model.pkl`
  - `A7_best_model.pkl`
- **Script**: `model_building.py`
  - Trains and evaluates models, saving the best one for each API.

### Step 4: Deploy Models for Predictions
- Load the best model for the specified API.
- Ask the user for:
  - The API code.
  - The number of forecast steps.
- Generate and display predictions based on user input.
- **Script**: `app.py`
  - Provides a user interface for making predictions using the pre-trained models.

## File Descriptions
1. **`Top_3_apis.py`**: Identifies the top 3 most called APIs from the dataset.
2. **`create_top_3.py`**: Filters the data for the top 3 APIs and stores it in separate CSV files.
3. **`model_building.py`**: Trains multiple models for each API and saves the best one as a `.pkl` file.
4. **`app.py`**: Deploys the models and allows users to make predictions for the selected API.

## How to Run the Project
1. **Install Required Libraries**:

2. **Run the Steps in Sequence**:
   - Step 1: Identify top 3 APIs
     ```bash
     python Top_3_apis.py
     ```
   - Step 2: Create CSV files for top 3 APIs
     ```bash
     python create_top_3.py
     ```
   - Step 3: Build models for the top 3 APIs
     ```bash
     python model_building.py
     ```
   - Step 4: Make predictions using the best models
     ```bash
     python app.py
     ```

## Example Workflow
- Input dataset is analyzed to find top 3 APIs (e.g., A8, A1, A7).
- Data for these APIs is filtered into separate files (`A8.csv`, `A1.csv`, `A7.csv`).
- Predictive models are trained for each API, and the best-performing models are saved as `.pkl` files.
- The user interacts with `app.py` to make predictions, specifying the API and number of forecast steps.


