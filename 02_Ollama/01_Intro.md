# 🧠 Eseguire un LLM in locale con Ollama – Appunti Dettagliati

> Lezione del: 15/04/2025
---

## 🚀 Obiettivo della sezione

- Imparare a **eseguire localmente modelli LLM** (Large Language Models) usando [**Ollama**](https://ollama.com).
- Ridurre i costi evitando l’utilizzo di API commerciali come OpenAI, Claude o Gemini.
- Consentire test e sviluppo **offline e gratuiti**, direttamente su Mac, Linux o Windows.

---

## 🌐 Cos'è Ollama?

- Ollama è un'applicazione multipiattaforma (macOS, Linux, Windows) che permette di:
  - **Eseguire modelli LLM** direttamente sulla propria macchina.
  - Scaricare e utilizzare facilmente modelli open-source per chat, RAG, agenti, embedding, visione, ecc.
- Non è necessaria alcuna registrazione o API key.
- Alternativa gratuita a soluzioni a pagamento come OpenAI API.

---

## 💸 Confronto con le API commerciali

| **Servizio**         | **Metodo**         | **Costo stimato (GPT-4, Claude, Gemini)** |
|----------------------|--------------------|-------------------------------------------|
| OpenAI API           | cloud, a pagamento | ~30$/milione token input, 60$/milione output |
| Ollama               | locale, gratuito   | 0€, richiede solo spazio su disco e risorse locali |

---

## 🖥️ Installazione di Ollama

1. **Vai su** [ollama.com](https://ollama.com)
2. Clicca su **Download**
3. Seleziona il tuo sistema operativo:
   - macOS (supportato nativamente)
   - Linux
   - Windows (disponibile)
4. Installa l'applicazione seguendo la guida della piattaforma.

⚠️ **Nota**: È raccomandato completare l'installazione **prima della prossima lezione**, dove useremo Ollama per test locali.

---

## 🧠 Selezione del modello

Dalla sezione *Models* del sito, Ollama offre l’accesso ai modelli LLM più popolari, come:

| **Modello**           | **Parametri** | **Tipo**           | **Note**                               |
|-----------------------|---------------|--------------------|----------------------------------------|
| `llama3:8b`, `llama3:70b` | 8B, 70B     | Chat               | Ottimizzati per risposte conversazionali |
| `mistral`              | 7B            | Chat / Agent       | Leggero e veloce                       |
| `qwen2.5`              | 14B           | Tool use           | Supporta tool usage                    |
| `deepseek-coder`       | 33B           | Codice             | Ottimizzato per completamento codice  |
| `phi-2`, `gemma`, ecc. | Vari          | Embedded / Vision  | Alcuni specifici per embedding o visione |

### ✅ Selezione avanzata:
- È possibile filtrare per:
  - 🔧 **Tool support**
  - 🧠 **Embedding**
  - 👁️ **Vision**

---

## 💡 Vantaggi dell’utilizzo locale

- **Risparmio economico**: nessun pagamento per token.
- **Velocità di esecuzione**: tutto avviene sulla macchina locale.
- **Flessibilità**: test rapidi di modelli diversi, incluse versioni personalizzate.
- **Privacy e sicurezza**: i dati non lasciano la macchina.

---

## 🧪 Prossimi passi

- Installa Ollama sul tuo sistema operativo.
- Nella prossima lezione vedremo come:
  - Scaricare un modello specifico.
  - Interrogarlo da terminale o tramite script.
  - Integrarlo nella tua app AI per test locali.
