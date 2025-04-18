# 🧪 Scrivere il primo test con DeepEval

## 🎯 Obiettivo della lezione
In questa sezione impariamo a:
- Impostare l'**API Key di OpenAI**
- Caricarla via `export` o da file `.env`
- Eseguire un primo test con **DeepEval** per valutare la *rilevanza della risposta* (Answer Relevance)
- Comprendere come DeepEval utilizza un LLM per confrontare *expected vs actual output*

---

## 🧩 1. Perché usare l'API di OpenAI?
Anche se nel corso useremo modelli locali (es. con Ollama), **in contesti aziendali** può essere necessario valutare le LLM via API come GPT-4.

Quindi, partiamo mostrando come usare **l’API di OpenAI** per i test iniziali.

---

## 🔐 2. Impostare l'API Key

### Metodo 1: via terminale
```bash
export OPENAI_API_KEY="sk-xxxxx..."
```

### Metodo 2: via file `.env`
1. Crea un file `.env`:
   ```
   OPENAI_API_KEY=sk-xxxxx...
   ```
2. In Python:
   ```python
   from dotenv import load_dotenv
   load_dotenv('.env')
   ```

---

## 📦 3. Preparazione ambiente di test

Crea un file `.ipynb` o `.py` per il test.

Nel notebook:
- Inserisci un blocco *Markdown* con il titolo del test
- Usa il codice per caricare la `.env`
- Scrivi il test con DeepEval (vedi sotto)

---

## 🧪 4. Primo test con DeepEval – *Answer Relevance*

```python
from deepeval.metrics.answer_relevancy import AnswerRelevancyMetric
from deepeval.test_case import LLMTestCase

# Definizione del test case
test_case = LLMTestCase(
    input="Who is the current president of United States of America?",
    actual_output="Joe Biden",
    retrieval_context=["Joe Biden serves as the current president of America"]
)

# Esecuzione della metrica Answer Relevance
metric = AnswerRelevancyMetric()
metric.measure(test_case)

# Stampa del risultato
print(metric.score)
```

---

## 🔍 Spiegazione del codice

| Blocco | Funzione |
|--------|----------|
| `LLMTestCase` | Definisce un singolo test case con input, output, contesto e risposta attesa |
| `AnswerRelevancyMetric()` | Metrica che confronta `actual_output` con `retrieval_context` |
| `measure()` | Esegue il test chiamando GPT-4 tramite l'API OpenAI |
| `metric_score` | Restituisce uno score tra `0` e `1` (dove `1` è perfetta rilevanza) |

---

## 🧪 Esecuzione in terminale
Crea un file `test.py` con lo stesso codice e lancia:
```bash
python3 test.py
```

---

## 🧾 Esempi di esito

### ✅ Test Superato (score: 1.0)
```python
actual_output = "Joe Biden is the current president of the United States."
retrieval_context = "Joe Biden serves as the current president of America."
# Score = 1.0
```

### ❌ Test Fallito (score: 0.0)
```python
actual_output = "Donald Trump is the president of the United States."
retrieval_context = "Joe Biden serves as the current president of America."
# Score = 0.0
```

---

## 📌 Conclusione

Abbiamo:
- Eseguito il primo test automatico con **DeepEval**
- Capito il funzionamento della metrica *Answer Relevance*
- Utilizzato OpenAI API come LLM di valutazione
- Preparato il terreno per test più avanzati

---

## ⏭️ Prossimi passi

Nella **prossima lezione**, analizzeremo in dettaglio il codice, ogni parametro del `LLMTestCase`, le metriche disponibili e come scrivere test multipli per valutare un'applicazione LLM in modo strutturato.
