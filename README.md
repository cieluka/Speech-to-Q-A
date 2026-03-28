Speech to Question Answering System

Project Overview
This project builds a complete pipeline from speech input to text answers:
**Speech → Transcription → Question Analysis → Answer Extraction**

### Stage 1: Speech Transcription 
**Objective**: Convert audio to text using Whisper
- **Dataset**: LibriSpeech_test-clean (1,500 samples)
- **Model**: Whisper Base
- **Results**:
  - WER: **4.96%** 
  - CER: **1.96%** 
  - Success Rate: >99%

**Output**: librispeech_local_1500.json

### Stage 2: Text Analysis & Feature Extraction 
**Objective**: Extract keywords and identify entities for QA preparation
**Methods**:
- KeyBERT for semantic keyword extraction
- spaCy NER for entity recognition
- Question word pattern analysis

**Results**:
- Identified **17 entity types** (PERSON, DATE, GPE, ORG, etc.)
- Found **512 question word patterns**

**Output**: phase2_keywords.json, phase2_analysis.json

### Stage 3: QA System Development 
#### Stage 3A: Dataset Exploration
**Objective**: SQuAD v2 analysis (50000 samples)
**Analysis**:
  - Question type distribution (WHO/WHAT/WHEN/WHERE/HOW)
  - Answer patterns and entity mapping
#### Stage 3B: QA Model Implementation & Evaluation
**Objective**: Build extractive QA system and establish baseline
**Model**: RoBERTa-base-squad2
**Baseline Evaluation** (all samples):
  - Exact Match: **41.23%**
  - F1 Score: **45.47%**
**Analysis**: 
Current performance below standard benchmarks (EM 70%+, F1 75%+) provides 
valuable learning experience. The project demonstrates:
- Complete evaluation pipeline implementation
- Proper use of EM & F1 metrics
- Functional QA system with confidence scoring
#### Stage 4: Speech Question Answering System Implementation
End-to-end speech-based question answering using Whisper and RoBERTa.
