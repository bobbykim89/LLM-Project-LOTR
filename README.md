# MiddleEarthChat

## Problem Statement

J.R.R. Tolkien's Middle-earth features hundreds of characters with similar-sounding names (Glorfindel, Gildor, Glóin; Celeborn, Celebrían, Celebrimbor), making it easy to lose track of who's who. As a Tolkien fan, I found myself constantly confused by these names while reading, and looking them up in wikis or books disrupted the reading experience.

**MiddleEarthChat** solves this by providing instant, conversational answers about Middle-earth characters—letting you stay immersed in the story.

## Project Description

A Retrieval-Augmented Generation (RAG) system that answers questions about characters from *The Lord of the Rings*, *The Hobbit*, *The Silmarillion*, and related works. Ask naturally ("Who is Glorfindel?" or "What's the difference between Celeborn and Celebrimbor?") and get accurate, context-aware responses.

### Tech Stack

**AI/ML:**
- Vector Database: Qdrant
- Embeddings: Jina-embeddings-v4
- LLM: GPT-4o-mini
- Evaluation: LLM-as-Judge (GPT-4o-mini & Claude)

**Backend:**
- Django REST Framework
- Neon Postgres (serverless)
- Deployed on Vercel

**Frontend:**
- Nuxt 4 (Vue.js 3)
- Tailwind CSS
- Deployed on Vercel

### Key Features

- **Semantic Search**: Find characters even with partial or fuzzy queries
- **Grounded Answers**: RAG ensures responses are based on actual character data
- **Fast & Scalable**: Serverless architecture for quick responses
- **Rigorously Evaluated**: Comprehensive testing for retrieval and generation quality

### Use Cases

- Quick character lookups while reading
- Distinguishing between similarly-named characters

## Live Demo

🌐 **Try it now**: [MiddleEarthChat](https://middleearth-chat.vercel.app/)

## Project Repositories

This is the main repository that provides an overview of the MiddleEarthChat project. The implementation is split across three specialized repositories:

### 1. 🔍 RAG & Evaluation
**Repository**: [lotr-characters](https://github.com/bobbykim89/lotr-characters)
**Commit ID**: 0b5f316

Contains the core RAG implementation, Qdrant setup, and comprehensive evaluation frameworks:
- Data scraping and preprocessing
- Qdrant vector database setup
- Embedding generation with Jina-embeddings-v4
- Retrieval evaluation metrics
- RAG evaluation using LLM-as-Judge methodology
- Docker containerization

> Note: A cron job runs every 3 days to perform health checks on the Qdrant Cloud collection, ensuring consistent availability and performance.

### 2. 🚀 Backend API
**Repository**: [lotr-characters-api](https://github.com/bobbykim89/lotr-characters-api)
**Commit ID**: 3ffd02d

Django REST Framework backend deployed on Vercel

### 3. 💬 Web Application
**Repository**: [middleearth-chat](https://github.com/bobbykim89/middleearth-chat)
**Commit ID**: 9fca88c

Modern, responsive chat interface built with Nuxt 4
