# Azure AI & Microsoft Foundry – Complete Study Notes

---

# Analyze Text with Azure Language

## Introduction

Azure Language enables applications to extract meaning from large volumes of text-based data such as emails, reviews, and business documents.

It provides APIs for:

- Language detection  
- Sentiment analysis  
- Key phrase extraction  
- Named entity recognition  
- Entity linking  

## Provision an Azure Language Resource

To use Azure Language:

1. Create a Language resource in Azure.
2. Retrieve:
   - Endpoint
   - Subscription key
3. Call APIs via:
   - REST (JSON)
   - SDKs

---

# Create Question Answering Solutions with Azure Language

## Overview

Question answering enables users to ask natural language questions and receive answers from a knowledge base.

## Knowledge Base

Sources:

- FAQ websites  
- Structured documents  
- Built-in chit-chat datasets  

## Multi-Turn Conversations

Allows follow-up clarification before returning a final answer.

Example:  
“How can I cancel a reservation?”  
→ Follow-up: Hotel or flight?

## Testing & Deployment

- Train model  
- Test in Language Studio  
- Inspect confidence scores  
- Deploy to REST endpoint  

## Performance Improvement

### Active Learning

Improves answer quality by learning alternative phrasings.

### Synonyms

Enhance understanding of similar expressions.

---

# Build a Conversational Language Understanding (CLU) Model

## NLP Design Pattern

1. User input  
2. Intent detection  
3. Action execution  

## Core Concepts

### Intents

User goals (e.g., GetWeather, TurnOnDevice)

### Utterances

Different ways to express the same intent.

### Entities

Context data (e.g., DeviceName)

Types:

- Learned  
- List  
- Prebuilt  

## Patterns

Used to differentiate similar utterances:

- Turn on the {DeviceName}  
- Is the {DeviceName} on?  

## Prebuilt Capabilities

- Summarization  
- Named Entity Recognition  
- PII detection  
- Sentiment analysis  
- Language detection  

---

# Custom Text Classification

## Project Types

- Single label  
- Multiple label  

## Evaluation Metrics

- Precision  
- Recall  
- F1 Score  

## Lifecycle

1. Define labels  
2. Tag data  
3. Train  
4. Evaluate  
5. Improve  
6. Deploy  

Dataset split:

- 80% training  
- 20% testing  

---

# Custom Named Entity Recognition (NER)

## Labeling Guidelines

- Consistency  
- Precision  
- Completeness  

## Evaluation

### Precision vs Recall

- Low precision → wrong labels  
- Low recall → missed entities  

### Confusion Matrix

Used for visual error analysis.

---

# Translate Text with Azure Translator

## Capabilities

- Language detection  
- One-to-many translation  
- Transliteration  

## Custom Translator

Steps:

1. Create workspace  
2. Create project  
3. Upload training data  
4. Train model  
5. Publish model  
6. Call API  

---

# Create Speech-Enabled Apps

## Speech APIs

- Speech to Text  
- Text to Speech  
- Speech Translation  
- Keyword Recognition  
- Intent Recognition  

## Speech to Text Pattern

1. SpeechConfig  
2. AudioConfig  
3. SpeechRecognizer  
4. RecognizeOnceAsync()  
5. Process SpeechRecognitionResult  

## Text to Speech Pattern

1. SpeechConfig  
2. AudioConfig  
3. SpeechSynthesizer  
4. SpeakTextAsync()  
5. Process SpeechSynthesisResult  

## SSML (Speech Synthesis Markup Language)

Allows advanced control:

- Speaking style  
- Pauses  
- Phonemes  
- Prosody  
- Say-as rules  
- Insert audio  

---

# Translate Speech with Azure Speech

## Speech Translation Pattern

1. SpeechTranslationConfig  
   - Source language  
   - Target languages  
2. AudioConfig  
3. TranslationRecognizer  
4. RecognizeOnceAsync()  

Result includes:

- Text (original transcription)  
- Translations dictionary  

## Synthesize Translations

### Event-Based Synthesis

- Real-time  
- Uses Synthesizing event  

### Manual Synthesis

- Iterate through Translations  
- Use SpeechSynthesizer per language  

---

# Develop an Audio-Enabled Generative AI Application

## Multimodal Models

Support:

- Text input  
- Audio input  
- Mixed prompts  

## Audio-Based Chat App

Same pattern as text chat, but:

User message includes:

- Text content item  
- Audio content item  

---

# Develop an Azure AI Voice Live Agent

## Azure AI Voice Live API

Real-time bidirectional speech-to-speech API.

Key characteristics:

- WebSocket-based  
- Low latency  
- No manual orchestration  

## Features

- Real-time audio processing (PCM16, G.711)  
- OpenAI voices and Azure custom voices  
- Avatar streaming (WebRTC)  
- Noise reduction and echo cancellation  

## Authentication

### Microsoft Entra (Recommended)

- Token-based authentication  
- Cognitive Services User role required  
- Bearer token in Authorization header  

### API Key

- Header-based or query string parameter  

## WebSocket Endpoints

Project connection:
wss://<resource>.services.ai.azure.com/voice-live/realtime


Model connection:
wss://<resource>.cognitiveservices.azure.com/voice-live/realtime


## Events

### Client Events

- session.update  
- input_audio_buffer.append  
- response.create  

### Server Events

- session.updated  
- response.done  
- conversation.item.created  

---

# Summary

This document covers:

- Azure Language (Text Analytics, Q&A, CLU, Classification, NER)  
- Azure Translator  
- Azure Speech (STT, TTS, Translation, SSML)  
- Multimodal Generative AI  
- Azure AI Voice Live API  
- Real-time voice agents  

Conceptual progression:

Text → Intent → Knowledge → Classification → Translation → Speech → Multimodal → Real-Time Voice Agents