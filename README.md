# Big Data Architecture for Real-Time Air Quality Monitoring in Brooklyn, New York

**Course:** COM579001P6 – Big Data Processing[cite: 2, 3]  
**University:** BINUS University Alam Sutera[cite: 3]

## Project Summary
Urban air pollution is a major public health concern[cite: 2, 3]. This project implements a **Big Data Architecture** to ingest, store, process, and analyze IoT sensor data in real-time for air quality monitoring in Brooklyn, New York[cite: 2, 3]. The primary focus of this analysis is tracking **PM 2.5** levels to detect pollution spikes, identify high-risk areas, and support decision-making[cite: 2, 3].

## Dataset
* **Source:** [Kaggle - Air Quality Data in Brooklyn, NY (OpenAQ 2025)](https://www.kaggle.com/datasets/aidenl25/air-quality-data-in-brooklyn-ny-openaq-2025)[cite: 2, 3]
* **Description:** Contains hourly PM 2.5 measurements, timestamps, geographic coordinates, and station metadata from various monitoring sensors[cite: 2, 3].

## Big Data Architecture
The proposed architecture uses a layered approach designed for deployment on a **Public Cloud** (Google Cloud Platform)[cite: 2, 3]:
* **Ingestion Layer:** Real-Time Streaming Pipeline[cite: 2, 3]
* **Storage Layer:** Apache Hadoop HDFS (for historical data) & Apache HBase (for real-time read/write)[cite: 2, 3]
* **Analytics Engine:** Apache Spark & PySpark (Batch & Spark Structured Streaming)[cite: 2, 3]
* **Visualization Layer:** Tableau[cite: 2, 3]

## Data Processing & Machine Learning
Data processing and Machine Learning modeling are built using the **PySpark** framework[cite: 2, 3]:
1. **Data Cleaning:** Removing duplicate data, filtering invalid PM 2.5 values (less than 0), and handling missing values[cite: 1, 3].
2. **Feature Engineering:** Extracting temporal features (year, month, day, hour) and classifying pollution levels into 3 classes: `Good`, `Moderate`, and `Unhealthy`[cite: 1, 2, 3].
3. **Handling Imbalanced Data:** Using the **SMOTE** (Synthetic Minority Over-sampling Technique) method to balance the target classes (especially the minority `Unhealthy` class)[cite: 1, 2, 3].
4. **Classification Model:** Training a **Random Forest Classifier** model with Hyperparameter Tuning through 5-Fold Cross Validation[cite: 1, 2, 3].
   * **Best Parameters:** `numTrees = 50`, `maxDepth = 15`[cite: 1, 2, 3]
   * **Model Performance:** Accuracy ~95.4% and F1-Score ~95.5%[cite: 1, 2, 3]. The `day` and `hour` features are the most crucial predictors[cite: 1, 3].

## Key Insights & Visualization
An interactive dashboard was created using **Tableau** to present data in an easily understandable way[cite: 2, 3]:
* **PM 2.5 Changes Over Time:** Identifying daily pollution peaks and air quality fluctuations[cite: 2, 3].
* **Daily Average PM 2.5:** Analysis shows that day 5 and day 6 have the highest pollution levels, falling into the "Moderate" and "Unhealthy" categories[cite: 2, 3].
* **Pollution Category Distribution:** Although the majority of the data indicates "Good" air quality, the system is capable of detecting anomalies during specific hours[cite: 2, 3].
* **Joshua Ferdinand**[cite: 2, 3]
* **Sylvester Luigi Hidayat**[cite: 2, 3]
* **Hansel Lie Arifin**[cite: 2, 3]
