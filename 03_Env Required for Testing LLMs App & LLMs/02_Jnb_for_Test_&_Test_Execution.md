# 📓 Uso di Jupyter Notebook in VS Code con DeepEval

---

## 🎯 Obiettivo della Lezione

- Imparare a creare e usare **Jupyter Notebook** in **Visual Studio Code**
- Eseguire comandi Python e pip all’interno del notebook
- Collegare il notebook a un **ambiente virtuale Python**
- Preparare il progetto per le prossime lezioni su **Confident AI / DeepEval**

---

## ✅ Prerequisiti

- **Python** installato
- **Visual Studio Code** installato
- Estensione **Jupyter** installata in VS Code
- Un **ambiente virtuale Python** attivo (es. `myenv312`)
- `deepeval` installato via:
```bash
pip install -U deepeval
```

---

## 🧭 Creazione del Notebook

1. **Apri VS Code**
2. Premi `Cmd+Shift+P` (Mac) o `Ctrl+Shift+P` (Windows)
3. Cerca: `Create: New Jupyter Notebook`
4. Clicca sulla voce per creare il nuovo notebook `.ipynb`

---

## ✍️ Struttura del Notebook

- Puoi alternare **celle Markdown** e **celle di codice**.
- Esempio:

**Markdown:**
```markdown
# Installazione di DeepEval
```

**Python:**
```python
!pip install -U deepeval
```

---

## 🧠 Selezione del Kernel

> 🔴 **Importante**: Se non selezioni il kernel, il codice non verrà eseguito.

1. Clicca in alto a destra su `Select Kernel`
2. Scegli l'ambiente virtuale corretto (es. `myenv312`)
3. Se richiesto, accetta l’installazione del pacchetto `ipykernel`

---

## ✅ Esecuzione della Prima Cell

1. Dopo aver selezionato il kernel e scritto il comando:
```python
!pip install -U deepeval
```
2. Premi `Shift + Invio` per eseguire
3. Visualizzerai il log dell’installazione direttamente nel notebook

---

## 💾 Salvataggio del Notebook

- Premi `Cmd+S` o `Ctrl+S`
- Dai un nome descrittivo, ad esempio:
  ```
  installation.ipynb
  ```

---

## 🧪 Prossimi Passi

Nel prossimo modulo vedremo:
- Come **registrarsi su Confident AI**
- Come **creare un golden dataset**
- Come confrontare le **risposte del modello con gli expected outputs**
- Utilizzo avanzato di DeepEval per il **regression testing** su LLMs

---

## 📌 Vantaggi di Jupyter Notebook

- Permette di mantenere **uno storico eseguibile** delle operazioni
- Alterna codice eseguibile e spiegazioni scritte
- È ideale per **sperimentazioni interattive**, soprattutto su dati e modelli

