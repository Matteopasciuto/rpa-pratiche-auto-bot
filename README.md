# 🚗 RPA Automazione Pratiche Automobilistiche (Portale dell'Automobilista)

Un sistema di **Robotic Process Automation (RPA)** potenziato dall'Intelligenza Artificiale per l'inserimento automatizzato e massivo delle pratiche auto sul portale governativo italiano.

## 🎯 Obiettivo del Progetto
Questo progetto nasce per ottimizzare i flussi di lavoro di autoscuole e agenzie, azzerando i tempi di data entry manuale e prevenendo errori di trascrizione. Il sistema legge i documenti dei clienti, processa i dati ed esegue l'inserimento completo della pratica (es. Conseguimento Patente B) in totale autonomia.

## ⚙️ Architettura del Sistema a 3 Fasi
1. **Cervello (Estrazione AI):** Utilizza l'API di Google Gemini 2.5 Flash per eseguire un OCR intelligente sui documenti d'identità (Patenti, CI), restituendo i dati anagrafici in un formato JSON strutturato.
2. **Validazione & Matching:** Calcolo matematico del Codice Fiscale tramite `python-codicefiscale` per validare l'output dell'IA. Associazione automatica dei file immagine del cliente (es. foto tessera) scansionando le directory locali.
3. **Braccia (Web Automation):** Script in `Playwright` che gestisce il login, la navigazione dei menu, la compilazione dinamica dei form React, l'iniezione sicura dei file (bypassando i blocchi del file explorer di Windows) e il download automatico della documentazione finale (PDF TT2112).

## 🛠️ Stack Tecnologico
* **Linguaggio:** Python
* **Automazione Browser:** Playwright (Sync API)
* **Intelligenza Artificiale:** Google GenAI API (Gemini 2.5 Flash)
* **Utilities:** `python-codicefiscale`, elaborazione JSON, gestione OS/file system.

## ⚠️ Privacy e Sicurezza
Tutte le credenziali di accesso al portale governativo e i codici PIN sono gestiti localmente e ignorati dal controllo di versione. Nessun documento d'identità reale o dato sensibile dei clienti viene caricato in questo repository.# rpa-pratiche-auto-bot
