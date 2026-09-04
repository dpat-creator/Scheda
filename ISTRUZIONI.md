# Scheda Danila — come metterla online e installarla

Sette file, una cartella. Non serve installare niente sul computer.

```
index.html                 l'app
manifest.webmanifest       nome, icona, colori (serve per l'installazione)
sw.js                      fa funzionare l'app senza rete
icon-192.png  icon-512.png  icon-maskable-512.png  apple-touch-icon.png
```

Regola unica: **i file devono restare tutti nella stessa cartella**, con questi nomi.

---

## Opzione A — Netlify Drop (la più veloce, ~2 minuti)

1. Vai su **app.netlify.com/drop**
2. Trascina nella pagina la cartella `scheda-app` intera (non i file singoli).
3. Netlify carica e ti dà un indirizzo tipo `https://qualcosa-1234.netlify.app`.
4. Crea un account gratuito quando te lo chiede, altrimenti il sito scade dopo un'ora.
5. In *Site configuration → Change site name* puoi rinominarlo, es. `scheda-danila.netlify.app`.

Per aggiornare la scheda in futuro: torni sul sito, *Deploys*, e trascini di nuovo la cartella.

## Opzione B — GitHub Pages (se preferisci avere i file su GitHub)

1. Su **github.com** crea un repository nuovo, pubblico, chiamato ad esempio `scheda`.
2. Nella pagina del repository: *Add file → Upload files*, trascina i sette file, poi *Commit changes*.
3. *Settings → Pages*. In **Source** scegli `Deploy from a branch`, branch `main`, cartella `/ (root)`. Salva.
4. Dopo un paio di minuti l'indirizzo è `https://TUONOME.github.io/scheda/`.

> Il repository dev'essere pubblico perché Pages sia gratuito. L'app non contiene dati personali: i tuoi carichi restano solo sul telefono, non finiscono su GitHub.

---

## Installarla sul telefono

**iPhone (Safari — deve essere Safari, non Chrome)**
Apri l'indirizzo → tasto Condividi (il quadrato con la freccia) → *Aggiungi a Home* → *Aggiungi*.

**Android (Chrome)**
Apri l'indirizzo → compare in fondo alla pagina il pulsante arancione *Installa l'app*, oppure menu ⋮ → *Installa app*.

Da lì in poi l'icona sta tra le altre app, si apre a schermo intero senza barra del browser e funziona anche senza campo in palestra (dopo la prima apertura con rete).

---

## Come funziona

- **Spunta le serie** man mano che le fai; la barra in alto mostra quante ne mancano.
- **Il campo kg** salva da solo. Nelle settimane successive ti suggerisce in grigio l'ultimo carico che avevi usato su quell'esercizio — se sei rimasta nel range su tutte le serie, alzalo.
- **Azzera** cancella solo le spunte della scheda e della settimana che stai guardando. I carichi restano.
- **Note & set up** sotto ogni esercizio: sono le indicazioni del coach, parola per parola.

## Backup — leggi questo

I dati vivono nella memoria del browser di quel telefono. Restano lì tra una sessione e l'altra, ma spariscono se cancelli i dati del sito, disinstalli l'app o cambi telefono. Su iPhone, inoltre, Safari può ripulire i dati di un sito che non apri per qualche settimana (l'app installata dalla schermata Home è molto meno esposta a questo).

Quindi: ogni tanto tocca **Esporta backup** in fondo alla pagina. Scarica un file `.json` che puoi rimettere dentro con **Ripristina backup**, anche su un telefono diverso.

## Aggiornare la scheda a ottobre

Gli esercizi stanno in fondo a `index.html`, nel blocco `const SCHEDE = {`. Ogni esercizio ha:

- `n` nome, `d` distretto, `rest` recupero, `som` tempo di esecuzione
- `w` le otto settimane: `[[3,"10"]]` vuol dire 3 serie da 10, `[[1,"10"],[2,"8"]]` vuol dire 1 da 10 più 2 da 8
- `up` opzionale: `1` nelle settimane in cui il coach ha segnato `+`

Se preferisci, mandami la scheda nuova e te la aggiorno io.
