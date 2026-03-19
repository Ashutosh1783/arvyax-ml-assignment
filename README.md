# ArvyaX Machine Learning Assignment

# Overview
This project builds an AI system that understands user emotions from text and contextual signals, and suggests meaningful actions to guide them toward a better mental state.

-------------------------------------------------

## Approach for this project

The system is divided into 3 main parts:

1. **Emotion Understanding**
   - Predicts emotional_state
   - Predicts intensity (1–5)

2. **Decision Engine**
   - Suggests what_to_do (e.g., rest, breathing, deep work)
   - Suggests when_to_do (now, later, tonight)

3. **Uncertainty Modeling**
   - Provides confidence score
   - Flags uncertain predictions

-----------------------------------------------------

## Features Used in this project

### Text Feature
- journal_text (main signal)

### Metadata Features
- sleep_hours
- energy_level
- stress_level
- time_of_day

----------------------------------------------------

## Model Details

### Emotional State
- Type: Classification
- Model: Logistic Regression

### Intensity
- Type: Classification (1–5)
- Model: Logistic Regression

--------------------------------------------------------

## Decision Logic

A rule-based system is used:

- High stress + low energy → Rest (now)
- High stress + high energy → Breathing (now)
- High energy → Deep Work (within 15 min)
- Sad/Anxious → Journaling (later today)
- Night → Sleep (tonight)

---------------------------------------------------------

## Confidence & Uncertainty

- Confidence is calculated using `predict_proba()`
- If confidence < 0.5 → uncertain_flag = 1

--------------------------------------------------------

## Handling Real-World Challenges

- Missing values → filled using median
- Noisy text → handled using TF-IDF
- Short inputs → handled via fallback logic
- Conflicting signals → resolved using rules

-----------------------------------------------------------

## How to Run

1. Place `Sample_arvyax_reflective_dataset.xlsx - Dataset_120.csv` and `arvyax_test_inputs_120.xlsx - Sheet1.csv` in the same folder
2. Run the script:
   Aryax.ipynb
3. Output file will be generated as:
predictions.csv

---

## Output Format

The output contains:

- id  
- predicted_state  
- predicted_intensity  
- confidence  
- uncertain_flag  
- what_to_do  
- when_to_do  

--------------------------------------------------

## Future Improvements

- Use advanced NLP models (BERT)
- Handle sarcasm better
- Use conversation history
- Multi-label emotion detection

--------------------------------------------------

## Conclusion(Final words)

This system goes beyond prediction by combining machine learning with decision logic to guide users toward better mental states.
