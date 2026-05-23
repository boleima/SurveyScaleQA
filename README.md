# SurveyScaleQA


This repository contains the code, data, and analysis scripts for the Paper: **"Do LLMs Give Consistent Opinions? Evaluating Response Reliability Under Varying Likert-Scale Formulations in Survey-Style MCQA"** .

## Overview

Large Language Models (LLMs) are increasingly deployed as simulated respondents in social science research. However, their consistency as survey takers remains under explored. This project systematically investigates the mechanical stability of LLM responses by subjecting them to rigorous perturbations in answer options and presentation formats.

We isolate the artifacts of text generation from genuine semantic stability by evaluating four major model families (**Llama 3.1, Mistral v0.3, Qwen 2.5, Gemma 2**) across two experimental datasets derived from the [OpinionQA Corpus](https://github.com/tatsu-lab/opinions_qa).


## Repository Structure

```plaintext
├── data_clean/
│       ├── opinionQA_questions_final.csv  # Final Reworded Dataset
│       ├── opQA_shuffled_ans-opt.csv      # Final Shuffled Dataset
│       ├── results{1-4}_clean.csv         # Cleaned Results: IT models (Reworded)
│       ├── res{1-4}_shuffled_clean.csv    # Cleaned Results: IT models (Shuffled)
│       ├── res{1-4}_clean_bm.csv          # Cleaned Results: Base models (Reworded)
│       └── res{1-4}_shuff_clean_bm.csv    # Cleaned Results: Base models (Shuffled)
├── code/
│   ├── # --- Preprocessing & Cleaning ---
│   ├── preproc_questions_opqa.py          # Initial data cleaning
│   ├── shuffle_answer_opts.py             # Script to generate shuffled datasets
│   ├── clean_res_base-mod.py              # Output cleaner for Base models
│   ├── clean_res_instr-tuned.py           # Output cleaner for IT models
│   ├── # --- Model Inference ---
│   ├── run_questions.py                   # IT Models (Reworded Dataset)
│   ├── run_quest_shuffled.py              # IT Models (Shuffled Dataset)
│   ├── run_quest_base-models.py           # Base Models (Reworded Dataset)
│   ├── run_quest_shuff_base-mod.py        # Base Models (Shuffled Dataset)
│   └── # --- Analysis ---
│   └── result_analysis.py                 # Metrics calculation (APD/MPD) & Plotting
```
