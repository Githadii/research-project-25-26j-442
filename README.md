# Integrated Predictive Intelligence Tool for Pediatric Health

[![Project ID](https://img.shields.io/badge/Project%20ID-25--26J--442-blue)](https://github.com)
[![Research Group](https://img.shields.io/badge/Research%20Group-CoEAI-green)](https://github.com)
[![Specialization](https://img.shields.io/badge/Specialization-Software%20Engineering-orange)](https://github.com)

> **An AI-powered mobile decision support system that unifies predictive analytics, personalized nutrition, emergency response, and multilingual voice support to enhance pediatric healthcare.
publication - https://ieeexplore.ieee.org/document/11600063**

---

## 📋 Table of Contents

- [Introduction](#-introduction)
- [Problem Statement](#-problem-statement)
- [Proposed Solution](#-proposed-solution)
- [Key Features](#-key-features)
- [System Architecture](#-system-architecture)
- [Project Structure](#-project-structure)
- [Technology Stack](#-technology-stack)
- [Getting Started](#-getting-started)
- [Components](#-components)
- [API Documentation](#-api-documentation)
- [Research Background](#-research-background)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Introduction

Pediatric healthcare faces numerous challenges including **delayed diagnosis**, **fragmented data**, and **limited accessibility**, especially in resource-constrained or multilingual settings. This research project (IT4010 - 2025 July Batch) proposes a mobile-based, AI-driven decision support system that enhances pediatric care through:

- 🔮 **Predictive Analytics** - Early risk detection
- 🍎 **Personalization** - Adaptive nutrition plans
- 🚨 **Real-Time Response** - Emergency support
- 🗣️ **Intelligent Accessibility** - Multilingual voice interface

---

## ❌ Problem Statement

Current pediatric healthcare systems suffer from several critical gaps:

### 1. **Fragmented Data Analysis**
Most tools analyze growth, nutrition, behavior, and environment **separately**, without linking their interdependencies.

### 2. **Static Nutrition Recommendations**
Existing apps provide non-behavior-aware nutrition recommendations that don't adapt to individual needs.

### 3. **Delayed Emergency Response**
Emergency response in children is often delayed due to lack of real-time prediction and routing tools.

### 4. **Accessibility Barriers**
Caregivers with low literacy or limited language proficiency struggle to use digital healthcare systems.

### 5. **No Unified Platform**
There is no single platform that integrates predictive AI, real-time decision support, and voice-based assistance in the pediatric domain.

---

## ✅ Proposed Solution

### Solution Overview
A **mobile-based AI system** that unifies predictive analytics, personalized nutrition, emergency response, and multilingual voice support to enhance pediatric healthcare.

### Key Objectives
- ✅ Predict early pediatric health risks using integrated data
- ✅ Personalize nutrition plans based on behavior and input
- ✅ Guide caregivers during emergencies with real-time insights
- ✅ Enable inclusive access via multilingual voice interface
- ✅ Deliver unified, explainable health analytics

---

## 🌟 Key Features

### 1. **AI-Driven Predictive Health Analytics with Multi-Domain Integration**
- Integrates growth metrics, nutrition, behavior, and environmental factors
- Predicts developmental delays, malnutrition, ADHD, and autism spectrum disorders
- Uses advanced machine learning and time-series modeling
- Provides early risk detection before clinical symptoms arise

### 2. **ML-Driven Personalized Nutrition Optimization with Behavioral Analysis**
- Collaborative filtering and NLP-based meal planning
- Adapts to dietary needs, allergies, and behavioral patterns
- Food image scanner for nutritional content estimation
- Community feed for caregiver engagement and knowledge sharing

### 3. **Real-Time Emergency Response Integration with Predictive Risk Assessment**
- Analyzes real-time data and historical trends
- Intelligent alerts and risk level assessment
- Live teleconsultation with healthcare professionals
- Dynamic routing to nearest pediatric care facility

### 4. **Voice-Activated Caregiver Support with Multilingual Conversational AI**
- Speech-to-text and multilingual translation
- Natural language interaction for diverse linguistic backgrounds
- Real-time guidance and support
- Powered by advanced LLM models (OpenAI, Gemini, Claude)

---

## 🏗️ System Architecture

<div align="center">
  <img src="https://i.postimg.cc/9MGfkdXf/Picture1.png" alt="PediTrack System Architecture" width="100%">
</div>

### Architecture Overview

The system follows a **microservices architecture** with four main layers:

1. **📱 Mobile Application Layer** (React Native + Expo)
   - Home Screen, Health Analytics, AI Chat, Nutrition & Feed, Location & Emergency

2. **🖥️ Backend Services Layer**
   - Chat Service (Node.js - Port 3001)
   - RAG Service (Python/FastAPI - Port 3002)
   - Health Analytics Service (Node.js - Port 5001)
   - Nutrition & Feed Service
   - Risk Assessment Service

3. **🧠 AI/ML Layer**
   - LLM APIs (OpenAI, Gemini, Claude)
   - Vector Store (FAISS - 24,855 documents)
   - Predictive Models
   - NLP/Voice Processing (Whisper)

4. **💾 Data Layer**
   - MongoDB (Health Records)
   - Medical Knowledge Base
   - User Data & Profiles
   - Emergency Services Database

---

## 📁 Project Structure

```
research-project-25-26j-442/
│
├── 📱 peditrackv2/                    # React Native Mobile Application
│   ├── app/                           # Expo Router app directory
│   │   ├── (tabs)/                    # Tab navigation screens
│   │   ├── health-analytics/          # Health analytics screens
│   │   ├── chat.tsx                   # AI chat screen
│   │   └── ...
│   ├── src/
│   │   ├── components/                # Reusable UI components
│   │   ├── screens/                   # Screen components
│   │   │   ├── ConversationalAI/      # AI chat interface
│   │   │   ├── HealthAnalytics/       # Health tracking screens
│   │   │   ├── Nutrition/             # Nutrition & feed screens
│   │   │   └── RiskAssessment/        # Emergency & risk screens
│   │   ├── services/                  # API service clients
│   │   │   ├── chatService.ts         # Chat API client
│   │   │   ├── healthAnalyticsService.ts
│   │   │   └── voiceService.ts        # Voice processing
│   │   └── types/                     # TypeScript definitions
│   ├── assets/                        # Images, fonts, etc.
│   └── package.json
│
├── 🖥️ services/                       # Backend Microservices
│   │
│   ├── peditrack-chat-service/        # AI Chat Service (Node.js)
│   │   ├── src/
│   │   │   ├── controllers/           # Request handlers
│   │   │   ├── services/              # Business logic
│   │   │   │   └── llm.service.js     # LLM integration
│   │   │   └── server.js              # Express app
│   │   ├── .env                       # Environment config
│   │   ├── package.json
│   │   └── QUICK_START.md
│   │
│   ├── peditrack-rag-service/         # RAG Service (Python/FastAPI)
│   │   ├── services/
│   │   │   ├── embedding_service.py   # Text embeddings
│   │   │   ├── vector_store.py        # FAISS vector DB
│   │   │   ├── ingestion_service.py   # Data ingestion
│   │   │   └── retrieval_service.py   # Document retrieval
│   │   ├── routes/
│   │   │   └── rag_routes.py          # API endpoints
│   │   ├── scripts/                   # Dataset management
│   │   │   ├── init_vector_store.py
│   │   │   ├── ingest_dataset.py
│   │   │   └── visualize_vectors.py
│   │   ├── data/
│   │   │   ├── raw_datasets/          # Downloaded datasets
│   │   │   └── processed/             # Preprocessed data
│   │   ├── vector_store/              # FAISS index storage
│   │   ├── tests/                     # RAG evaluation
│   │   │   └── rag_evaluator.py
│   │   ├── main.py                    # FastAPI app
│   │   ├── requirements.txt
│   │   └── README.md
│   │
│   ├── health-analytics-service/      # Health Analytics (Node.js)
│   │   ├── models/                    # MongoDB models
│   │   │   ├── Baby.js
│   │   │   ├── Measurement.js
│   │   │   ├── HealthRecord.js
│   │   │   ├── Medication.js
│   │   │   └── AIInsight.js
│   │   ├── routes/                    # API routes
│   │   ├── utils/
│   │   │   └── calculations.js        # BMI, percentiles
│   │   ├── server.js
│   │   ├── package.json
│   │   └── README.md
│   │
│   ├── peditrack-nutrition-share-feed-service/  # Nutrition & Social
│   ├── peditrack-risk-assessment-service/       # Risk Assessment
│   └── places-proxy/                            # Location services
│
├── 🎨 peditrackadmin/                 # Web Admin Dashboard (React + Vite)
│   ├── src/
│   ├── package.json
│   └── README.md
│
├── 📄 Documentation
│   ├── Integrated Predictive Intelligence Tool for Pediatric Health.pdf
│   └── IT4010-TAF-2025 July Batch - 25-26J-442.pdf
│
└── README.md                          # This file
```

---

## 🛠️ Technology Stack

### **Mobile Application**
- **Framework**: React Native with Expo (v51.0.0)
- **Language**: TypeScript
- **Navigation**: Expo Router
- **UI Components**: Custom components with React Native SVG
- **State Management**: React Hooks + AsyncStorage
- **Voice Processing**: @react-native-voice/voice
- **Media**: expo-av, expo-image-picker

### **Backend Services**

#### Chat Service (Node.js)
- **Runtime**: Node.js
- **Framework**: Express.js
- **LLM Integration**: LangChain
- **Providers**: OpenAI, Google Gemini, Anthropic Claude
- **Vision AI**: GPT-4o-mini (cost-optimized)
- **File Upload**: Multer

#### RAG Service (Python)
- **Framework**: FastAPI + Uvicorn
- **Embeddings**: sentence-transformers (all-MiniLM-L6-v2)
- **Vector Store**: FAISS (24,855 pediatric documents)
- **Datasets**: HuggingFace Datasets
- **ML Libraries**: NumPy, scikit-learn
- **Visualization**: Matplotlib, Seaborn

#### Health Analytics Service (Node.js)
- **Database**: MongoDB + Mongoose
- **Features**: Growth tracking, BMI calculation, predictive insights
- **Analytics**: Growth velocity, percentile calculations

### **AI/ML Technologies**
- **Large Language Models**: GPT-3.5/4, Gemini, Claude
- **Speech Recognition**: Whisper (OpenAI)
- **Embeddings**: Sentence Transformers
- **Vector Search**: FAISS
- **NLP**: LangChain, Transformers

### **Data Sources**
- **HealthCareMagic Dataset**: 24,855 pediatric Q&A pairs
- **Medical Dialogues**: MedDialog, MediTOD
- **WHO Growth Standards**: Child growth references

---


## 🧩 Components

### 1. AI-Driven Predictive Health Analytics

**Location**: `services/health-analytics-service`

**Features**:
- Baby profile management
- Growth tracking (height, weight, head circumference)
- Automatic BMI calculation
- Health records and medication tracking
- AI-powered growth predictions
- Percentile calculations and trend analysis

**API Endpoints**:
```
POST   /api/babies                          # Create baby profile
GET    /api/babies/:id                      # Get baby details
POST   /api/measurements                    # Add measurement
GET    /api/measurements/baby/:id/analytics # Get predictions
POST   /api/ai-insights/generate/:babyId    # Generate AI insights
```

**Documentation**: [Health Analytics README](services/health-analytics-service/README.md)

---

### 2. ML-Driven Personalized Nutrition Optimization

**Location**: `peditrackv2/src/screens/Nutrition`

**Features**:
- Personalized meal planning
- Food image recognition and nutritional analysis
- Community feed for sharing recipes and tips
- Dietary preference and allergy management
- Behavioral eating pattern analysis

**Technologies**:
- Collaborative filtering for recommendations
- NLP for recipe parsing
- Computer vision for food recognition

---

### 3. Real-Time Emergency Response Integration

**Location**: `peditrackv2/src/screens/RiskAssessment`

**Features**:
- Real-time risk assessment
- Emergency contact management
- Live teleconsultation
- Dynamic hospital routing
- Predictive alerts for critical conditions

**Integration**:
- Google Maps API for location services
- Twilio for video consultations
- WebRTC for real-time communication

---

### 4. Voice-Activated Multilingual Conversational AI

**Location**: `services/peditrack-chat-service` + `peditrackv2/src/screens/ConversationalAI`

**Features**:
- **Multi-Provider LLM Support**: OpenAI, Gemini, Claude
- **Vision AI**: Image analysis with GPT-4o-mini
- **Voice Input**: Speech-to-text with Whisper
- **RAG Integration**: 24,855 pediatric medical documents
- **Conversation History**: Persistent chat storage
- **Multilingual Support**: Translation and localization

**RAG Knowledge Base**:
- ✅ Symptoms & Diagnosis
- ✅ Treatment & Care
- ✅ Development Milestones
- ✅ Infant Care & Feeding
- ✅ Vaccinations

**API Endpoints**:
```
POST   /api/chat/message                    # Send text message
POST   /api/chat/message-with-image         # Send image with text
POST   /api/chat/voice                      # Voice input
GET    /api/rag/retrieve                    # Retrieve medical context
GET    /api/rag/stats                       # RAG system statistics
```

**Documentation**: 
- [Chat Service Quick Start](services/peditrack-chat-service/QUICK_START.md)
- [RAG Service README](services/peditrack-rag-service/README.md)

---


## 🔬 Research Background

### Research Problem

Pediatric healthcare systems globally face significant challenges:

1. **Fragmentation of Data**: Health data across anthropometry, behavior, nutrition, and environment are analyzed in silos
2. **Adult-Centric Systems**: Current EHRs lack pediatric-specific prediction models
3. **Static Recommendations**: Nutrition tools don't adapt to evolving needs
4. **Reactive Emergency Care**: Lack of predictive models for critical conditions
5. **Accessibility Barriers**: Language and literacy barriers prevent effective use

### Research Objectives

This research aims to develop a unified AI-powered system that:

- Integrates multi-domain pediatric health data
- Enables early prediction of developmental delays, malnutrition, ADHD, and autism
- Provides personalized, adaptive nutrition recommendations
- Supports real-time emergency response with predictive analytics
- Ensures inclusive access through multilingual voice interfaces

### Key Technologies

- **Recurrent Neural Networks** for clinical event prediction [1]
- **Deep Learning with EHRs** for scalable health analytics [2]
- **Matrix Factorization** for personalized recommendations [4]
- **Speech Recognition** via large-scale weak supervision [7]
- **Multilingual NLP** for translation and accessibility [8]

### References

[1] E. Choi et al., "Doctor AI: Predicting clinical events via recurrent neural networks," arXiv:1511.05942, 2016.

[2] A. Rajkomar et al., "Scalable and accurate deep learning with electronic health records," npj Digital Medicine, vol. 1, no. 1, pp. 1–10, 2018.

[3] M. Aczon et al., "Predictive modeling in pediatric critical care using recurrent neural networks," Critical Care Medicine, vol. 49, no. 7, pp. 1123–1131, 2021.

[4] Y. Koren, "Matrix factorization techniques for recommender systems," Computer, vol. 42, no. 8, pp. 30–37, 2009.

[5] World Health Organization, "WHO Child Growth Standards," 2006.

[6] X. Li et al., "Real-time risk prediction in emergency departments using EHR data," BMC Medical Informatics and Decision Making, vol. 20, 2020.

[7] A. Radford et al., "Whisper: Robust speech recognition via large-scale weak supervision," OpenAI, 2022.

[8] Y. Liu et al., "Multilingual denoising pre-training for neural machine translation," 2020.

---




## 👥 Team

**Project ID**: 25-26J-442  
**Research Cluster**: CoEAI - Centre of Excellence for AI  
**Specialization**: Software Engineering (SE)  
**Institution**: IT4010 Research Project - 2025 July Batch

---



