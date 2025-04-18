
# 🧠 Selezione dei Modelli LLM e Requisiti Hardware in Ollama

> 📚 Lezione dedicata alla scelta consapevole dei modelli LLM da eseguire in locale tramite Ollama, in base a potenza di calcolo disponibile e obiettivi del progetto.

> Lezione del: 15/04/2025

---

## 🎯 Obiettivo della lezione

- Comprendere come selezionare un **modello LLM adatto alla propria macchina**.
- Esaminare la **complessità, le dimensioni e i requisiti hardware** dei modelli disponibili.
- Capire il **compromesso tra potenza del modello e capacità della macchina**.

---

## 🧩 Selezione del modello LLM in Ollama

Quando si sceglie un modello da eseguire localmente, è possibile specificare:

- **Dimensione del modello** (es. 7B, 8B, 14B, 32B, 70B, fino a 405B o 671B)
- **Quantizzazione** (versione, compressione)
- **Numero di head di attenzione** (headcount) e relative dimensioni (`head_kv`)

### Esempi:

| **Modello**               | **Parametri** | **Dimensione file** | **Headcount** | **head_kv** |
|---------------------------|----------------|----------------------|---------------|-------------|
| Deepseek Coder 7B         | 7B             | ~4.7 GB              | 28            | ?           |
| Deepseek 70B              | 70B            | ~404 GB              | 128           | 128         |
| LLaMA 3.1 (405B)          | 405B           | ~243 GB              | 128           | 8           |
| Mistral / Qwen / Gemma    | Vari           | <10 GB               | Dipende       | Dipende     |

⚠️ **Nota**: Più è alto il numero di parametri, maggiore sarà la qualità delle risposte, ma anche l’impegno richiesto in termini di:
- Memoria RAM
- Potenza CPU/GPU
- Spazio disco

---

## 🛠️ Requisiti Hardware (consigliati)

| **Modello Max Consigliato** | **Macchine consigliate**                            |
|-----------------------------|------------------------------------------------------|
| Fino a 8B                   | Laptop consumer o Mac con M1/M2                     |
| Fino a 14B                  | Laptop con 32–64 GB RAM, M1 Max, M2 Ultra           |
| 30B+                        | Desktop con **GPU NVIDIA dedicata** (es. 2080/3080) |
| 70B+                        | Multi-GPU A100 / Server HPC                         |

💡 Se il modello è troppo grande:
- La tua macchina potrebbe rallentare, crashare o non eseguire il modello.
- Usa versioni quantizzate (es. `Q4_0`, `Q5_K_M`, `Q6_K`) per risparmiare memoria.

---

## 🧮 Effetti della complessità del modello

| **Fattore**          | **Aumenta con**                    | **Conseguenza**                                   |
|----------------------|------------------------------------|---------------------------------------------------|
| Parametri (es. 70B)  | Capacità linguistica / ragionamento | Aumentano i requisiti di esecuzione               |
| Quantizzazione       | ↓ Spazio disco / RAM               | Può ridurre la qualità della generazione          |
| Headcount            | Maggiore parallelismo / classificazione | Più consumo memoria e calcoli                    |

---

## 💡 Suggerimenti pratici

- Se hai un **Mac M1/M2 con 32–64 GB RAM**, usa modelli fino a **14B**.
- Se hai una **GPU discreta (es. 2080/3080)**, puoi eseguire anche **30–40B**.
- Se hai meno di 16 GB RAM e nessuna GPU dedicata: **usa modelli leggeri (<8B)**.
- Ricorda: **più è piccolo il modello, meno accurate saranno le risposte**, specialmente per task complessi.

---

## 📌 Conclusione

- Ollama permette di **testare modelli avanzati in locale** senza costi di API.
- Tuttavia, è cruciale selezionare il **modello giusto in base alla propria macchina**.
- Nella prossima lezione vedremo **come scaricare e avviare il primo modello LLM localmente** con Ollama.
