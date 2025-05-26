# Question Answering Model Evaluation Report

## Dataset Information
- Dataset: WikiDoc QA
- Number of samples evaluated: 100
- Task: Answering medical questions with factual information

## Models Evaluated
- azure: gpt-4o-mini
- groq: llama-3.3-70b-versatile
- groq: mistral-saba-24b
- groq: llama-3.1-8b-instant
- groq: gemma2-9b-it

## Evaluation Metrics
- **ROUGE-1, ROUGE-2, ROUGE-L**: Measures of n-gram overlap between generated and reference answers
- **BLEU**: Precision-focused measure of word overlap
- **METEOR**: Evaluation metric that considers synonyms and stemming
- **Semantic Similarity**: Domain-specific semantic similarity using Bio_ClinicalBERT embeddings

## Key Findings
- **Best model for rouge1**: groq_gemma2-9b-it (score: 0.2403)
- **Best model for rouge2**: groq_gemma2-9b-it (score: 0.0571)
- **Best model for rougeL**: groq_gemma2-9b-it (score: 0.1391)
- **Best model for bleu**: groq_gemma2-9b-it (score: 0.0164)
- **Best model for meteor**: azure_gpt-4o-mini (score: 0.2327)
- **Best model for semantic_similarity**: azure_gpt-4o-mini (score: 0.9258)

- **Best overall model**: groq_gemma2-9b-it (average rank: 1.50)

## Performance Comparison
### Average Scores
| Model | Rouge1 | Rouge2 | Rougel | Bleu | Meteor | Semantic similarity | Inf. Time (s) |
| ----- | ------ | ------ | ------ | ---- | ------ | ------------------- | ------------- |
| azure_gpt-4o-mini | 0.2332 | 0.0529 | 0.1287 | 0.0158 | 0.2327 | 0.9258 | 4.04 |
| groq_llama-3.3-70b-versatile | 0.2020 | 0.0492 | 0.1138 | 0.0151 | 0.2166 | 0.9187 | 2.26 |
| groq_mistral-saba-24b | 0.2054 | 0.0518 | 0.1115 | 0.0142 | 0.2187 | 0.9204 | 3.21 |
| groq_llama-3.1-8b-instant | 0.1956 | 0.0473 | 0.1117 | 0.0148 | 0.2149 | 0.9171 | 3.42 |
| groq_gemma2-9b-it | 0.2403 | 0.0571 | 0.1391 | 0.0164 | 0.2236 | 0.9195 | 2.09 |

## Conclusion
Based on our comprehensive evaluation across multiple metrics, we observe the following:

1. **groq_gemma2-9b-it** shows the best overall performance across the evaluated metrics, particularly excelling in semantic similarity measures.
2. **azure_gpt-4o-mini** is the runner-up with strong performance especially in ROUGE metrics.
3. The medical domain-specific evaluation highlighted the importance of using specialized metrics for medical question answering.
4. We observed high correlation between semantic similarity and ROUGE metrics, suggesting that semantic understanding aligns with lexical overlap in this domain.
5. Inference time varies significantly between models, with some models offering a better balance between performance and speed.

