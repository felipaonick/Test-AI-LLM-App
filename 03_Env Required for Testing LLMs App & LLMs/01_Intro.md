# ⚙️ Setup Ambiente di Valutazione LLM con DeepEval

---

## 🎯 Obiettivo della Sezione

In questa sezione imparerai a:
- Configurare l’ambiente per testare applicazioni basate su modelli linguistici di grandi dimensioni (LLM)
- Utilizzare **DeepEval** come tool principale per l’evaluation
- Preparare tutto in **Visual Studio Code (VS Code)** + **Jupyter Notebook**

> 💡 Nota: lo stesso processo si applica anche a strumenti simili come **Ragas** o altri framework di valutazione.

---

## 🧰 Requisiti Preliminari

Prima di iniziare, assicurati di avere installato:
- **Python** (consigliata versione ≥ 3.12)
- **Visual Studio Code** (o alternativamente Cursor IDE)
- **Estensione Jupyter Notebook per VS Code**

---

## 🐍 Installazione di Python

1. Vai su [python.org/downloads](https://www.python.org/downloads/)
2. Scarica la versione più recente compatibile con il tuo sistema operativo (Windows / Mac / Linux)
3. In alternativa, su Mac puoi usare `brew install python`

---

## 🛠️ Editor di Codice

### 🔹 Opzione 1: Visual Studio Code
- Scaricalo da: [https://code.visualstudio.com](https://code.visualstudio.com)
- Consigliato per utenti generici
- Supporta tutte le estensioni necessarie (Python, Jupyter, GitHub Copilot…)

### 🔹 Opzione 2: Cursor IDE
- Scaricabile da: [https://www.cursor.sh](https://www.cursor.sh)
- Ideale se vuoi sfruttare funzionalità AI avanzate (es. agenti MCP, auto-completamento, ecc.)
- Totalmente compatibile con estensioni VS Code

---

## 🧪 Creazione e Attivazione Ambiente Virtuale

> Best practice: ogni progetto Python dovrebbe usare un ambiente virtuale dedicato.

### 🔹 Creazione:
```bash
python3.12 -m venv myenv312
```

### 🔹 Attivazione:
```bash
source myenv312/bin/activate
```

> Dopo l’attivazione, comparirà il nome dell’ambiente tra parentesi nel terminale.

### 📦 Perché usare un virtualenv?
- Isola le librerie del progetto
- Evita conflitti con altri ambienti
- Può essere copiato o spostato facilmente tra macchine

---

## 📥 Installazione DeepEval

1. Vai su [https://github.com/confident-ai/deep-eval](https://github.com/confident-ai/deep-eval) (se disponibile)
2. Comando di installazione:
```bash
pip install -U deepeval
```

> Verranno installate automaticamente anche tutte le **dipendenze** richieste (transformers, datasets, ecc.).

---

## 📓 Installazione Estensione Jupyter

Per eseguire ed esplorare i test su notebook interattivi:

1. Apri Visual Studio Code
2. Vai su “Extensions” (Ctrl+Shift+X)
3. Cerca e installa:
```
Jupyter
```

> Indispensabile per le esercitazioni delle prossime lezioni.

---

## ✅ Verifica Finale Setup

Checklist:
- [x] Python installato
- [x] VS Code o Cursor operativi
- [x] Ambiente virtuale creato e attivo
- [x] Libreria `deepeval` installata
- [x] Estensione Jupyter attiva

---

## 🧭 Conclusione

Hai completato la **configurazione dell’ambiente di test** per valutare LLM con DeepEval!

Dalla prossima lezione:
- Usiamo DeepEval per misurare **relevance, hallucination, factuality** e altri parametri
- Lavoriamo su progetti reali in **Jupyter Notebook**

