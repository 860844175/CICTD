# Collaborative-Intelligence-based-Clinical-Triage-Dataset-CICTD-
![CICTD Toy Example](https://github.com/user-attachments/assets/f23f61cf-8663-42cd-b7a6-651bb1d6e5f5)


This repository provides the Collaborative Intelligence-based Clinical Triage Dataset (CICTD) along with the simulation code to facilitate research and development in intelligent clinical triage systems.

# Abstract
AI offers the important potential to enhance Emergency Room (ER) triage efficiency  but a lack of trust from healthcare professionals and patients limits its adoption due to concerns over accuracy and reliability. To address this, we introduce the Collaborative Intelligence-based Clinical Triage Dataset (CICTD), a large-scale benchmark containing patient requests and ER doctor annotations for triage decision-making. Along with CICTD, we define key evaluation tasks, including diagnostic question generation, ESI level prediction, triage recommendations, and misdiagnosis prediction. Our approach emphasizes a human-in-the-loop framework, ensuring AI escalates uncertain cases to experts, balancing automation with trust and improving ER triage efficiency.


# Statistics
## Dataset Statistics
| **Category** | **Statistic** | **Value / Distribution** |
|-------------|-------------|--------------------------|
| **Overall Scale** | Total ED Visits | 12000 |
|  | Unique Patients | 11407 |
|  | Expert-Annotated Cases | 300 |
|  | % ED Visits with Discharge Report | 42.58% |
|  | Simulation Time Span | 50 Days (1/3 Normal, 1/3 Flu, 1/3 Covid periods) |
|  | # of Cities | 6 (Boston, Houston, Minneapolis, St. Louis, Detroit, New Orleans) |
|  | # of Lab Tests Covered | 36 (CBC, BMP, etc) |
| **ESI Distribution (# of Patients)** | ESI 1 | 640 |
|  | ESI 2 | 3817 |
|  | ESI 3 | 6618 |
|  | ESI 4 | 892 |
|  | ESI 5 | 33 |
| **Hourly Patient Arrival Distribution** | Late Night (00:00–06:00) | Mean: 34.91, Std: 21.15 |
|  | Morning (06:00–12:00) | Mean: 85.714, Std: 51.71 |
|  | Afternoon (12:00–18:00) | Mean: 102.71, Std: 62.51 |
|  | Evening (18:00–24:00) | Mean: 119.51, Std: 72.93 |
| **ED Outcomes** | % of Admitted | 31.45% |
|  | % of Went Home | 62.56% |


## Annotation Task Description
| **Task Name**                        | **Annotation Goal**                                                  |
|---------------------------------------|----------------------------------------------------------------------|
| **Diagnosis Question**                | Annotate 10 given diagnostic questions as **Essential / Optional / Wrong**. |
| **Missing Essential Question**        | If none of the 10 given diagnostic questions cover the most critical inquiry, provide the missing essential question. |
| **Diagnosis Lab Test Recommendation** | Identify and annotate the **recommended diagnostic lab tests** for the patient. |
| **ER Test Recommendation**            | Determine and annotate the **type of emergency room (ER) the patient should visit** (e.g., ER with Oncology and Pulmonology Support). |
| **Maximum Safe Waiting Time**         | Estimate the **maximum safe waiting time** for the patient before seeking medical attention. |



