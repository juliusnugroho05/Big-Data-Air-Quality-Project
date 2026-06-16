# Big Data Architecture for Real-Time Air Quality Monitoring in Brooklyn, New York

**Course:** COM579001P6 – Big Data Processing

**University:** BINUS University Alam Sutera

## Project Summary
Urban air pollution is a major public health concern. This project implements a **Big Data Architecture** to ingest, store, process, and analyze IoT sensor data in real-time for air quality monitoring in Brooklyn, New York. The primary focus of this analysis is tracking **PM 2.5** levels to detect pollution spikes, identify high-risk areas, and support decision-making.

## Dataset
* **Source:** [Kaggle - Air Quality Data in Brooklyn, NY (OpenAQ 2025)](https://www.kaggle.com/datasets/aidenl25/air-quality-data-in-brooklyn-ny-openaq-2025)
* **Description:** Contains hourly PM 2.5 measurements, timestamps, geographic coordinates, and station metadata from various monitoring sensors.

## Big Data Architecture
The proposed architecture uses a layered approach designed for deployment on a **Public Cloud** (Google Cloud Platform):
* **Ingestion Layer:** Real-Time Streaming Pipeline
* **Storage Layer:** Apache Hadoop HDFS (for historical data) & Apache HBase (for real-time read/write)
* **Analytics Engine:** Apache Spark & PySpark (Batch & Spark Structured Streaming)
* **Visualization Layer:** Tableau

## Data Processing & Machine Learning
Data processing and Machine Learning modeling are built using the **PySpark** framework:
1. **Data Cleaning:** Removing duplicate data, filtering invalid PM 2.5 values (less than 0), and handling missing values.
2. **Feature Engineering:** Extracting temporal features (year, month, day, hour) and classifying pollution levels into 3 classes: `Good`, `Moderate`, and `Unhealthy`.
3. **Handling Imbalanced Data:** Using the **SMOTE** (Synthetic Minority Over-sampling Technique) method to balance the target classes (especially the minority `Unhealthy` class).
4. **Classification Model:** Training a **Random Forest Classifier** model with Hyperparameter Tuning through 5-Fold Cross Validation.
   * **Best Parameters:** `numTrees = 50`, `maxDepth = 15`
   * **Model Performance:** Accuracy ~95.4% and F1-Score ~95.5%. The `day` and `hour` features are the most crucial predictors.

## Key Insights & Visualization
An interactive dashboard was created using **Tableau** to present data in an easily understandable way:
* **PM 2.5 Changes Over Time:** Identifying daily pollution peaks and air quality fluctuations.
* **Daily Average PM 2.5:** Analysis shows that day 5 and day 6 have the highest pollution levels, falling into the "Moderate" and "Unhealthy" categories.
* **Pollution Category Distribution:** Although the majority of the data indicates "Good" air quality, the system is capable of detecting anomalies during specific hours.
