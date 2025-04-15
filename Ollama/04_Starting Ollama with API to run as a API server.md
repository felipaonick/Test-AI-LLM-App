## 🧠 Uso di Ollama come API Server per LLM

### 📌 Obiettivo della lezione
Configurare Ollama come **server API** per comunicare con modelli LLM in locale tramite richieste HTTP, in alternativa all’interfaccia a riga di comando.

---

### 🔧 Avvio del server Ollama

Per avviare il server API di Ollama:

```bash
ollama serve
```

- Questo comando esegue Ollama in modalità **servizio** sulla porta `11434`.
- Se Ollama è già in esecuzione, apparirà un messaggio tipo:
  
  ```
  address already in use
  ```

✅ Una volta avviato, Ollama espone un’**interfaccia HTTP REST** accessibile all’indirizzo:

```
http://localhost:11434
```

---

### 🔍 Verifica API attive

Puoi testare se il server è attivo con:

```
http://localhost:11434/
```

📥 La risposta sarà:

```json
{"status": "ollama is running"}
```

---

### 📮 API di generazione: `/api/generate`

**Endpoint**: `POST /api/generate`

Permette di inviare un prompt e ottenere la risposta del modello.

#### 📦 Payload esempio

```json
{
  "model": "qwen2.5:14b",
  "prompt": "Why is the sky blue?",
  "stream": false
}
```

- `model`: nome del modello installato (es. `llama3`, `deepseek-r1:8b`, ecc.)
- `prompt`: il testo della richiesta da processare
- `stream`: `true` per risposta parola per parola (streaming), `false` per risposta intera

---

### 🧪 Esempio pratico con Postman

1. **Metodo**: `POST`
2. **URL**: `http://localhost:11434/api/generate`
3. **Body** (JSON):

```json
{
  "model": "qwen2.5:14b",
  "prompt": "Why is the sky blue?",
  "stream": false
}
```

📤 **Risultato atteso**:

Una risposta completa generata dal modello, ad esempio:

