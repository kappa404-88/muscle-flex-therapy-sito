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

## Dati ancora da inserire

Il sito è visibile a Google: niente dati di esempio, ciò che non è confermato è nascosto. Appena Camelia li manda, aggiungere:

1. **Telefono e WhatsApp**: oggi si prenota solo con un messaggio su Instagram (`https://ig.me/m/muscle_flex_therapy`). Con il numero vero si possono rimettere il pulsante WhatsApp (`https://wa.me/39NUMERO?text=...`), il link `tel:` e il pulsante "Chiama" nella barra in basso sul telefono.
2. **Prezzi e durate** del listino (oggi "Prezzi su richiesta") e conferma dei 6 trattamenti elencati.
3. **Orari**, **via e numero** di Bengi Fitness, **anni di esperienza**, eventuali corsi o attestati.
4. **P.IVA** nel piè di pagina (obbligatoria per legge sul sito di un'attività) e la pagina dell'**informativa privacy**.
5. **Logo, icone e `og.jpg`** rigenerati dal logo originale in alta qualità.

La foto di Camelia nella sezione "Chi sono" è in `assets/camelia.webp` e `assets/camelia.jpg` (640×800, ritagliata 4:5): per cambiarla basta sostituire i due file.

Ogni volta che si cambia qualcosa, aggiornare `lastmod` in `sitemap.xml`.

## Pubblicazione

Il repository è pronto per GitHub Pages: contiene `CNAME` (con `muscleflextherapy.it`), `.nojekyll`, una pagina `404.html`, `robots.txt` e `sitemap.xml`. Registrar dei domini: Register.it. Quando si decide di pubblicare:

1. Unire la PR in `main`.
2. Su GitHub: Settings → Pages → Build and deployment → Deploy from a branch → `main` / `/ (root)`. Il dominio personalizzato viene letto dal file `CNAME`.
3. Presso il registrar di muscleflextherapy.it, nei DNS:
   - record **A** per `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - record **AAAA** per `@`: `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
   - record **CNAME** per `www`: `kappa404-88.github.io`
4. Quando GitHub conferma il dominio (può volerci fino a un giorno), attivare "Enforce HTTPS".
5. **muscleflextherapy.art, .online e .shop**: GitHub Pages accetta un solo dominio per sito, quindi vanno reindirizzati con l'inoltro (redirect 301) del registrar verso `https://muscleflextherapy.it`.
6. Google: in [Search Console](https://search.google.com/search-console) aggiungere la proprietà di tipo Dominio `muscleflextherapy.it`, inserire nei DNS il record TXT che Google indica, poi inviare la sitemap `https://muscleflextherapy.it/sitemap.xml`.
7. Consigliata la scheda Google Business Profile di Muscle Flex Therapy presso Bengi Fitness, Paratico.

## Crediti

- [three.js](https://threejs.org) r128, licenza MIT (`assets/vendor/LICENSE-three.txt`).
- Font [Cormorant Garamond](https://github.com/CatharsisFonts/Cormorant) e [Manrope](https://github.com/sharanda/manrope), licenza SIL Open Font License 1.1 (`assets/fonts/`).
