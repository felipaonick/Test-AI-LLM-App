# Uderstand Evaluation LLM Metrics


## LLM Evaluation

- Testing/Evaluating an LLM is not as straightforward as testing a usual software. Evaluating an LLM is always challenging whether we are:

    1. Building an LLM application
    2. Building an AI Agent
    3. Fine-Tuning an LLM with large dataset

- Evaluating these requires set of metrics instead of unit/integration or regression testing them

## Statistic Evaluation

- BLEU (Bilingual Evaluation Uderstudy)
- ROUGE (Recall-Oriented Uderstudy for Gisting Evaluation)
- METEOR (Metric for Evaluation of Translation with Explicit ORdering)

These metrics are typically used when we Fine-tuning a LLM, using HuggingFace libraries.

But in this course we don't cover these metrics beacuse we won't fine-tune a LLM.

## LLM Metrics

Some of the common metrics are:

1. **Answer Relevancy**: Determines whether an LLM output is able to address the given input in an informative ans concise manner.

2. **Prompt Alignment**: Determines whether an LLM output is able to follow instructions from your prompt template.

3. **Correctness**: Determines whether an LLM output is factually correct based on some ground truth.

4. **Hallucination**: Determines whether an LLM output contains fake or made-up information.

5. **Contextual Relevancy**: Determines whether the retriever in a RAG-based LLM system is able to extract the most relevant information for your LLM as context.