```json
{
    "model": "qwen2.5:14b",
    "created_at": "2025-04-15T15:04:01.098059Z",
    "response": "The sky appears blue due to a phenomenon called Rayleigh scattering. When sunlight enters Earth's atmosphere, it collides with molecules and small particles in the air. Sunlight is made up of different colors, each with its own wavelength—red light has longer wavelengths than blue light.\n\nWhen sunlight encounters gas molecules such as nitrogen and oxygen, shorter-wavelength light (like blue) scatters more easily than other colors because these wavelengths are closer to the size of the gas molecules. This means that when you look up at the sky on a clear day, much of the scattered blue light enters your eye from all directions.\n\nThis is why we see the daytime sky as blue: it's not actually painted blue but appears so due to the scattering effect of sunlight by the gases and particles in our atmosphere. At sunrise or sunset, when the sun is near the horizon, its light has to pass through more layers of the Earth’s atmosphere than during midday. More extensive scattering occurs, which means that most shorter wavelengths are scattered away before we can see them on the horizon, leaving us with longer wavelength colors like red and orange dominating our view.",
    "done": true,
    "done_reason": "stop",
    "context": [
        151644,
        8948,
        198,
        2610,
        525,
        1207,
        16948,
        11,
        3465,
        553,
        54364,
        14817,
        13,
        1446,
        525,
        264,
        10950,
        17847,
        13,
        151645,
        198,
        151644,
        872,
        198,
        34634,
        279,
        12884,
        374,
        6303,
        30,
        151645,
        198,
        151644,
        77091,
        198,
        785,
        12884,
        7952,
        6303,
        4152,
        311,
        264,
        24844,
        2598,
        13255,
        62969,
        71816,
        13,
        3197,
        39020,
        28833,
        9237,
        594,
        16566,
        11,
        432,
        4530,
        3341,
        448,
        34615,
        323,
        2613,
        18730,
        304,
        279,
        3720,
        13,
        8059,
        4145,
        374,
        1865,
        705,
        315,
        2155,
        7987,
        11,
        1817,
        448,
        1181,
        1828,
        45306,
        2293,
        1151,
        3100,
        702,
        5021,
        92859,
        1091,
        6303,
        3100,
        382,
        4498,
        39020,
        33906,
        6819,
        34615,
        1741,
        438,
        46403,
        323,
        23552,
        11,
        23327,
        2630,
        34861,
        3100,
        320,
        4803,
        6303,
        8,
        1136,
        10175,
        803,
        6707,
        1091,
        1008,
        7987,
        1576,
        1493,
        92859,
        525,
        12128,
        311,
        279,
        1379,
        315,
        279,
        6819,
        34615,
        13,
        1096,
        3363,
        429,
        979,
        498,
        1401,
        705,
        518,
        279,
        12884,
        389,
        264,
        2797,
        1899,
        11,
        1753,
        315,
        279,
        36967,
        6303,
        3100,
        28833,
        697,
        7912,
        504,
        678,
        17961,
        382,
        1986,
        374,
        3170,
        582,
        1490,
        279,
        61082,
        12884,
        438,
        6303,
        25,
        432,
        594,
        537,
        3520,
        23983,
        6303,
        714,
        7952,
        773,
        4152,
        311,
        279,
        71816,
        2456,
        315,
        39020,
        553,
        279,
        44512,
        323,
        18730,
        304,
        1039,
        16566,
        13,
        2411,
        63819,
        476,
        42984,
        11,
        979,
        279,
        7015,
        374,
        3143,
        279,
        34074,
        11,
        1181,
        3100,
        702,
        311,
        1494,
        1526,
        803,
        13617,
        315,
        279,
        9237,
        748,
        16566,
        1091,
        2337,
        5099,
        1292,
        13,
        4398,
        16376,
        71816,
        13666,
        11,
        892,
        3363,
        429,
        1429,
        23327,
        92859,
        525,
        36967,
        3123,
        1573,
        582,
        646,
        1490,
        1105,
        389,
        279,
        34074,
        11,
        9380,
        601,
        448,
        5021,
        45306,
        7987,
        1075,
        2518,
        323,
        18575,
        67266,
        1039,
        1651,
        13
    ],
    "total_duration": 36183943900,
    "load_duration": 16357875000,
    "prompt_eval_count": 35,
    "prompt_eval_duration": 488499100,
    "eval_count": 228,
    "eval_duration": 19330875500
}
```

📡 Se `stream: true`, la risposta verrà ricevuta **a frammenti**, un token alla volta.

---

### 📚 Documentazione ufficiale API Ollama

Disponibile qui:  
🔗 [https://ollama.com/library](https://ollama.com/library)

Contiene:
- Specifiche endpoint (`/generate`, `/chat`, `/embeddings`, ecc.)
- Parametri supportati
- Esempi d’uso via `curl`, Postman, HTTP libraries

---

### ⚙️ Integrazione con LangChain

> A partire dalla prossima sezione del corso, tutte le interazioni con il modello locale verranno effettuate **tramite le API HTTP** di Ollama, utilizzabili da LangChain, script Python/NodeJS, ecc.

---

### ✅ Conclusioni

- Ollama può essere avviato come **API server** locale per comunicare con LLM.
- L’endpoint `/api/generate` consente di generare testo passando un prompt e un modello.
- Il supporto allo streaming permette l’uso in applicazioni in tempo reale.
- Eseguire `ollama serve` è il passo fondamentale per abilitare l’uso in backend o da codice esterno.
- Utile per integrazioni con Postman, LangChain, app locali o backend AI personalizzati.

---

✅ Nella prossima lezione, vedremo **come integrare LangChain o altri strumenti direttamente con l’API server Ollama**, usando modelli locali con estrema flessibilità.
