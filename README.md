Speech to Question Answering System

Project Overview
This project builds a complete pipeline from speech input to text answers:
**Speech → Transcription → Question Analysis → Answer Extraction**

Pipeline Stages
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
