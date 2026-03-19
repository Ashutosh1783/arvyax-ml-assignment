# Error Analysis

This section analyzes failure cases and limitations of the model.

---------------------------------------------------------------------

## 1. Ambiguous Text
**Example:** "I’m fine"

- Problem: Text does not clearly express emotion
- Model prediction may be incorrect
- Improvement: Use context/history

-----------------------------------------------------------------------

## 2. Very Short Inputs
**Example:** "ok", "hmm"

- Problem: No meaningful signal
- Model struggles to predict correctly
- Improvement: Use default/fallback rules

--------------------------------------------------------------------------

## 3. Conflicting Signals
**Example:**
- Text: positive
- Stress level: high

- Problem: Model gets confused
- Improvement: Use weighted decision logic

------------------------------------------------------

## 4. Noisy Labels
- Problem: Training data may contain incorrect labels
- Effect: Model learns wrong patterns
- Improvement: Data cleaning or robust models

-------------------------------------------------------

## 5. Missing Values
- Problem: Some features are missing
- Solution: Filled using median
- Limitation: Not always accurate

---------------------------------------------------------

## 6. Sarcasm / Hidden Emotion
**Example:** "Great, another bad day..."

- Problem: Model interprets as positive
- Improvement: Advanced NLP models (BERT)

------------------------------------------------------------

## 7. Mixed Emotions
**Example:** "I feel tired but also hopeful"

- Problem: Single label cannot capture multiple emotions
- Improvement: Multi-label classification

------------------------------------------------------------

## 8. Long Noisy Text
- Problem: Irrelevant words affect prediction
- Improvement: Text cleaning or summarization

----------------------------------------------------------------

## 9. Low Confidence Predictions
- Problem: Model unsure about prediction
- Solution: Used confidence score and uncertain_flag

-----------------------------------------------------------------

## 10. Lack of Context
- Problem: Model does not know past history
- Improvement: Add user history or sequence modeling

-----------------------------------------------------------------

## Summary of error analysis

The main challenges were:
- Ambiguous and short text
- Conflicting signals
- Noisy real-world data

Future improvements can focus on better NLP models and contextual understanding.
