# RoboSense: Hybrid Dataset Generation for Industrial Hazard Detection

This project provides a comprehensive dataset generation framework named **RoboSense**, designed to assist in training and validating machine learning models for hazard detection in industrial environments. The framework supports the creation of both real and synthetic datasets.

## Project Description

RoboSense is a hybrid (real and synthetic) dataset generation framework developed for use in industrial facilities equipped with IoT-based sensor networks and mobile robotic platforms. The objective is to enhance environmental monitoring and support predictive hazard detection using AI.

## Components

- **Sensor Suites**: Fixed and mobile sensors collecting telemetry data (temperature, humidity, pressure, gas concentrations).
- **Autonomous Mobile Robots (AMRs)**: Two robots equipped with sensor modules and localization via NFC tags.
- **Real Dataset**: Data collected over 90 days under normal and rare hazard conditions.
- **Synthetic Dataset**: Augmented using statistical techniques (normal) and fitted curve models (hazard).
- **ML Validation Pipeline**: Includes Random Forest, SVM, MLP, and XGBoost classifiers.

## Dataset Structure

- `Real_Dataset.csv`: Collected from four sensor suites across 90 days (including rare real hazard events).
- `Synthetic_Dataset.csv`: Includes 360 days of synthesized data for both normal and 15 hazard event types.

## Key Features

- Generalizable to multiple industrial settings.
- Supports binary classification: `Normal` vs. `Hazard_1`.
- Time-aligned sensor data at 1-minute intervals.
- Integration-ready with ThingsBoard IoT platform via MQTT.

## Publications and Citations

If you use this dataset or framework, please cite the following:

> RoboSense: A Hybrid Real and Synthetic Dataset Generation Framework for AI-driven Industrial Hazard Detection and Environmental Monitoring. Sensors, 2025.

## Additional Resources

- ⚙️ See [`USAGE.md`](./USAGE.md) for detailed dataset reuse guidelines and instructions.
