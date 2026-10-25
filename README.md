# Muscle Flex Therapy

Sito web di Muscle Flex Therapy: Camelia, massoterapista e massaggiatrice sportiva a Paratico (BS), presso la palestra Bengi Fitness. Dominio principale: **muscleflextherapy.it** (acquistati anche .art, .online e .shop, da reindirizzare al .it).

È un sito statico di una sola pagina: `index.html` più la cartella `assets/`. Non serve nessuna compilazione. Per provarlo in locale:

```
python3 -m http.server 8000
```

e poi apri http://localhost:8000 (aperto direttamente come file alcuni browser bloccano i font).

## Struttura

- `index.html`: pagina, stili e script della colonna vertebrale 3D.
- `assets/fonts/`: Cormorant Garamond (titoli) e Manrope (testo) ospitati nel sito, nessuna richiesta a Google Fonts.
- `assets/fibers.svg`: il motivo di fibre muscolari dello sfondo (usato come maschera, il colore lo decide il CSS).
- `assets/vendor/three.min.js`: three.js r128, ospitato nel sito.
- `assets/logo-*.png`, `assets/icon-*.png`, `assets/apple-touch-icon.png`: logo e icone, ricavati da un'immagine di 378 px. Vanno rigenerati dal logo originale in alta qualità.
- `assets/og.jpg`: immagine di anteprima quando si condivide il link (1200×630).

## Prima di andare online

Il sito contiene ancora dati di esempio. Da fare, in quest'ordine:

1. **Togliere il `noindex`**: in `index.html` eliminare `<meta name="robots" content="noindex">`. Finché resta, Google non indicizza il sito.
2. **Togliere la fascia "Bozza di anteprima"** in cima alla pagina (`<div class="note">`).
3. **Sostituire i segnaposto** (tutto ciò che è tra parentesi quadre, più i dati di esempio):
   - Trattamenti: nomi, descrizioni, durate e prezzi del listino (ora sono di esempio); condizioni del pacchetto da 5 sedute.
   - Chi sono: `[anni di esperienza]`, il terzo badge `[Corso o specializzazione]`, il ritratto di Camelia.
   - Contatti: telefono, email `[email]`, indirizzo di Bengi Fitness `[via e numero]`, orari (ora sono di esempio). Gli orari compaiono anche nella fascia "Dove / Quando" sotto l'apertura.
   - Piè di pagina: `P.IVA [da inserire]`.
4. **Il numero di telefono compare in più punti**: nel testo dei contatti, nel link `tel:+39...`, nella fascia "Prenota" sotto l'apertura e nei link `https://wa.me/39...` dei pulsanti WhatsApp. Tenerli allineati.
5. **Verificare le parole sul tipo di servizio**: i testi usano "massoterapista" e "massaggiatrice sportiva" come nella bio Instagram di Camelia. Confermare il titolo (per esempio il diploma) prima di aggiungere parole come "terapeutico" o promesse sul dolore.
6. **Aggiungere la pagina dell'informativa privacy** e il link nel piè di pagina. Il sito non usa cookie, quindi non serve il banner.
7. **Rigenerare logo, icone e `og.jpg`** dal logo originale.

## Pubblicazione

Il repository è già pronto per GitHub Pages: contiene `CNAME` (con `muscleflextherapy.it`), `.nojekyll` e una pagina `404.html`. Quando si decide di pubblicare:

1. Unire la PR in `main`.
2. Su GitHub: Settings → Pages → Build and deployment → Deploy from a branch → `main` / `/ (root)`. Il dominio personalizzato viene letto dal file `CNAME`.
3. Presso il registrar di muscleflextherapy.it, nei DNS:
   - record **A** per `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - record **AAAA** per `@`: `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
   - record **CNAME** per `www`: `kappa404-88.github.io`
4. Quando GitHub conferma il dominio (può volerci fino a un giorno), attivare "Enforce HTTPS".
5. **muscleflextherapy.art, .online e .shop**: GitHub Pages accetta un solo dominio per sito, quindi vanno reindirizzati con l'inoltro (redirect 301) del registrar verso `https://muscleflextherapy.it`.
6. Prima del lancio vero, togliere il `noindex` e la fascia "Bozza" (vedi sopra).

## Crediti

- [three.js](https://threejs.org) r128, licenza MIT (`assets/vendor/LICENSE-three.txt`).
- Font [Cormorant Garamond](https://github.com/CatharsisFonts/Cormorant) e [Manrope](https://github.com/sharanda/manrope), licenza SIL Open Font License 1.1 (`assets/fonts/`).
