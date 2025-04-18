# ✅ DeepEval - Uso della metrica **Contextual Precision**

## 🔁 Riepilogo lezione precedente
Nella lezione precedente abbiamo scritto e testato il primo codice con la metrica **Answer Relevancy**, ottenendo un punteggio di `1.0`, che indicava un'alta coerenza tra risposta attesa e risposta generata.

## 🧠 Obiettivo di questa lezione
Apprendere come utilizzare la metrica **Contextual Precision** in DeepEval per testare la coerenza tra:
- il **contesto di recupero** fornito (ad esempio da un sistema RAG)
- la **risposta generata**
- e un'**output atteso**

## 📦 Metriche disponibili in DeepEval
Oltre ad `AnswerRelevancy`, DeepEval supporta numerose metriche tra cui:
- `ContextualPrecisionMetric`
- `AnswerFaithfulnessMetric`
- `MultimodalFaithfulnessMetric`
- `KnowledgeRetentionMetric`
- `ConversationRelevancyMetric`
- `ImageEditingMetric`
- e molte altre.

## 🧰 Setup iniziale
Assicurati di avere già installato:
- DeepEval (`pip install -U deepeval`)
- Jupyter extension su VS Code
- OpenAI API key caricata tramite variabile d’ambiente o `.env`

## 📄 Codice per testare la **Contextual Precision Metric**

```python
# Import delle classi necessarie da deepeval
from deepeval.test_case import LLMTestCase
from deepeval.metrics import ContextualPrecisionMetric

# Istanziazione della metrica
contextual_precision = ContextualPrecisionMetric()

# Creazione del test case
test_case = LLMTestCase(
    input="Who is the current president of USA in 2024?",
    # Should come from an LLM or from an Agent or RAG
    actual_output="Donald Trump",
    # RAG - Vector DB, AI Agent - Agent Tools Call, LLM - LLM invoke response
    retrieval_context=["Donald Trump serves as the current president of America."],
    expected_output="Donald Trump is the current president of America"
)

# Esecuzione del test con la metrica
contextual_precision.measure(test_case)

# Output dei risultati
print("✅ Score:", contextual_precision.score)
print("✅ Success:", contextual_precision.success)
print("✅ Score Breakdown:", contextual_precision.score_breakdown)
```

## ⚠️ Possibile errore: `MissingTestCaseParameterError`
Se dimentichi di fornire l'`expected_output`, otterrai un errore:

```
MissingTestCaseParameterError: Expected output cannot be None for ContextualPrecisionMetric
```

💡 Questo accade perché **alcune metriche richiedono campi obbligatori** nel `LLMTestCase`. Verifica sempre i parametri richiesti.

## 🧪 Esecuzione del test
Quando tutto è corretto, l’output sarà:

```plaintext
✅ Score: 1.0
✅ Success: True
✅ Score Breakdown: None
```

Significa che la risposta fornita è perfettamente coerente con il contesto fornito.

## 🧭 Confronto con casi reali
In uno scenario reale:
- `actual_output` dovrebbe essere generato da un LLM o agente
- `retrieval_context` dovrebbe provenire da un database vettoriale (es. Chroma, Weaviate)
- `expected_output` dovrebbe derivare da golden dataset o annotazioni umane

Per ora abbiamo usato valori **hard-coded** per semplificare l'apprendimento.

## 📌 Conclusione
- Abbiamo appreso come scrivere test con la **Contextual Precision Metric**
- Abbiamo gestito un errore comune (campo mancante)
- Abbiamo visto come leggere i risultati di un test

## 🔜 Prossimo passo
Nella prossima lezione vedremo **come salvare questi test nel cloud** di DeepEval (Confident AI) per poterli visualizzare su dashboard con grafici, storici e visualizzazioni avanzate.
