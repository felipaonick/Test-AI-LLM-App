# 📊 Evaluation Metrics per LLM 

> Lezione dedicata alla comprensione delle **metriche di valutazione (evaluation metrics)** nei sistemi basati su modelli linguistici di grandi dimensioni (LLM).  
> 📅 Data: 2025-04-15

---

## 📌 Introduzione

Le **metriche di valutazione** sono strumenti fondamentali per misurare le prestazioni di un LLM o di un'applicazione costruita su di esso, soprattutto nel contesto di:
- RAG (Retrieval-Augmented Generation)
- Tool-augmented LLMs (funzioni e agenti)
- Chatbot conversazionali

---

## 🧩 Metriche più comuni

### 1. ✅ Answer Relevance
- **Definizione**: misura quanto la risposta del modello è pertinente alla query dell’utente.
- **Applicazione**: valida sia su modelli LLM base che su applicazioni AI.
- **Obiettivo**: garantire che la risposta rifletta davvero l’intento dell’utente.

---

### 2. 🔄 Contextual Relevancy and Contextual Precision
#### a. Contextual Relevancy
- **Definizione**: verifica se la risposta si allinea al contesto recuperato (es. in un sistema RAG).
- **Domanda chiave**: la risposta usa correttamente il contesto fornito?

#### b. Contextual Precision
- **Definizione**: misura quanto è preciso il contesto recuperato.
- **Domanda chiave**: il contesto è rilevante rispetto alla query?

📌 *Differenza*: una valuta **la qualità della risposta rispetto al contesto**, l’altra valuta **la qualità del contesto stesso**.

---

### 3. 🧰 Tool Selection Accuracy
- **Definizione**: valuta la capacità del LLM di selezionare il giusto tool da eseguire per una determinata richiesta.
- **Contesto**: cruciale in sistemi con decine o centinaia di strumenti.
- **Esempio**: distinguere quando usare un tool di invio email o di interrogazione database.

---

### 4. ⚖️ Bias Detection
- **Definizione**: identifica eventuali bias nei contenuti generati.
- **Esempio**: se alla domanda “I ragazzi prendono voti più alti delle ragazze?” il modello risponde “Sì”, allora è presente un bias.
- **Importanza**: i bias riflettono pregiudizi nei dati di addestramento.

---

### 5. 🧮 Function Argument Accuracy
- **Definizione**: verifica la correttezza degli argomenti passati da un LLM a una funzione o API.
- **Applicazione**: fondamentale quando l’LLM interagisce con tool e funzioni esterne.
- **Effetti**: un argomento errato può causare il fallimento della chiamata e risposte nulle o sbagliate.

---

## 🧠 Altre metriche citate (in base agli strumenti usati)

- **Faithfulness**: la risposta è supportata dal contesto?
- **Hallucination Detection**: presenza di informazioni inventate.
- **Completeness**: la risposta è esaustiva?
- **Context Recall**: quanto contesto rilevante è stato effettivamente utilizzato?
- **Function Call Accuracy**: la funzione invocata è quella corretta?

---

## 🛠️ Nota sugli strumenti

Non tutti gli strumenti di valutazione supportano tutte le metriche.  
Alcuni hanno funzioni avanzate come **hallucination detection**, altri no.

---

## ✅ Conclusione

Queste metriche:
- Consentono di valutare in profondità **l'affidabilità, l'efficacia e la correttezza** di un LLM o del sistema che lo utilizza.
- Sono essenziali per il debugging, il miglioramento continuo e l’auditabilità delle risposte AI.

