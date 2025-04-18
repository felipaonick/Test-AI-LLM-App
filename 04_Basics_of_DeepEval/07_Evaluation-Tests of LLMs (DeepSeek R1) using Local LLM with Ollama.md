## 🧪 Esecuzione dei Test DeepEval su Modello Locale (Ollama)

### 🎯 Obiettivo della Lezione
- Sostituire l’uso dell’API OpenAI (GPT-4) con un **modello locale**.
- Eseguire test in **modalità completamente offline**.
- Azzerare i costi legati all’inferenza via API.

---

## 🛠️ Requisiti
- **Modello Ollama già scaricato**, es: `deepseek-r1:8b` (`deepseek-r1`).
- Ollama in esecuzione locale.
- DeepEval già installato.
- API ConfidentAI già configurata (opzionale, per visualizzazione in dashboard cloud).

---

## 🔧 Impostazione del Modello Locale

Per dire a DeepEval di usare il modello Ollama locale:

```bash
!deepeval set-ollama-model deepseek-llm:8b-instruct
```

✅ Risultato atteso:
```
Congratulations! You are now using local Ollama model for all the evaluation that requires an LM.
```

---

## 🧪 Esecuzione del Test: `dataset.evaluate()`

Una volta impostato il modello locale, è possibile eseguire la valutazione:

```python
dataset.evaluate(metrics=[AnswerRelevancyMetric()])
```

🔁 Il test verrà eseguito utilizzando il **modello locale Ollama**, ad esempio `deepseek-r1`, invece di GPT-4.

### ✅ Output atteso
- Nessun costo di esecuzione.
- Risultati identici (se il modello è accurato).
- Risposta elaborata in locale.
- Risultati visibili anche nel portale **Confident AI** se il login è attivo.

---

## 📊 Confronto risultati

Nel portale **Confident AI**, sarà possibile confrontare:
- Risultati ottenuti tramite OpenAI (GPT-4).
- Risultati ottenuti con modelli locali Ollama.

### 🟢 Vantaggi:
| Aspetto             | Modello Locale Ollama        | API OpenAI GPT-4       |
|---------------------|------------------------------|-------------------------|
| 💸 Costo            | Nessuno                      | Sì (a consumo)          |
| 🔐 Privacy          | Totale (nessun invio dati)   | Dati inviati a OpenAI   |
| 🚀 Velocità         | Dipende dal proprio hardware | Costante ma remoto      |
| 🧪 Ripetibilità     | Alta (modello sempre uguale) | Possibili update invisibili |

---

## 💡 Suggerimento Avanzato

È possibile usare anche un comando alternativo con `base_url`:

```bash
!deepeval set-ollama-model deepseek-r1:8b-instruct --base-url http://localhost:11434
```

Questo è utile se:
- Ollama gira su un container Docker.
- Si usa una porta diversa da quella predefinita.

---

## ✅ Conclusione

- Ora siamo in grado di **eseguire test DeepEval completamente offline**.
- Nessun costo ulteriore sarà sostenuto.
- La qualità del test dipende dal **modello Ollama selezionato**.
- La metodologia rimane identica a quella usata con OpenAI.

---

## 📍Prossimi Passi

Nelle prossime lezioni:
- Useremo questa configurazione con **metriche multiple**.
- Scopriremo come **eseguire test avanzati** con agenti, tool calling, e RAG.
- Pubblicheremo test anche **senza Confident AI**, salvando i risultati in file locali.
