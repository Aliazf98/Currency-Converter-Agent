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
pip install google-adk google-generativeai requests python-dotenv jupyter

# Create .env file with your API key
cp .env.example .env
# Edit .env file (see API Key section below)

# Launch Jupyter
jupyter notebook currency-converter-agent.ipynb
```

## Usage Tutorial

**Open**: `currency-converter-agent.ipynb`

**Run cells top-to-bottom**:

| # | Cell | Action | Success Message |
|---|------|--------|-----------------|
| 1 | **Cell 1** | Imports + `.env` load | `Setup complete. API key loaded` |
| 2 | **Cell 2** | Gemini model config | `Model configuration created` |
| 3 | **Cell 3** | Tools (fees + rates) | `Custom tools created w/ caching` |
| 4 | **Cell 4** | Calculator agent | `Calculation Agent created` |
| 5 | **Cell 5** | Main agent | `Enhanced Currency Agent created` |

### 🚀 Test It!

**Cell 6+** → Copy & Run:

```python
await test_conversion_agent(
    enhancedcurrencyagent,
    "Convert 1000 EUR to TRY with fees",
    "Enhanced Agent"
)
```

## Changing API Key Locally

```bash
# Method 1: Edit .env directly
nano .env
# Update line: GOOGLE_API_KEY=NewAIzaSyKeyHere

# Method 2: Replace via terminal (secure - hidden input)
read -s -p "Enter new API key: " newkey
echo "GOOGLE_API_KEY=$newkey" > .env

# Verify change (shows first 20 chars only)
grep GOOGLE_API_KEY .env | cut -c1-30 '...'

# Method 3: Quick check current key
head -1 .env

# Restart Jupyter: Kernel → Restart → Run Cell 1
```
