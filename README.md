# LLM Evaluation for Medical Question Answering

This project evaluates the performance of different Large Language Models (LLMs) on medical question answering tasks using the PubMed dataset.

## Project Structure

- `data/`: Contains raw and processed data files
  - `processed/pubmedqa_processed.csv`: Processed PubMed QA dataset
- `QA/`: Jupyter notebooks for running evaluations
  - `pubMed_eval.ipynb`: Notebook for evaluating models on PubMed data
- `scripts/`: Standalone scripts for evaluation
  - `pubmed_evaluation.py`: Command-line tool for running evaluations
- `results/`: Contains evaluation results
  - `QA/PubMed_TorF/`: Results for PubMed true/false/maybe questions
    - `plots/`: Visualizations of model performance
    - `summary_report.md`: Comprehensive evaluation report

## Setup

1. Create a `.env` file in the project root with your API keys:

```
AZURE_OPENAI_KEY=your_azure_openai_key
AZURE_OPENAI_VERSION=your_azure_openai_version
AZURE_ENDPOINT=your_azure_endpoint
AZURE_DEPLOYMENT_NAME=gpt-4o-mini
GROQ_API_KEY_SUB=your_groq_api_key
```

2. Install the required packages:

```bash
pip install openai groq pandas numpy matplotlib seaborn tqdm scikit-learn python-dotenv
```

## Running the Evaluation

### Using the Jupyter Notebook

1. Open `QA/pubMed_eval.ipynb` in Jupyter Notebook or JupyterLab
2. Run all cells to execute the evaluation

### Using the Command-line Script

```bash
cd LLM_Evaluation
python scripts/pubmed_evaluation.py --sample_size 100 --seed 42
```

Command-line options:
- `--data_path`: Path to the PubMed dataset CSV (default: "data/processed/pubmedqa_processed.csv")
- `--results_dir`: Directory to save results (default: "results/QA/PubMed_TorF")
- `--sample_size`: Number of samples to evaluate (default: 100)
- `--seed`: Random seed for sampling (default: 42)

## Results

The evaluation produces:

1. Individual JSON files with raw model responses
2. Confusion matrices for each model
3. An accuracy comparison chart
4. A comprehensive summary report (summary_report.md)
5. Error analysis data

The summary report includes:
- Overall accuracy for each model
- Detailed performance metrics for the best model
- Sample of errors made by each model
- Conclusions and insights
