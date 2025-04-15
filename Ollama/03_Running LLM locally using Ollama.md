# 🧠 Uso di Modelli LLM Locali con Ollama

> Lezione del: 15/04/2025

### 🖥️ Introduzione
In questa lezione impariamo a:
- Eseguire modelli LLM **localmente** con **Ollama**.
- Scaricare, eseguire e testare modelli di diverse dimensioni.
- Capire le differenze tra modelli piccoli e grandi in termini di accuratezza e performance.
- Utilizzare Ollama via terminale per interagire con i modelli come se fosse ChatGPT.

---

### 🚀 Avvio del terminale e verifica modelli disponibili

1. Si apre il terminale (es. **Hyper** su macOS).
2. Comando base per vedere i modelli installati:

```bash
ollama list
```

3. Il comando mostra tutti i modelli **già scaricati** e pronti per l’uso.

---

### ⬇️ Download e avvio di un modello

Per scaricare un modello, si usa:

```bash
ollama pull nome_modello
```

Per eseguire un modello, si usa:

```bash
ollama run nome_modello
```

💡 **Esempio:** Per scaricare ed eseguire `qwen:1.8b`:

```bash
ollama run qwen:1.8b
```

👉 Ollama scarica il modello (simile a Docker) e lo esegue localmente, aprendo un prompt interattivo tipo ChatGPT.

---

### 🧪 Test con modelli piccoli

Esempio: modello `qwen:1.8b` (1.8 miliardi di parametri):

- Prompt: `"How are you doing?"` → risposta generica corretta.
- Prompt: `"Write Selenium with C# for google.com website."` → **risposta completamente sbagliata**.
  - Motivo: modello troppo piccolo e vecchio (serie `Qwen 1.5` di Alibaba Cloud).
  - Produce codice con `HttpClient` e **non usa nemmeno Selenium**.

---

### 📈 Passaggio a modelli più potenti

Esecuzione del modello `deepseek-r1:8b` (8 miliardi di parametri):

```bash
ollama run deepseek-r1:8b
```

- **Migliore ragionamento e accuratezza**.
- Prompt: `"Write Selenium with C# for google.com website."` → genera codice corretto e funzionante.
  - Il modello **pensa prima di rispondere**, simula reasoning.
  - Il codice include `WebDriver`, `ChromeDriver` ecc., pronto per Visual Studio.

---

### 🔍 Differenze tra modelli

| Modello               | Parametri      | Accuratezza | Performance | Note |
|----------------------|----------------|-------------|-------------|------|
| `qwen:1.8b`          | 1.8B           | ❌ Bassa     | ✅ Alta      | Codice errato |
| `deepseek-r1:8b`  | 8B             | ✅ Alta      | 🟡 Media     | Codice corretto |
| `deepseek-r1:70b` | 70B            | ✅✅ Molto alta | ❌ Molto esigente | Richiede molta RAM/VRAM |

📌 **Nota**: l’uso di modelli più grandi come `70B` o `400B` richiede **hardware avanzato**:
- GPU: NVIDIA 3080/4090 o superiore
- VRAM: 64–128 GB
- Possibilmente quantizzazione (Q4, Q5, ecc.) per ridurre peso e migliorare l’esecuzione

---

### 🧵 Comandi utili

- **Chiudere un prompt Ollama attivo**:

```bash
/bye
```

- **Elenco modelli disponibili localmente**:

```bash
ollama list
```

- **Eseguire un modello già installato**:

```bash
ollama run nome_modello
```

- **Eliminare un modello già installato**:

```bash
ollama rm nome_modello
```

- **Mostrare le caratteristiche di un modello**:

```bash
ollama show nome_modello
```

- **Mostrare tutti i comandi possibile e la loro descrizione**:

```bash
ollama --help
```

---

### 💡 Conclusione

- Ollama permette di **testare localmente** i modelli LLM, risparmiando sui costi API (OpenAI, Anthropic, ecc.).
- È possibile eseguire prompt in stile ChatGPT **senza connessione internet**.
- L’accuratezza delle risposte dipende dalla **dimensione e qualità del modello** scelto.
- Ollama supporta modelli per **reasoning**, **scrittura codice**, **tool calling**, **vision**, **embeddings**, ecc.

---

✅ Nella prossima lezione vedremo **come integrare questi modelli locali nelle nostre applicazioni**.
