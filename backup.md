# Collaborative-Intelligence-based-Clinical-Triage-Dataset-CICTD-

![CICTD Toy Example](https://github.com/user-attachments/assets/c4df408d-fbfa-4613-945f-f35cc544c67e)

This repository provides the Collaborative Intelligence-based Clinical Triage Dataset (CICTD) along with the simulation code to facilitate research and development in intelligent clinical triage systems.

# Abstract

AI offers the important potential to enhance Emergency Room (ER) triage efficiency  but a lack of trust from healthcare professionals and patients limits its adoption due to concerns over accuracy and reliability. To address this, we introduce the Collaborative Intelligence-based Clinical Triage Dataset (CICTD), a large-scale benchmark containing patient requests and ER doctor annotations for triage decision-making. Along with CICTD, we define key evaluation tasks, including diagnostic question generation, ESI level prediction, triage recommendations, and misdiagnosis prediction. Our approach emphasizes a human-in-the-loop framework, ensuring AI escalates uncertain cases to experts, balancing automation with trust and improving ER triage efficiency.

# Contribution:

-**Introducing CICTD**, a large-scale benchmark dataset with real-world patient ER requests and expert annotations for triage decisions.

-**Defining** multiple key evaluation tasks along with evaluation metrics, supporting both individual and city-wide AI or CI-driven triage decisions.

-**Conceptualizing** a human-in-the-loop AI framework, ensuring AI models defer to experts when uncertainty is high, enhancing trust and efficiency in ER decision-making.

-**Providing** a foundation for the development of trustworthy AI systems in emergency medicine, bridging the gap between AI automation and expert-driven healthcare.

# Example of Structured MIMIC-IV Record and Corresponding GPT-4 Contextualized Input

## Processed MIMIC-IV Structured Record

-**Subject ID:** 11714491

-**Stay ID:** 30000012

-**Age:** 66

-**Gender:** Female

-**Arrival Transport:** Ambulance

-**Disposition:** Admitted

-**Chief Complaint:** Change in Mental Status

**Vital Signs**

- HR: 96.0 bpm
- BP: 98.8 mmHg
- RR: 18.0 / min

**Discharge Report:**She presents with CC of AMS and confusion noted since 9am this morning, noted by her visiting nurse and husband. Husband accompanied her to the ED and reports that these episodes of confusion have been recurrent, however, she had been doing well since her discharge last week. Today she has expressed forgetfulness...

-**ICD-9 Code:** 5722

-**ICD Title (Diagnosis):** Hepatic Encephalopathy

-**Acuity:** 2.0

-**Intime:** 2126-02-14 20:22:00

-**Outtime:** 2126-02-15 01:59:00

---

## GPT-4 Contextualized Output

**Chief Complaint (Free-Text):**

> “I feel really confused and can’t remember things, like why I was putting in my dentures or what to do in the kitchen, and it’s really scary.”

**History Summary:**

The patient has a significant past medical history including alcoholic cirrhosis diagnosed several years ago, classified as Child-Pugh Class C, complicated by Grade II esophageal varices (treated with banding), hepatic encephalopathy, hepatocellular carcinoma (HCC) in segment IV, and portal venous thrombosis.

She has a history of chronic back pain, myelodysplastic syndrome, muscle spasms, cataract surgery, and a cerebellar TIA without residual deficits. She's also had GI bleeding and is being considered for a liver transplant.

Her medications include furosemide, spironolactone, tramadol, gabapentin, bisacodyl, multivitamins, pantoprazole, and rifaximin. Family history includes alcoholic liver disease (father) and diabetes (paternal side). No siblings or coronary artery disease.

**Physician-Patient Dialogue:**

1.**Q:** When did you first start feeling confused and having trouble remembering things?**A:** I started feeling confused this morning, around 9 AM.

2.**Q:** Have you noticed any changes in your behavior or personality recently?**A:** Yes, I’ve been more forgetful and having trouble focusing.

3.**Q:** Given your history of hepatic encephalopathy, have you had any episodes of confusion or memory loss in the past?

**A:** Yes, but this time it's worse than usual.

# Statistics

## Dataset Statistics

| **Category**                            | **Statistic**               | **Value / Distribution**                                    |

| --------------------------------------------- | --------------------------------- | ----------------------------------------------------------------- |

| **Overall Scale**                       | Total ED Visits                   | 12000                                                             |

|                                               | Unique Patients                   | 11407                                                             |

|                                               | Expert-Annotated Cases            | 300                                                               |

|                                               | % ED Visits with Discharge Report | 42.58%                                                            |

|                                               | Simulation Time Span              | 50 Days (1/3 Normal, 1/3 Flu, 1/3 Covid periods)                  |

|                                               | # of Cities                       | 6 (Boston, Houston, Minneapolis, St. Louis, Detroit, New Orleans) |

|                                               | # of Lab Tests Covered            | 36 (CBC, BMP, etc)                                                |

| **ESI Distribution (# of Patients)**    | ESI 1                             | 640                                                               |

|                                               | ESI 2                             | 3817                                                              |

|                                               | ESI 3                             | 6618                                                              |

|                                               | ESI 4                             | 892                                                               |

|                                               | ESI 5                             | 33                                                                |

| **Hourly Patient Arrival Distribution** | Late Night (00:00–06:00)         | Mean: 34.91, Std: 21.15                                           |

|                                               | Morning (06:00–12:00)            | Mean: 85.714, Std: 51.71                                          |

|                                               | Afternoon (12:00–18:00)          | Mean: 102.71, Std: 62.51                                          |

|                                               | Evening (18:00–24:00)            | Mean: 119.51, Std: 72.93                                          |

| **ED Outcomes**                         | % of Admitted                     | 31.45%                                                            |

|                                               | % of Went Home                    | 62.56%                                                            |

## Annotation Task Description

| Annotation Task               | Description                                                                                     | Label Choices                                                  |

|------------------------------|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------|

| Physician Question Relevance | Expert annotators judge how each physician-posed question contributes to accurate triage decision-making. | Perfectly relevant, Partially relevant, Irrelevant, Incorrect |

| ESI Level Assignment         | Assign preliminary Emergency Severity Index (ESI) level based on the narrative and dialogue.     | 1, 2, 3, 4, 5                                                  |

| ER Recommendation            | Recommend the most appropriate treatment location given initial patient presentation.            | Tertiary ED, Community ED, Urgent Care, Observation Unit, Other |

| Safe Wait Time Estimation    | Estimate the maximum safe waiting period before patient risk escalates.                         | 0–10 min, 10–30 min, 30–60 min, 60–240 min, >240 min          |

| Laboratory Test Recommendation | Determine whether each common laboratory test should be ordered.                                 | CBC; BMP; Troponin; D-dimer; Urinalysis, etc                  |
