# Currency Converter AI Agent

[![ADK](https://img.shields.io/badge/ADK-Agent-blue)](https://google.github.io/adk-docs/)
[![Gemini](https://img.shields.io/badge/Powered-Gemini-orange)](https://aistudio.google.com/)
[![Live Rates](https://img.shields.io/badge/Live-Frankfurter-green)](https://frankfurter.app/)

This repository contains an **ADK AI Agent** for currency conversion using Google's Agent Development Kit (ADK). The agent fetches **live exchange rates** from the Frankfurter API, calculates **transaction fees** for common currency pairs (USD, EUR, GBP, TRY, CAD, AUD), and provides formatted conversion summaries with fee deductions.

The Jupyter notebook implements a specialized LLM agent powered by **Gemini models**, custom tools for fees and rates (with 1-hour caching), and a calculation sub-agent for precise math.

## Features

- **Live exchange rates** via Frankfurter API with 1-hour caching
- **Realistic transaction fees** (percentage + fixed) per currency pair
- **Supported currencies**: USD, EUR, GBP, TRY, CAD, AUD
- **Clean output format**: Original amount, fees, rate, final amount
- **Error handling** for unsupported currencies and API failures
- **Rate limit friendly** with intelligent caching

## Prerequisites

- Python 3.13+ with Jupyter
- Google AI Studio API key (free tier)
- Dependencies: `google-adk`, `google-generativeai`, `requests`, `python-dotenv`

## Quick Start

```bash
# Clone the repository
git clone https://github.com/Aliazf98/Currency-Converter-Agent.git
cd Currency-Converter-Agent

# Create virtual environment (recommended)
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt  # Or manually: pip install google-adk google-generativeai requests python-dotenv jupyter

# Create .env file with your API key
cp .env.example .env
# Edit .env file (see API Key section below)

# Launch Jupyter
jupyter notebook currency-converter-agent.ipynb
```
