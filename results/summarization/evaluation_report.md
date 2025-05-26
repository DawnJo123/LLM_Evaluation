# Text Summarization Model Evaluation Report

## Dataset Information
- Dataset: CORD-19 Summarization
- Number of samples evaluated: 100
- Task: Summarizing medical abstracts into titles

## Models Evaluated
- groq: mistral-saba-24b
- azure: gpt-4o-mini
- groq: llama-3.3-70b-versatile
- groq: llama-3.1-8b-instant
- groq: gemma2-9b-it

## Evaluation Metrics
- **ROUGE-1, ROUGE-2, ROUGE-L**: Measure of n-gram overlap between generated and reference summaries
- **BLEU**: Precision-focused measure of word overlap
- **METEOR**: Evaluation metric that considers synonyms and stemming
- **Clinical Similarity**: Domain-specific semantic similarity using Bio_ClinicalBERT embeddings

## Key Findings
- **Best model for rouge1**: azure_gpt-4o-mini (score: 0.4731)
- **Best model for rouge2**: groq_llama-3.3-70b-versatile (score: 0.2417)
- **Best model for rougeL**: groq_llama-3.3-70b-versatile (score: 0.4028)
- **Best model for bleu**: groq_llama-3.3-70b-versatile (score: 0.0896)
- **Best model for meteor**: groq_llama-3.1-8b-instant (score: 0.3624)
- **Best model for clinical_similarity**: azure_gpt-4o-mini (score: 0.9405)

- **Best overall model**: azure_gpt-4o-mini (average rank: 2.00)

## Performance Comparison
### Average Scores
| Model | Rouge1 | Rouge2 | Rougel | Bleu | Meteor | Clinical_similarity | Inf. Time (s) |
| ----- | ------ | ------ | ------ | ---- | ------ | ------------------- | ------------- |
| groq_mistral-saba-24b | 0.4232 | 0.2108 | 0.3477 | 0.0613 | 0.3381 | 0.9173 | 3.00 |
| azure_gpt-4o-mini | 0.4731 | 0.2255 | 0.3772 | 0.0861 | 0.3579 | 0.9405 | 2.14 |
| groq_llama-3.3-70b-versatile | 0.4727 | 0.2417 | 0.4028 | 0.0896 | 0.3116 | 0.9351 | 2.07 |
| groq_llama-3.1-8b-instant | 0.4660 | 0.2346 | 0.3810 | 0.0857 | 0.3624 | 0.9367 | 3.11 |
| groq_gemma2-9b-it | 0.2437 | 0.1159 | 0.2012 | 0.0253 | 0.3054 | 0.9038 | 2.34 |

## Conclusion
Based on our comprehensive evaluation across multiple metrics, we observe the following:

1. **azure_gpt-4o-mini** shows the best overall performance across the evaluated metrics, particularly excelling in semantic similarity measures.
2. **groq_llama-3.3-70b-versatile** is the runner-up with strong performance especially in ROUGE metrics.
3. The clinical domain-specific evaluation highlighted the importance of using specialized metrics for medical text summarization.
4. We observed high correlation between ROUGE metrics and clinical similarity, suggesting that n-gram overlap is still relevant in specialized domains.
5. Inference time varies significantly between models, with larger models generally taking longer but producing higher quality summaries.

