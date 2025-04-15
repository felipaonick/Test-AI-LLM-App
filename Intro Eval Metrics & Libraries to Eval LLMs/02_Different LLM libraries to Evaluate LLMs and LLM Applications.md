# 🧪 Librerie di Valutazione per LLM – Appunti Dettagliati

> 📚 Lezione dedicata agli strumenti principali per **valutare** applicazioni basate su **Large Language Models (LLM)**.  
> 🗓️ Data generazione: 2025-04-15

---

## 📌 Introduzione

Valutare le performance di un'applicazione LLM richiede strumenti affidabili. In questa lezione vengono presentate le **5 principali librerie di valutazione** attualmente più usate:

1. **OpenAI Evals**
2. **Ragas**
3. **DeepEval**
4. **Galileo**
5. **HuggingFace Evaluate**

Queste librerie differiscono per funzioni, compatibilità con modelli, integrazioni e osservabilità.

---

## 🧭 Panoramica delle librerie

### 1. 🔬 OpenAI Evals

- **Descrizione**: framework sviluppato da OpenAI per valutare sistemi costruiti su modelli OpenAI.
- **Caratteristiche**:
  - Ampio **registry** di test predefiniti.
  - Supporto alla **creazione di Eval personalizzati**.
- **Modelli compatibili**: principalmente GPT-4, GPT-4-turbo, GPT-3.5.
- **Limitazioni**: poco utile con modelli non-OpenAI.

---

### 2. 📦 Ragas (`ragas.io`)

- **Descrizione**: libreria open-source per la valutazione di applicazioni LLM, con focus su sistemi **RAG**.
- **Punti di forza**:
  - Supporta metodi **state-of-the-art** (SOTA) per valutazioni automatiche.
  - Valutazione anche **senza dataset etichettati**.
  - Supporto per framework come **LlamaIndex**.
  - Offre un’interfaccia per **monitoraggio online** e **generazione dati sintetici**.
- **Richiede**: API key per usare la piattaforma online.

---

### 3. 🧪 DeepEval (`confident-ai.com`)

- **Descrizione**: framework open-source pensato per valutare facilmente le performance degli LLM.
- **Obiettivi**:
  - Costruzione, test e monitoraggio delle applicazioni AI.
  - Offre un'interfaccia visuale con **grafici e metriche**.
- **Caratteristiche**:
  - Supporta metodi recenti come hallucination detection, RAG, relevance.
  - Possibilità di unit testing per LLM in stile Python.
- **Utilizzo**: semplice da integrare in pipeline esistenti.

---

### 4. 👁️‍🗨️ Galileo (`galileo-ai.com`)

- **Descrizione**: piattaforma di osservabilità avanzata per applicazioni GenAI.
- **Caratteristiche**:
  - Dashboard stile **LangSmith** per monitorare le invocazioni, chiamate a tool, etc.
  - Categorie:
    - **Evaluate**: per testare la qualità delle risposte.
    - **Observe**: per monitorare l’esecuzione e analizzare comportamenti.
    - **Protect**: per aggiungere **guardrails** contro allucinazioni o output indesiderati.
  - Sistema di **alert e protezione** per filtrare risposte non sicure.

---

### 5. 🤗 HuggingFace Evaluate

- **Menzionata brevemente**: presente tra le principali, anche se non dettagliata nella lezione.
- **Ruolo**: utile per metriche standard (BLEU, ROUGE, F1, etc.) più che per valutazioni avanzate su modelli generativi complessi.

---

## 🧩 Differenze principali tra le librerie

| Caratteristica               | OpenAI Evals | Ragas       | DeepEval    | Galileo     |
|-----------------------------|--------------|-------------|-------------|-------------|
| ✅ Open-source              | ❌           | ✅           | ✅           | ❌           |
| 🧠 Supporto modelli diversi | ❌ (solo OpenAI) | ✅         | ✅           | ✅           |
| 📊 Dashboard visuale        | ❌           | ✅ (web)     | ✅           | ✅           |
| 🔍 Hallucination detection  | ✅           | ✅           | ✅           | ✅ (con alert) |
| 🔐 Guardrails               | ❌           | ❌           | ❌           | ✅           |
| 🧪 Dataset-free eval        | ❌           | ✅           | ✅           | ❌           |

---

## 📚 Considerazioni finali

- La scelta della libreria dipende da:
  - **Tipo di modello** usato (es. GPT vs open-source)
  - **Obiettivo della valutazione** (hallucinations, relevance, RAG)
  - **Budget/Stack aziendale** (Galileo più orientato enterprise)

- **Ragas** e **DeepEval** risultano essere le scelte migliori per chi desidera **monitoraggio, valutazione automatica e open-source**.

- **Galileo** è eccellente per team enterprise che necessitano di **osservabilità avanzata e protezioni integrate**.

