# Automazioni di risparmio energetico per dispositivi CAME DOMOTIC 3.0 in Home Assistant

Questa raccolta di blueprint è progettata per semplificare l'integrazione di **termostati CAME** con sensori finestra, in conformità alla normativa **UNI EN 15232-1:2017** sui sistemi di automazione degli edifici (BACS – Building Automation and Control Systems).

## Contenuto

La directory `blueprints/automation/cameautomations/` contiene tre blueprint:

1. **spegni_salva_stato.yaml**
   Spegne il termostato e ne salva lo stato quando si apre una finestra.

2. **ripristina_stato.yaml**
   Ripristina lo stato precedente del termostato alla chiusura della finestra.

3. **blocca_riaccensione.yaml**
   Previene la riaccensione del termostato mentre la finestra è ancora aperta.

## Requisiti

- Home Assistant 2023.5 o successiva
- Termostati CAME integrati tramite l'integrazione personalizzata `ha_came`
- Sensori finestra (binari), è possibile utilizzare i sensori finestra delle centrali antifurto Proxinet.
- `input_select` helper creati per ciascun termostato da controllare

## Installazione

1. Copia la cartella `cameautomations` in: config/blueprints/automation/


2. Riavvia Home Assistant oppure ricarica i blueprint da:

> Impostazioni → Automazioni → Blueprint → Menu (in alto a destra) → Ricarica blueprint

3. Crea gli **helper input_select** per ogni termostato da:

> Impostazioni → Dispositivi e servizi → Helper → + Crea Helper → Selezione

- Per ogni input_select, aggiungi le opzioni corrispondenti ai possibili stati HVAC del termostato (`off`, `heat`, `cool`, `auto`).
- Dai un nome significativo (es. `termostato_soggiorno_stato`).

4. Crea nuove automazioni utilizzando i blueprint:

- Vai su **Impostazioni → Automazioni → + Crea automazione → Usa blueprint**.
- Seleziona uno dei blueprint in `cameautomations`.
- Compila i campi richiesti (sensore finestra, termostato, input_select stato salvato).
- Salva l’automazione.

5. Ripeti per tutti i termostati e sensori finestra da gestire.

## Riferimenti normativi

Questo sistema contribuisce all’efficienza energetica degli edifici secondo:
**UNI EN 15232-1:2017 – Prestazione energetica degli edifici – Influenza dell’automazione, del controllo e della gestione tecnica dell’edificio (BACS)**.

## Contributi

Progetto mantenuto da **[Flavio](https://github.com/odoricof)**.

Pull request, segnalazioni e miglioramenti sono benvenuti!




