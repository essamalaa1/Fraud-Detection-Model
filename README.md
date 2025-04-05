# Fraud Detection and Analysis Project
This project is designed to perform a comprehensive analysis on a fraud detection dataset. It includes exploratory data analysis (EDA), data cleaning and preprocessing, visualization, and predictive modeling. In addition, an interactive dashboard is built using Dash to facilitate data exploration.

## Project Overview
### The primary objectives of this project are to:

#### Understand the distribution and relationships within the dataset.

#### Clean and preprocess the data to prepare it for modeling.

#### Build baseline and resampling-based logistic regression models.

#### Evaluate model performance using metrics such as precision, recall, F1-score, and log loss.

#### Create an interactive dashboard to visualize key insights and trends.

## 1. Data Exploration and Visualization
### Data Loading and Initial Inspection
#### The dataset is loaded using pandas.read_csv and basic information (data types, null counts, etc.) is reviewed.

#### An initial distribution of the target variable (Class) is visualized using a pie chart to highlight the imbalance between fraudulent and non-fraudulent transactions.

### Detailed Feature Exploration
#### Histograms and box plots are generated for each feature (except the target) to understand their distributions and detect any potential outliers.

#### Variance analysis is performed to identify the most variable features, which are then visualized.

#### A correlation matrix is created using a heatmap to investigate linear relationships between numeric features. Scatter plots are also used to visualize specific relationships (e.g., between V2 and Amount).

### Dashboard Visualization
#### An interactive dashboard is built using Dash and Plotly Express. The dashboard allows users to:

##### Select a feature from a dropdown list.

##### View a histogram of the selected feature, colored by transaction class.

##### View a scatter plot showing the relationship between Time and Amount.

## 2. Data Cleaning and Preprocessing
### Handling Missing Values and Outliers
#### The code checks for missing values and assesses their overall impact.

#### Columns with low ratios of missing data are retained, while rows with missing values are handled appropriately.

#### For the feature V13, missing values are imputed with the column mean.

### Feature Scaling
#### Numerical features (excluding the target) are standardized using StandardScaler to normalize the data. This step is essential due to varying distributions across features.

### Feature Selection
#### Irrelevant features such as Time and V2 are dropped based on initial EDA insights.

#### The data is filtered to include rows without missing values for the non-fraud class and all rows for the fraud class.

## 3. Predictive Modeling
### Baseline Logistic Regression Model
#### A baseline logistic regression model is built on the cleaned dataset.

#### The dataset is split into training and testing sets using train_test_split.

#### Model performance is evaluated with confusion matrix, precision, recall, F1-score, and log loss. The baseline model achieves an F1-score of approximately 72.3%, which serves as the base accuracy.

### Handling Class Imbalance
#### vTwo resampling techniques are explored to improve the model's performance:

##### Undersampling:

###### The non-fraud class is undersampled to balance the dataset.

###### The undersampled model is evaluated and compared with the baseline, though it shows a significant difference between training and test loss, suggesting potential overfitting.

##### Oversampling:

###### The oversampling method uses RandomOverSampler to increase the representation of the minority (fraud) class.

###### The oversampled logistic regression model shows improved F1 scores and a minimal gap between training and test log loss, indicating better generalization.

## 4. Model Evaluation
### For each modeling approach, performance is measured using:

#### Confusion Matrix: To visualize true versus predicted classes.

#### Precision, Recall, and F1-score: To evaluate classification performance.

#### Log Loss: To assess the quality of probability estimates.

### These metrics help in comparing the baseline model with the models built using undersampling and oversampling strategies.

## 5. Interactive Dashboard
### The dashboard is developed using Dash, Plotly Express, and HTML components.

### It provides an interactive interface where users can select a feature to view detailed histograms and scatter plots.

### The dashboard facilitates exploratory data analysis by allowing users to dynamically explore data distributions and relationships.
