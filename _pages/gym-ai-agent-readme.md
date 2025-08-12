---
layout: single
title: "Gym AI Agent – README / Developer Guide"
permalink: /gym-ai-agent/readme/
author_profile: false
---

# 🏋️‍♂️ Gym AI Agent

**AI-powered personal trainer** that creates custom workout and nutrition plans based on user goals, preferences, and progress.  
Built with **Falcon 7B Instruct**, **RAG architecture**, and a modern web UI.


# 🚀 Features
- Personalized workout plans – automatically generated based on fitness goals
- Nutrition advice – calorie and macronutrient calculation
- Document-based knowledge base – thousands of fitness and nutrition documents indexed
- Fast and responsive UI – powered by Next.js + Tailwind CSS + shadcn/ui
- Low-latency backend – Python + FastAPI + OpenAI API

# 🛠️ Tech Stack
- LLM: Falcon 7B Instruct (quantized, local inference)
- RAG: ChromaDB + text-embedding-3-small
- Frontend: Next.js 15, Tailwind CSS, shadcn/ui
- Backend: FastAPI, Python 3.11
- Deployment: Local GPU (RTX 4080 SUPER) or cloud

# 📦 Installation & Run locally

## Clone repository
git clone https://github.com/<your-user>/gym-ai-agent.git
cd gym-ai-agent

## Create and activate environment
conda create -n gym-agent python=3.11
conda activate gym-agent

## Install dependencies
pip install -r requirements.txt

## Start backend
uvicorn app.main:app --host 0.0.0.0 --port 8000

## Start frontend
cd frontend
npm install
npm run dev

# 📸 Screenshots
(Add screenshots of the UI and workflow here.)

# 📄 License
MIT License – See LICENSE file.
