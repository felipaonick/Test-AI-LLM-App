# ✅ DeepEval – Login con Confident AI e Configurazione iniziale

## 🔍 Cos’è Confident AI?
**Confident AI** è la piattaforma cloud integrata con **DeepEval**, pensata per conservare in un luogo centralizzato i report dei test eseguiti localmente.  
Pur eseguendo le valutazioni nel proprio ambiente, DeepEval consente – grazie a Confident AI – di:
- Creare dataset
- Eseguire simulazioni
- Osservare metadati dei test
- Lanciare valutazioni online
- Raccogliere feedback umani
- Monitorare metriche, iperparametri, prompt, ecc.

---

## 👥 Creazione di un account su Confident AI

### Requisito ufficiale
È richiesto un **indirizzo email aziendale** per completare l’iscrizione.

### 🛠️ Workaround con email temporanea
In mancanza di un'email aziendale, è possibile usare:
- Un **servizio di email temporanea** (es. temp-mail.org)
- Validità di circa 15 minuti per ricevere link di conferma
- Generare una password forte (può essere quella suggerita da Apple)

⚠️ *Nota etica*: il metodo è utile per test e formazione, ma **non è raccomandato per uso aziendale o produzione.**

---

## 📝 Creazione dell’account

1. Visitare il sito [https://confident-ai.com](https://confident-ai.com) o tramite link da DeepEval
2. Inserire l’email aziendale (o quella temporanea) e una password
3. Confermare l'account
4. Inserire:
   - **Nome dell’organizzazione** (es: Execute Automation Ltd.)
   - **Nome personale**
   - **Server location** (es: United States)
5. Selezionare gli **obiettivi di test** (es: functional testing, no safety testing)
6. Nome progetto: es. `"rag application"`
7. Generare e copiare l’**API Key** fornita

---

## 🔐 Integrazione dell’API Key in DeepEval

Per permettere a DeepEval di comunicare con la dashboard cloud:

### 📦 Codice Python per login:
```python
import deepeval

deepeval.login_with_confident_ai("<API_KEY>")
```

Sostituire `"<API_KEY>"` con la propria chiave generata.

### ✅ Output atteso
```
Congratulations. You have successfully logged in.
```

---

## 🧪 Verifica della connessione

Una volta effettuato il login:
- Qualsiasi valutazione (`evaluate()`) verrà tracciata nel proprio **workspace** su Confident AI
- Il progetto e i test saranno visibili nella dashboard

---

## 🧭 Prossimi Step

- Terminare il processo di onboarding su Confident AI
- Esplorare la dashboard:
  - Prompt library
  - Dataset
  - Result history
- Iniziare a scrivere test utilizzando `evaluate()` e il proprio **modello LLM locale**

---

## 🛠️ Troubleshooting

Durante l’uso di `evaluate()` potresti vedere l’errore:
```
API key is required
```
👉 Questo errore si risolve assicurandosi di aver eseguito correttamente `login_with_confident_ai()` con una chiave valida.

---

## ✅ In sintesi

| Step | Azione |
|------|--------|
| 1️⃣ | Creare account su Confident AI |
| 2️⃣ | Generare e salvare l’API key |
| 3️⃣ | Eseguire login in DeepEval con `deepeval.login_with_confident_ai(<API key>)` |
| 4️⃣ | Iniziare a scrivere test con `evaluate()` |
| 5️⃣ | Monitorare i test nella dashboard cloud |
