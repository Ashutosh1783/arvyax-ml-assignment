# Edge Deployment Plan

This section explains how the system can run efficiently on edge devices like mobile phones.

-----------------------------------------------------------------

## Model Choice

- Used Logistic Regression (lightweight model)
- TF-IDF vectorizer with limited features
- Low memory footprint

-------------------------------------------------------------------------

## Why Suitable for Edge?

- Fast inference (milliseconds)
- Small model size
- No GPU required
- Can run offline

-------------------------------------------------------------------------------

## Deployment Approach

1. Train model offline (on laptop/server)
2. Save model using joblib/pickle
3. Load model in mobile/backend system
4. Run predictions locally

------------------------------------------------------------------------------------

## Latency

- Prediction time is very low (<100 ms)
- Suitable for real-time user interaction

------------------------------------------------------------------------------------

## Memory Usage

- TF-IDF + Logistic Regression → low RAM usage
- Works on low-end devices

-----------------------------------------------------------------------------------

## Trade-offs

| Aspect        | Trade-off |
|--------------|----------|
| Accuracy     | Moderate |
| Speed        | High |
| Model Size   | Small |
| Complexity   | Low |

-----------------------------------------------------------------------------------

## Robustness

- Handles missing values using median
- Handles short text using fallback logic
- Uses uncertainty flag for low-confidence cases

----------------------------------------------------------------------------------------

## Future Improvements

- Use compact transformer models (TinyBERT)
- Quantization for smaller size
- On-device learning for personalization

--------------------------------------------------------------------------------------------

## Conclusion(Final words)

The system is lightweight, fast, and suitable for deployment on edge devices while maintaining reasonable performance.
