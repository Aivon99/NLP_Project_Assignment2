# Assignment 2 – Sexism Detection with LLMs

This repository contains the implementation of Assignment 2 for the Natural Language Processing course (University of Bologna).  
The objective is to tackle **EDOS Task B**, a five-class classification problem for detecting sexist content using zero-shot and few-shot prompting on open-source Large Language Models (LLMs).

---

## Task Description

Given an input text, the model must assign one of the following labels:

- non-sexist  
- threats  
- derogation  
- animosity  
- prejudiced discussion  

The assignment evaluates model performance in zero-shot and few-shot settings, followed by an error analysis.

---

## Implemented Pipeline

### 1. Data Loading
- Loads `a2_test.csv` into a pandas DataFrame.
- Loads `demonstrations.csv` for few-shot prompting.

### 2. Model Setup
- Selection of two open-source LLMs from the assignment list.
- Quantization setup for single-GPU execution.
- Model and tokenizer loading using HuggingFace APIs.

### 3. Prompt Construction
- Zero-shot prompt formatting based on the assignment template.
- Few-shot prompt construction with balanced demonstrations.
- Helper functions:
  - `prepare_prompts`
  - `build_few_shot_demonstrations`

### 4. Inference
- Generates model responses for all test samples.
- Implements:
  - `generate_responses`
  - `process_response` for label extraction and mapping.

### 5. Metrics
- Accuracy  
- Macro F1-score  
- Fail-ratio (invalid or off-task responses)  
- Confusion matrices for both LLMs evaluated.

### 6. Error Analysis
- Performance comparison between chosen LLMs.
- Qualitative evaluation of incorrect outputs.
- Analysis of typical error patterns.

---
## Models Used

Two LLMs selected from the recommended list, quantized and evaluated.  
Examples include:

- Mistral  
- Llama  
- Phi  
- Qwen  
- TinyLlama  
- DeepSeek  

(Actual models specified in the notebook.)

---

## How to Run

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   
2. Login to HuggingFace (if using gated models):
   huggingface-cli login

3. Open and run the notebook:
   NLP_2526_A2 _consegna.ipynb

