
# RoboFusion Dataset

The RoboFusion Dataset is an open-source Real and Synthetic Dataset designed to support hazard prediction and environmental monitoring in industrial environments using Autonomous Mobile Robots (AMRs) and fixed IoT sensor suites.

This repository provides:
• Real and synthetic datasets for both normal and hazard conditions  
• Scripts for data augmentation for normal data synthesizing, fit models for hazard data synthesizing, hazard injection, and machine learning model validation (after paper publication)  
• A reproducible framework for synthetic data generation based on real-world behavior (after paper publication)

---

## Project Overview

RoboFusion is a data simulation and augmentation framework that collects sensor data from 2 mobile AMRs and 2 fixed sensor suites. The goal is to create a comprehensive dataset that includes both normal and hard-to-capture hazard scenarios using advanced modeling and augmentation techniques. The synthetic data mirrors real-world sensor signals under different environmental and operational conditions.

---

## Dataset Structure

• `Real_Dataset.csv`: Raw environmental readings collected via the ThingsBoard IoT platform  
• `Synthetic_Normal_Dataset.html`: Generated using:  
  - Noise Injection  
  - Time Warping  
  - Feature Scaling  
• `Synthetic_Hazard_Dataset.html`: Simulated using multi-stage hazard models (Ignition, Growth, Peak, Decay)  
• `Inject_Hazards_and_ML_Model.html`: Code for merging hazard and normal data and running ML predictions  
• `Merged_Dataset.csv`: Final combined dataset ready for training

---

## Sensor Suite

Each suite (AMR_1, AMR_2, Suite_1, Suite_2) includes:  
• T1, T2: Temperature sensors (ambient and onboard)  
• H%: Relative Humidity  
• P: Barometric Pressure  
• AL: Altitude  
• Dust: Particulate Matter Sensor  
• MQ2 – MQ135: Gas sensors (CO, CH₄, H₂, NH₃, LPG, alcohol, smoke, etc.)

---

## How to Use

1. Clone the repository  
   `git clone https://github.com/Amr-Khamis-84/RoboFusion-Dataset.git`
2. Explore the synthetic data files and preprocessing scripts  
3. Use or adapt the ML model pipeline to validate hazard detection  
4. Extend the synthetic generation techniques for your own use cases or datasets

---

## License

This project is licensed under the [Creative Commons Zero v1.0 Universal (CC0)](https://creativecommons.org/publicdomain/zero/1.0/).  
You are free to copy, modify, distribute, and use the dataset without restriction.

---

## Acknowledgments

The author extends sincere thanks to the **Industry Service Complex (ISC)** at the **Arab Academy for Science, Technology and Maritime Transport (AASTMT), Main Campus, Alexandria, Egypt**, for providing access to the manufacturing facilities and testing environment through the **Projects Implementation Workshop**.

During the preparation of this manuscript, the authors used **ChatGPT-4 (OpenAI, 2025)** for editorial suggestions and manuscript structuring. The authors have reviewed and validated all content manually.

---

## Contact

**Amr Khamis**  
GitHub: [Amr-Khamis-84](https://github.com/Amr-Khamis-84)
