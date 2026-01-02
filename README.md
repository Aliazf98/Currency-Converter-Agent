text
# Currency Converter AI Agent

[![ADK](https://img.shields.io/badge/ADK-Agent-blue)](https://google.github.io/adk-docs/)
[![Gemini](https://img.shields.io/badge/Powered-Gemini-orange)](https://aistudio.google.com/)
[![Live Rates](https://img.shields.io/badge/Live-Frankfurter-green)](https://frankfurter.app/)

This repository contains an **ADK AI Agent** for currency conversion using Google's Agent Development Kit (ADK). The agent fetches **live exchange rates** from the Frankfurter API, calculates **transaction fees** for common currency pairs (USD, EUR, GBP, TRY, CAD, AUD), and provides formatted conversion summaries with fee deductions.

The Jupyter notebook implements a specialized LLM agent powered by **Gemini models**, custom tools for fees and rates (with 1-hour caching), and a calculation sub-agent for precise math.
