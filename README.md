# LLM Evaluation

A comprehensive framework for evaluating Large Language Model (LLM) applications using LangSmith and LangChain. This project demonstrates best practices for evaluating both simple chatbots and Retrieval-Augmented Generation (RAG) systems.

## Overview

This project provides tools and examples for:
- Creating evaluation datasets with LangSmith
- Implementing custom evaluators using LLM-as-a-Judge patterns
- Evaluating chatbot responses for correctness and conciseness
- Evaluating RAG systems across multiple dimensions (correctness, relevance, groundedness, retrieval quality)
- Tracking experiments and comparing model performance

## Features

### Simple Chatbot Evaluation
- **Correctness Evaluation**: Uses GPT-4o-mini as a judge to assess factual accuracy
- **Conciseness Evaluation**: Checks if responses are appropriately brief
- **Dataset Management**: Create and manage evaluation datasets in LangSmith

### RAG System Evaluation
- **Correctness**: Grades answers against ground truth using structured output
- **Relevance**: Evaluates if the response addresses the user's question
- **Groundedness**: Checks if responses are justified by retrieved documents
- **Retrieval Relevance**: Assesses quality of document retrieval

## Prerequisites

- Python >= 3.12
- OpenAI API key
- LangSmith API key

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd llm-evaluation
```

2. Install dependencies using `uv`:
```bash
uv sync
```

3. Set up environment variables:
Create a `.env` file in the project root:
```env
OPENAI_API_KEY=your_openai_api_key
LANGSMITH_API_KEY=your_langsmith_api_key
```

## Dependencies

- **LangChain**: Framework for building LLM applications
- **LangSmith**: Platform for observing and evaluating LLM applications
- **OpenAI**: LLM provider
- **ChromaDB & FAISS**: Vector databases for RAG
- **Sentence Transformers**: Embedding models
- **BeautifulSoup4**: Web scraping and parsing
- **PyPDF**: PDF document processing
- **Pandas**: Data analysis and results visualization

## Usage

### Running the Jupyter Notebook

The main evaluation workflows are demonstrated in `llm-eval.ipynb`:

```bash
jupyter notebook llm-eval.ipynb
```

## Evaluation Metrics

### Chatbot Metrics
- **Correctness**: Binary evaluation using LLM-as-a-Judge
- **Conciseness**: Length-based metric (response < 2x expected length)

### RAG Metrics
- **Correctness**: Structured evaluation comparing against ground truth
- **Relevance**: Assesses if response addresses the question
- **Groundedness**: Verifies response is supported by retrieved documents
- **Retrieval Relevance**: Evaluates quality of document retrieval

## Project Structure

```
llm-evaluation/
├── main.py                 # Main application entry point
├── llm-eval.ipynb         # Jupyter notebook with evaluation examples
├── pyproject.toml         # Project dependencies and metadata
├── .env                   # Environment variables (not tracked)
├── .gitignore            # Git ignore rules
└── README.md             # This file
```

## Evaluation Workflow

1. **Create Dataset**: Define inputs and expected outputs
2. **Define Evaluators**: Implement custom evaluation functions
3. **Run Experiments**: Execute evaluations with LangSmith
4. **Analyze Results**: Review metrics and compare experiments
5. **Iterate**: Refine prompts, models, or retrieval strategies

## Best Practices

- Use structured outputs for consistent LLM-as-a-Judge evaluations
- Include explanations in evaluation schemas to improve reasoning
- Test multiple evaluation metrics to get comprehensive insights
- Track experiments with meaningful prefixes and metadata
- Compare results across different model versions and configurations

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

