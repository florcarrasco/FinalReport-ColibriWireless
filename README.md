# Physical Activity Monitoring with Colibri Wireless Unit

## Introduction and Project Background

The rise of fitness trackers marks a significant evolution in the landscape of personal health technology. Originally developed as basic heart monitors in the 1980s, these devices have undergone substantial transformation, becoming intricate systems that offer rich insights into various health metrics and physical activities. Modern fitness trackers not only measure heart rates but also track sleep patterns, count steps, monitor various forms of physical activity, and even provide GPS tracking for outdoor activities. This development has been driven by advances in sensor technology, data analytics, and consumer demand for wearable health monitoring devices.

This project centres on the Colibri Wireless unit, an advanced inertial measurement unit (IMU). More details about the unit can be found [here](Additional_Information/TrivisioColibriwirelessBrochure.pdf). The Colibri unit stands out due to its unique configuration of incorporating multiple sensors that capture three-dimensional acceleration, angular rates, and magnetic fields, providing high-resolution data. This project aims to leverage these capabilities to offer more precise and detailed monitoring of physical activities than its competitors.
## Project Goals

The primary goal of this project is to enhance the utility of the Colibri Wireless unit in health and activity monitoring applications, with a specific focus on integrating BMI (Body Mass Index) calculations to improve health risk assessment and activity monitoring accuracy. By analysing detailed data captured from various daily and sports activities under controlled conditions, coupled with BMI and related health metrics, we aim to:

- Investigate how BMI interacts with various health-related metrics to understand its impact on overall health and fitness device effectiveness.
-  Enhance device performance and user experience by Formulating actionable recommendations based on the study’s findings to optimise the fitness tracking device. These enhancements could involve adjustments to the device's sensors, algorithms, or user interface.
-  Address study design limitations.
-  Explore more sophisticated modelling techniques by incorporating additional variables that were not included in the initial study.

## Research Significance

This research is significant as it contributes to the field of personal health monitoring, where accurate and real-time data analysis is crucial for preventive healthcare. By improving the performance and capabilities of the Colibri Wireless unit, the project aligns with the broader goal of advancing health technology to better meet the needs of both individuals and healthcare providers. Moreover, the findings from this study could inform future developments in wearable technology, helping to shape innovations that enhance user well-being and health management.
## Data Collection and Analysis Setup

Data was collected from nine subjects equipped with three Colibri wireless IMUs and a BM-CS5SR heart-rate monitor. The subjects consisted of one female and eight males, aged 27.22 ± 3.31 years.
## Subject Details

Comprehensive demographic and physiological data were collected for each subject, including specific measurements like age, gender, height, weight, resting heart rate, and maximum heart rate. Detailed individual subject information is available in [Subject Information](Additional_Information/subjectInformation.pdf).
## Data Collection Hardware

* IMUs: Three Colibri wireless inertial measurement units were used, placed over the wrist of the dominant arm, on the chest, and on the dominant side's ankle. These units sampled data at 100Hz, providing detailed measurements including 3D-acceleration, gyroscope, and magnetometer readings across multiple axes.
* Heart Rate Monitor: The heart rate was recorded using a BM-CS5SR monitor.

## Activities Performed


The subjects performed a structured set of 12 basic activities outlined in the [Data Collection Protocol](Additional_Information/DataCollectionProtocol.pdf), with additional optional activities suggested from a list containing a wide range of everyday, household, and sports activities. The basic activities included:

  1. Lying
  2. Sitting
  3. Standing
  4. Walking
  5. Running
  6. Cycling
  7. Nordic walking
  8. Watching television
  9. Computer work
 10. Car driving
 11. Ascending stairs
 12. Descending stairs

Each activity was performed according to specific guidelines to ensure consistent data collection across subjects. A complete description of these activities, including their setup and execution, can be found in [Description of Activities](Additional_Information/DescriptionOfActivities.pdf).

## Data Collection Protocol

Each subject followed a detailed protocol for the data collection, performing the specified activities in a controlled environment. The protocol ensured that data was collected systematically for each activity, capturing physiological responses accurately. The protocol also suggested additional optional activities, enhancing the dataset with diverse physical exertions.
## Summary of Collected Data

Over 10 hours of data were collected, with nearly 8 hours labelled according to the 18 different activities performed. Due to the use of wireless sensors, some data points were missing, attributed to data dropping or hardware issues like connection losses or system crashes. Detailed summaries of the data collected for each activity by each subject are provided in [Performed Activities Summary](Additional_Information/PerformedActivitiesSummary.pdf).
## Libraries and Modules Utilised

