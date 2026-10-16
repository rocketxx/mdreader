# MD Reader

Lettore ed editor di file Markdown (`.md`) in un'unica pagina HTML.
Funziona nel browser e anche senza internet. Non serve installare nulla.

- **Usarlo:** apri `md-reader.html` con Chrome, Edge o Firefox, oppure vai all'indirizzo
  GitHub Pages del progetto, se è pubblicato.
- **Privacy:** i documenti non vengono inviati da nessuna parte. Restano sul tuo computer e
  finiscono nell'archivio del browser solo se li salvi tu.

---

## Per iniziare

1. Apri un documento. Puoi farlo in tre modi:
   - trascina uno o più file `.md` sulla pagina;
   - premi **Apri** (Ctrl+O);
   - incolla del testo Markdown con Ctrl+V.
2. Per modificarlo premi **Modifica** (Ctrl+E). La finestra si divide: a sinistra scrivi, a
   destra vedi il risultato in tempo reale.
3. Per conservarlo hai due possibilità:
   - **Ctrl+S** lo salva nell'archivio del browser;
   - **Ctrl+Shift+S** scarica il file `.md`.

Ogni documento aperto ha la sua scheda sotto la barra in alto. Accanto al nome:

| Simbolo | Significato |
|---|---|
| ● | Modifiche non salvate |
| ✓ | Salvato nell'archivio del browser |

Se chiudi una scheda o la pagina con modifiche non salvate, il browser chiede conferma.

## Cosa sa fare

### Lettura
- Indice laterale, che evidenzia la sezione che stai leggendo.
- Barra di avanzamento della lettura.
- Ricerca nel documento (Ctrl+F) con contatore dei risultati. Invio va al successivo,
  Shift+Invio al precedente.
