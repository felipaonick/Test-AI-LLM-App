## 🧪 Valutazione con DeepEval e Pubblicazione su Confident AI

### 📌 Obiettivo della lezione
In questa lezione impareremo a:
- Salvare i test eseguiti con DeepEval in una struttura chiamata `EvaluationDataset`.
- Valutare più test in modo centralizzato.
- Pubblicare i risultati su **Confident AI** (piattaforma cloud di monitoraggio ed analisi).
- Visualizzare i test con metadati, risultati e spiegazioni.

---

## 🗃️ EvaluationDataset: cos'è e come funziona

La classe `EvaluationDataset` di DeepEval consente di:
- Aggregare più test case (oggetti `LMTestCase`) in un unico dataset.
- Valutare in batch una serie di test.
- Inviare i risultati al portale cloud di Confident AI per una visualizzazione completa.

### 🧱 Esempio di creazione
```python
from deepeval.dataset import EvaluationDataset

dataset = EvaluationDataset(test_cases=[test_case])
```
- `test_case` è un oggetto `LMTestCase` precedentemente definito.
- Il dataset può contenere anche più test, es. `[tc1, tc2, tc3]`.

---

## ✅ Metodo `.evaluate()`: esecuzione della valutazione

```python
dataset.evaluate(metrics=[AnswerRelevancyMetric()])
```

### Funzionalità principali:
- Esegue i test su GPT-4 (o altro LLM configurato).
- Stampa i risultati dettagliati nella console (score, soglia, ragione).
- Pubblica automaticamente il test sul portale Confident AI se hai effettuato il login con l’API key.

---

## 📊 Esempio di output console
```
Running DeepEval AnswerRelevancyMetric with GPT-4...
Evaluating 1 test case(s) in parallel.
✔ Metric: Answer Relevancy
   Score: 1.0
   Threshold: 0.5
   Reason: Answer perfectly aligned with the query, providing relevant information.
```

---

## 🌐 Visualizzazione dei risultati su Confident AI

Dopo l’esecuzione:
- Si apre automaticamente il portale Confident AI.
- Mostra tutti i dettagli del test:
  - Prompt di input
  - Output atteso e ottenuto
  - Retrieval context (contesto recuperato)
  - Risultato (pass/fail)
  - Score (es. 1.0)
- Supporta la **comparazione tra test run** successivi.

---

## 💡 Vantaggi dell'approccio con EvaluationDataset

| Vantaggio                         | Descrizione                                                                 |
|----------------------------------|-----------------------------------------------------------------------------|
| 📦 Aggregazione                  | Puoi eseguire e tracciare più test insieme.                                |
| 📊 Dashboard intuitiva           | Visualizzi e confronti i risultati nel cloud Confident AI.                 |
| 🔁 Storico test                  | Ogni test è tracciato con timestamp e metadati.                            |
| 📉 Riduzione del rumore          | Ottieni anche ragioni, score breakdown, dettagli per debugging.            |
| 💸 Cost awareness                | Visualizzi il costo stimato delle chiamate API (es. su GPT-4).             |

---

## 🚨 Nota sui costi

L’uso di modelli come **GPT-4 via API** comporta costi elevati. Per questo motivo:
- È preferibile **eseguire i test in locale** con LLM ospitati su Ollama.
- Le prossime lezioni mostreranno **come evitare l'uso di OpenAI API**.

---

## 📍Prossimi step

Nelle prossime lezioni vedremo:
- Come eseguire i test in locale con Ollama e modelli open-source.
- Come evitare costi eccessivi mantenendo tracciabilità su Confident AI.
- Come sfruttare al massimo la dashboard per valutazioni continue e regression test.