For comprehensive data analysis and modelling, a variety of Python libraries and modules were employed, as detailed below:

 *    **Pandas:** Used for data manipulation tasks such as merging data frames and handling missing values.
 *  **NumPy:** Utilised for heavy numerical computations.
 *  **Matplotlib and Seaborn:** Employed for visual data exploration and creating insightful plots.
  *   **SciKit-Learn:** Used for several machine learning tasks including Principal Component Analysis (PCA), linear regression models, and feature selection.
   * **StatsModels:** Applied for more detailed statistical modelling and hypothesis testing. This includes using the Empirical Cumulative Distribution Function (ECDF) for non-parametric analysis.
   * **StandardScaler:** From SciKit-Learn, used for normalising features before applying machine learning models.
   * **SequentialFeatureSelector:** Also from SciKit-Learn, employed to identify the best subset of features for predictive modelling.
   * **Train Test Split, Mean Squared Error, and R2 Score:** Utilised for model evaluation, specifically to assess the performance of regression models.
   * **Linear Regression:** Implemented for predictive modelling, essential for understanding relationships between variables.


## Data Wrangling and Cleaning Process
### Data Consolidation
* Source Data: Physiological and activity-related data collected from multiple subjects during the experiment were consolidated into a unified dataset.
* Method: The original raw data from sensor outputs was pre-processed to ensure consistency in variable naming, time alignment, and column formatting. Python's pandas library was employed to integrate data from multiple input files into a single, coherent DataFrame.
### Data Cleaning
* Handling Missing Values: Missing data points were addressed using imputation techniques such as forward and backward filling, ensuring continuity in time-series data while preserving trends and variability.
* Data Validity Checks: Erroneous or unreliable sensor readings, particularly from accelerometers and gyroscopes during high-motion activities, were flagged and excluded from analysis.
* Activity Filtering: Data segments corresponding to irrelevant or unclassified activities (e.g., activityID 0) were removed to focus on valid and interpretable activity categories.
* Normalization: Key variables were normalized to facilitate downstream comparisons and improve model stability during analysis.
### Data Integration and Enrichment
* New Metrics Calculation: Variables such as energy expenditure and physiological efficiency were derived using established formulas, enriching the dataset for deeper analysis.
* Temporal Features: Duration of each activity was computed, and transitions between activities were analyzed to identify patterns of activity switching.
### Data Structure Optimization
* Dimensionality Reduction: Principal Component Analysis (PCA) was applied to reduce the feature set while retaining 85% of the variance. This optimization enhanced computational efficiency and interpretability.
* Feature Engineering: New composite variables representing combined physiological effects were generated to capture complex interactions not directly measurable.
## Predictive Hypothesis and Analytical Methodology


The [report](FinalReport-ColibriWireless.pdf) hypothesizes that physiological metrics captured by the Colibri Wireless device can predict both the type and intensity of physical activity. The analysis involves the following key stages:

1. **Activity Classification**  Utilizing supervised machine learning algorithms such as Random Forest and Support Vector Machines to categorize physical activities based on physiological inputs.
2. **Energy Prediction Models:** Regression techniques were employed to estimate caloric expenditure and correlate it with specific physiological markers such as heart rate variability and accelerometer readings.
3. **Cluster Analysis:** Unsupervised clustering methods (e.g., K-means) identified natural groupings within the data, providing insights into participant behavioral patterns across activity types.
## Analytical Results
1. **Activity Engagement:** Significant variability was noted in activity duration across participants. Subjects exhibited differing levels of adherence and engagement with prescribed activity regimes.
2. **Energy Expenditure Patterns:** Regression models revealed strong correlations between accelerometer-derived movement intensities and estimated caloric outputs.
BMI Implications: The study highlighted a weak association between BMI categories and average energy expenditure, suggesting the need for refined stratification in future analyses.
3. **PCA Insights:** PCA reduced the dataset to five principal components, explaining 85% of the variance. Dominant components were heavily influenced by variables like energy expenditure, heart rate, and activity duration.
## Future Work
* **Participant Diversity:** Expand the participant pool to include a balanced gender representation and broader BMI categories to enhance the generalizability of findings.
* **Intense Activities:** Incorporate a wider spectrum of physical activity intensities, including resistance training and endurance exercises, to validate device accuracy under diverse conditions.
* **Sensor Enhancements:** Integrate additional sensors to measure variables such as oxygen saturation and sweat rate for a more comprehensive physiological assessment.
* **Algorithm Improvements:** Develop real-time predictive algorithms capable of adjusting for individual variability in physiological responses.
* **User-Centric Features:** Introduce functionalities in the device that allow users to input personalized parameters like fitness goals, enhancing the device’s relevance for different user groups.
