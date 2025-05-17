# Token Classification for Abbreviation and Long-form Detection

## Overview

This project explores various NLP approaches for **token classification**, specifically targeting **abbreviation (AC)** and **long-form (LF)** detection in biomedical texts using the **PLOD-CW-25** dataset. Tokens are labeled using the **BIO format**, with optional inclusion of POS tags. The goal is to build and evaluate models that can identify abbreviations and their expansions effectively.

## Dataset

- **Primary**: [PLOD-CW-25](https://huggingface.co/datasets/surrey-nlp/PLOD-CW-25)
- **Optional**: [PLODv2-filtered](https://huggingface.co/datasets/surrey-nlp/PLODv2-filtered)
- Label tags: `B-AC`, `B-LF`, `I-LF`, `B-O`

## Experiments

The following experiments are structured into three main categories, each with multiple variations:

### 🔬 Experiment 1: Model Architecture Comparison

- `Experiment1_Bert.ipynb`  
  Fine-tuning BERT for token classification.

- `Experiment1_RoBERTa.ipynb`  
  Fine-tuning RoBERTa to compare against BERT.

### ⚙️ Experiment 2: Training Configuration

- `Experiment2_adafactor.ipynb`  
  Training with the Adafactor optimizer.

- `Experiment2_schedulefree.ipynb`  
  Training without a learning rate scheduler for comparison.

### 📈 Experiment 3: Dataset Augmentation

- `Experiment3_Additional50.ipynb`  
  Including 50% training examples from PLODv2-filtered.

- `Experiment3_Additional25.ipynb`  
  Extending to 25% examples and analyzing performance impact.

## Evaluation

- **Metrics**: F1-score (primary), Precision, Recall  
- **Tool**: [`seqeval`](https://github.com/chakki-works/seqeval)  
- **Visualizations**: Confusion matrices and training curves

## Error Analysis

Manual inspection of misclassifications from the best-performing models helped identify common error patterns, label confusion, and domain-specific ambiguities.

## Deployment 

- Web deployment done using [`Streamlit`](https://tokenclassification.streamlit.app/) 
- Logging user inputs and predictions


You may extend this work with:
- Performance testing for scalability and latency

## Dependencies

Key Python libraries:
- `transformers`
- `datasets`
- `seqeval`
- `scikit-learn`
- `pandas`
- `matplotlib`

## Contributors

- [`SlightlyCodic`](https://github.com/SlightlyCodic): Model experimentation (BERT, RoBERTa) and integration
- [`AadityaArunSingh`](https://github.com/AadityaArunSingh): Data augmentation experiments
- Anish: Optimizer configuration and experiments
- Twinkle: Dataset Analysis and Visualizations



