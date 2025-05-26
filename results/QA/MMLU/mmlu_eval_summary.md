# MMLU Medical MCQ Evaluation Summary

## Overview
This report presents the results of evaluating various language models on medical multiple choice questions from the MMLU dataset.

## Dataset
- **Number of questions evaluated**: 100
- **Topic**: Medical knowledge (MCQs)

## Model Performance Summary

### Accuracy Metrics

| model_provider   | model_name              |   accuracy |   total_questions |   accuracy_pct | display_name                   |
|:-----------------|:------------------------|-----------:|------------------:|---------------:|:-------------------------------|
| azure            | gpt-4o-mini             |       0.87 |               100 |             87 | gpt-4o-mini (azure)            |
| groq             | llama-3.3-70b-versatile |       0.83 |               100 |             83 | llama-3.3-70b-versatile (groq) |
| groq             | mistral-saba-24b        |       0.78 |               100 |             78 | mistral-saba-24b (groq)        |
| groq             | gemma2-9b-it            |       0.75 |               100 |             75 | gemma2-9b-it (groq)            |
| groq             | llama-3.1-8b-instant    |       0.72 |               100 |             72 | llama-3.1-8b-instant (groq)    |

## Key Findings

* The best performing model was **gpt-4o-mini** (azure) with an accuracy of 87.00%
* The lowest performing model was **llama-3.1-8b-instant** (groq) with an accuracy of 72.00%
* The performance gap between the top and bottom model is 15.00 percentage points
* The average accuracy across all models was 79.00%

## Conclusion
There is a moderate performance gap between the models, suggesting that larger models generally perform better on medical knowledge tasks.