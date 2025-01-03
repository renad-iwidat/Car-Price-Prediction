
---

# Car Price Prediction

A comprehensive machine learning project for predicting car prices based on a variety of features, such as car specifications, usage history, and more. This project involves extracting, cleaning, preprocessing, and analyzing data to build predictive models.

## Table of Contents
1. [Introduction](#introduction)
2. [Features](#features)
3. [Project Structure](#project-structure)
4. [Data Processing](#data-processing)
5. [Modeling](#modeling)
6. [Results](#results)
7. [Requirements](#requirements)
8. [Usage](#usage)
9. [License](#license)

---

## Introduction

The goal of this project is to predict the price of a car based on its features using machine learning models. The project covers:
- Extracting data from HTML files.
- Cleaning and preprocessing data to handle missing and inconsistent values.
- Encoding categorical variables and handling outliers.
- Building and evaluating machine learning models.

## Features

The project processes and utilizes the following features for prediction:

- **Car Name**: Brand and model.
- **Year**: Manufacturing year.
- **Sunroof**: Binary indicator for the presence of a sunroof.
- **Fuel Type**: Type of fuel used by the car.
- **Original Use**: The car’s initial purpose or usage.
- **License Status**: The license type or status.
- **Gear Type**: Type of gearbox.
- **Glass**: Type of glass used in the car.
- **Engine**: Engine power.
- **Meter Reading**: The car's mileage or distance traveled.
- **Wheel Drive**: Type of wheel-drive system.
- **Payment Options**: Available payment methods.
- **Purpose**: Whether the car is for sale or other purposes.
- **Previous Owners**: The number of previous owners.
- **Passengers**: Passenger capacity.
- **Price**: The target variable for prediction.

---

## Project Structure

```
Car-Price-Prediction/
├── data/                  # Directory containing raw HTML files for feature extraction
├── extract_features.ipynb # Notebook for extracting features from HTML files
├── handling_data.ipynb    # Notebook for cleaning, preprocessing, and preparing data
├── models/                # Directory for trained models (optional)
├── README.md              # Project documentation
├── cars_dataset.csv       # Extracted and cleaned dataset
├── handling_data.csv      # Preprocessed dataset for modeling
```

---

## Data Processing

### 1. Feature Extraction
- Data is extracted from HTML files using BeautifulSoup.
- Key features are mapped from Arabic feature names to English attributes.
- Binary and numeric features are derived (e.g., sunroof presence, engine power).

### 2. Data Cleaning
- Missing values are handled using imputation or removal.
- Features like `prev_owners`, `meter`, and `passengers` are transformed to numeric using mapping and regular expressions.
- Irrelevant features with high missing percentages are dropped (e.g., `wheel_drive`).

### 3. Encoding and Normalization
- Categorical features are encoded using one-hot encoding.
- Numeric features are normalized for better model performance.

### 4. Outlier Detection
- Outliers are identified using the Interquartile Range (IQR) method and Z-scores.
- Visualizations highlight outliers in key features like `engine`, `meter`, and `year`.

---

## Modeling

Two models were trained and evaluated for predicting car prices:
1. **K-Nearest Neighbors (KNN)**:
   - Hyperparameters: `n_neighbors=11`, `weights='distance'`.
   - RMSE and MAE were used for evaluation.
2. **Decision Tree Regressor**:
   - Hyperparameters: `max_depth=5`.
   - RMSE and MAE were used for evaluation.

### Data Splitting
The dataset was split into training (75%) and testing (25%) sets.

---

## Results

### K-Nearest Neighbors (KNN)
- **RMSE**: Root Mean Squared Error of predictions.
- **MAE**: Mean Absolute Error of predictions.

### Decision Tree Regressor
- **RMSE**: Root Mean Squared Error of predictions.
- **MAE**: Mean Absolute Error of predictions.

**Comparison**:
- The model with the lower RMSE and MAE is more effective in predicting car prices.

---

## Requirements

- Python 3.8 or higher
- Required Python libraries:
  - pandas
  - numpy
  - scikit-learn
  - matplotlib
  - BeautifulSoup4

To install all dependencies:
```bash
pip install -r requirements.txt
```

---

## Usage

### Step 1: Clone the Repository
```bash
git clone https://github.com/username/Car-Price-Prediction.git
cd Car-Price-Prediction
```

### Step 2: Run Feature Extraction
Use `extract_features.ipynb` to extract features from raw HTML files:
1. Place your HTML files in the `data/` directory.
2. Run the notebook to generate `cars_dataset.csv`.

### Step 3: Data Cleaning and Preprocessing
Use `handling_data.ipynb` to clean and preprocess the extracted data:
1. Handle missing values, outliers, and normalize features.
2. Save the preprocessed data as `handling_data.csv`.

### Step 4: Train Models
Split the data into training and testing sets, and train the models:
- Train the KNN and Decision Tree models.
- Evaluate their performance using metrics like RMSE and MAE.

### Step 5: Make Predictions
Use the trained models to predict car prices for new data.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Future Enhancements

- Incorporate additional features for improved predictions.
- Experiment with advanced machine learning models like Random Forest, Gradient Boosting, or Neural Networks.
- Build a user-friendly web interface for real-time car price predictions.

---
