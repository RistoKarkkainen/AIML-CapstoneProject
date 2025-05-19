### Capstone Project: Air Pollution Prediction Based on Weather Factors

**Risto Kaerkkaeinen**

#### Executive Summary
This project analyzes air pollution levels across different regions, focusing on how weather conditions and environmental factors influence air quality. Using machine learning and statistical methods, we explore the relationships between variables such as temperature, humidity, and proximity to industrial areas with pollution severity. We build predictive models to classify air quality levels and uncover meaningful patterns. Insights from this study support public health planning and pollution control strategies by enabling data-driven environmental decisions.

#### Rationale
Understanding how weather and regional factors impact air quality is critical for effective environmental policy, public health, and urban planning. Identifying the conditions that lead to hazardous air quality allows cities to act early—such as issuing warnings or adjusting traffic policies—to reduce health risks and improve overall air quality management.

#### Research Question
How do air pollution levels vary across different locations, and how do weather conditions influence these variations?

#### Data Sources
We use the [Air Quality and Pollution Assessment dataset](https://www.kaggle.com/datasets/mujtabamatin/air-quality-and-pollution-assessment) from Kaggle, which contains:
- Pollutant measurements: PM2.5, PM10, NO2, SO2, CO  
- Weather indicators: Temperature (°C), Humidity (%)  
- Contextual data: Proximity to industrial areas (km), Population density (people/km²)  
- Target variable: Air Quality Levels (Good, Moderate, Poor, Hazardous)

#### Methodology
- **Data Cleaning and Preprocessing**: Handled missing values and standardized formats
- **Exploratory Data Analysis and Correlation Study**
- **Class Imbalance Handling**: Applied SMOTE to improve learning on minority classes
- **Clustering**: K-means and DBSCAN to identify patterns in pollution levels across regions
- **Dimensionality Reduction**: PCA to simplify feature space for clustering
- **Classification Models**:
  - Support Vector Machines (SVC)
  - Random Forest (with GridSearch hyperparameter tuning)
  - TabPFN (pretrained transformer for tabular data)
- **Evaluation Metrics**: Accuracy, Precision, Recall, and F1-score
- **Visualization**: Heatmaps, time series plots, and geospatial distribution

#### Results

- **SVC Accuracy**: 76%  
  - Good (0): Precision 0.88, Recall 0.97, F1-score 0.93  
  - Moderate (1): Precision 0.71, Recall 0.73, F1-score 0.72  
  - Poor (2): Precision 0.53, Recall 0.60, F1-score 0.56  
  - Hazardous (3): Precision 0.94, Recall 0.30, F1-score 0.45  

- **Random Forest** (after hyperparameter tuning):
  - Best parameters: `n_estimators=200`, `max_depth=None`, `min_samples_split=2`
  - Accuracy: 1.00  
  - F1-scores: All categories 0.99–1.00, indicating very strong performance but potential overfitting

- **TabPFN** (pretrained transformer):
  - Accuracy: 1.00  
  - F1-scores: 0.99–1.00 across all classes, including perfect scores for the Hazardous category  
  - Excellent performance on all classes, likely benefiting from balanced data via SMOTE

#### Business Recommendations

**Deploy Predictive Models for Air Quality Forecasting**
The Random Forest and TabPFN models achieved near-perfect accuracy (1.0), making them highly suitable for forecasting air quality levels in real time. City planners and environmental agencies can integrate these models into early warning systems to proactively alert the public during high-risk conditions.

**Improve Monitoring in High-Risk Areas**
The analysis shows that areas with high population density and close proximity to industrial zones are more likely to experience poor air quality. Resources such as mobile air monitoring units and emission controls should be focused on these locations.

**Use Weather Data to Trigger Preventive Actions**
Weather conditions like temperature and humidity were found to strongly influence pollution levels. Municipal authorities can use this relationship to issue public health advisories or implement temporary traffic restrictions on days with high pollution risk.

**Enhance Public Health Campaigns on High Pollution Days**
Predicting “Hazardous” air quality days is now more reliable, thanks to SMOTE and model tuning. Health departments can schedule targeted campaigns encouraging mask usage, reduced outdoor activity, or use of public transit during predicted spikes.

**Support Data-Driven Urban Planning**
The results can inform zoning and infrastructure decisions. For example, new industrial developments should be planned away from dense residential areas, using model insights to assess potential environmental impact in advance.

**Continue Model Evaluation to Ensure Robustness**
Despite high accuracy, especially from TabPFN, future use should include ongoing evaluation with updated datasets to ensure performance remains reliable and not overfitted to the current data sample.

#### Outline of project

- [Link to Github](https://github.com/RistoKarkkainen/AIML-CapstoneProject)
- [Link to Notebook](https://github.com/RistoKarkkainen/AIML-CapstoneProject/blob/main/capstone.ipynb)

##### Contact and Further Information

Risto Kaerkkaeinen
ristokar@gmail.com