- Codice colorato per linguaggio, con pulsante **Copia** su ogni blocco.
- Diagrammi [Mermaid](https://mermaid.js.org/) nei blocchi ` ```mermaid `.
- Formule matematiche: `$E = mc^2$` dentro il testo, `$$ … $$` su righe proprie.
- Riquadri colorati in stile GitHub: `> [!NOTE]`, `> [!TIP]`, `> [!IMPORTANT]`,
  `> [!WARNING]`, `> [!CAUTION]`.
- Immagini ingrandibili con un clic. Esc chiude.
- Tema chiaro e scuro (pulsante ◐).
- Visualizzazione del sorgente (pulsante **Sorgente**).

### Modifica
- Barra di formattazione: grassetto, corsivo, barrato, titoli, link, codice, elenchi,
  attività, citazioni, tabelle, linee.
- Gli elenchi continuano da soli quando premi Invio. Invio su una voce vuota chiude l'elenco.
- Le caselle delle attività (`- [ ]`) si spuntano anche dall'anteprima, e il testo si
  aggiorna.
- Editor e anteprima scorrono insieme, allineati ai titoli.
- Ctrl+Z e Ctrl+Y annullano e ripristinano, anche dopo i comandi della barra.

### Menu File
| Voce | Cosa fa |
|---|---|
| Archivia nel browser | Salva il documento nell'archivio (Ctrl+S) |
| Scarica .md | Scarica il file Markdown (Ctrl+Shift+S) |
| Esporta HTML | Scarica una pagina HTML autonoma, con gli stili del reader |
| Copia come testo formattato | Copia il documento per incollarlo in Outlook, Word o Confluence |
| Mostra differenze | Mostra le righe aggiunte e rimosse rispetto al file aperto |
| Stampa / PDF | Stampa. Ogni sezione principale inizia su una nuova pagina e i link mostrano l'indirizzo |

## L'archivio del browser

Premi **Archivio** (Alt+A) per vedere i documenti salvati.

- **Cercare:** il campo di ricerca guarda sia nel nome sia nel contenuto.
- **Ordinare:** per ultima modifica, nome o dimensione.
- **Spostarsi:** con le frecce ↑/↓ scegli il documento, con Invio lo apri. A destra vedi
  l'anteprima del documento selezionato.
- **Azioni sul singolo documento:** Apri, Rinomina, Duplica, Scarica, Elimina.
- **Azioni su più documenti:** spunta le caselle e usa **Scarica selezionati** o
  **Elimina selezionati**. Senza selezione i pulsanti diventano **Scarica tutto**, che
  produce un unico `.zip`, ed **Elimina tutto**.
- **Importare:** **Importa file**, oppure trascina dei `.md` sulla schermata.

### Prima di affidarti all'archivio
- **L'archivio vive nel singolo browser.** Non si sincronizza tra computer o tra browser
  diversi e non è visibile ad altre persone.
- **Ogni indirizzo ha il suo archivio.** Il file aperto dal Desktop e la versione online su
  GitHub Pages non vedono gli stessi documenti. Per spostarli usa **Scarica tutto**, poi
  **Importa file**.
- **Si perde se cancelli i dati di navigazione del sito.** Anche in navigazione privata
  l'archivio non è disponibile o sparisce alla chiusura. Per i documenti importanti tieni
  sempre anche una copia scaricata.
- **Le eliminazioni non si possono annullare.**

## Scorciatoie

| Tasti | Azione |
|---|---|
| Ctrl+O | Apri file |
| Ctrl+E | Apri / chiudi l'editor |
| Ctrl+S | Salva nell'archivio del browser |
| Ctrl+Shift+S | Scarica il file `.md` |
| Alt+A | Apri / chiudi l'archivio |
| Ctrl+F | Cerca nel documento, o nell'archivio se è aperto |
| Ctrl+B / Ctrl+I / Ctrl+K | Grassetto / corsivo / link (nell'editor) |
| Tab | Inserisce due spazi (nell'editor) |
| Esc | Chiude ingrandimento, differenze, menu o archivio |
| Ctrl+P | Stampa |

Su Mac usa ⌘ al posto di Ctrl.

## Problemi noti
- Il file pesa circa 4 MB, quasi tutto per i diagrammi Mermaid. La libreria viene caricata
  solo se il documento contiene un diagramma.
- **Copia come testo formattato:** in Word e Outlook restano grassetti, tabelle, link e
  colori del codice. Formule e diagrammi possono non essere incollati correttamente.
- Lo scorrimento allineato ai titoli funziona con i titoli scritti con `#`. Con i titoli
  sottolineati (`===`, `---`) o dentro le citazioni torna a uno scorrimento proporzionale.

---


## Manutenzione

`md-reader.html` contiene tutto: il codice del reader e le librerie già compresse.

- **Per una piccola modifica** puoi modificare direttamente l'HTML. Il codice del reader è
  nell'ultimo blocco `<script>` del file: cercalo con `// ---------- Stato`. Gli stili sono
  nei blocchi `<style>` in testa.
- **Per modifiche frequenti o per aggiornare una libreria** conviene lavorare su file
  separati e poi unirli in un unico HTML:

  | File | Contenuto |
  |---|---|
  | `app.js` | Logica del reader |
  | `app.css` | Stili dell'interfaccia |
  | `doc.css` | Stili del documento (usati anche dall'esportazione HTML) |
  | `body.html` | Struttura della pagina |
  | `build.js` | Unisce tutto: `node build.js <cartella-librerie> index.html` |


## Librerie incluse

| Libreria | Versione | Licenza | Uso |
|---|---|---|---|
| [marked](https://github.com/markedjs/marked) | 12.0.2 | MIT | Conversione del Markdown |
| [DOMPurify](https://github.com/cure53/DOMPurify) | 3.4.16 | Apache 2.0 / MPL 2.0 | Rimozione di codice pericoloso dai documenti |
| [highlight.js](https://highlightjs.org/) | 11.9.0 | BSD-3-Clause | Colori del codice |
| [KaTeX](https://katex.org/) | 0.16.11 | MIT | Formule matematiche |
| [Mermaid](https://mermaid.js.org/) | 10.9.1 | MIT | Diagrammi |
