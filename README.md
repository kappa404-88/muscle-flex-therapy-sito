# Muscle Flex Therapy

Sito web di Muscle Flex Therapy, i massaggi di Camelia. Dominio principale: **muscleflextherapy.it** (acquistati anche .art, .online e .shop, da reindirizzare al .it).

È un sito statico di una sola pagina: `index.html` più la cartella `assets/`. Non serve nessuna compilazione. Per provarlo in locale:

```
python3 -m http.server 8000
```

e poi apri http://localhost:8000 (aperto direttamente come file alcuni browser bloccano i font).

## Struttura

- `index.html`: pagina, stili e script della colonna vertebrale 3D.
- `assets/fonts/`: Figtree e Marcellus ospitati nel sito, nessuna richiesta a Google Fonts.
- `assets/vendor/three.min.js`: three.js r128, ospitato nel sito.
- `assets/logo-*.png`, `assets/icon-*.png`, `assets/apple-touch-icon.png`: logo e icone, ricavati da un'immagine di 378 px. Vanno rigenerati dal logo originale in alta qualità.
- `assets/og.jpg`: immagine di anteprima quando si condivide il link (1200×630).

## Prima di andare online

Il sito contiene ancora dati di esempio. Da fare, in quest'ordine:

1. **Togliere il `noindex`**: in `index.html` eliminare `<meta name="robots" content="noindex">`. Finché resta, Google non indicizza il sito.
2. **Togliere la fascia "Bozza di anteprima"** in cima alla pagina (`<div class="note">`).
3. **Sostituire i segnaposto** (tutto ciò che è tra parentesi quadre, più i dati di esempio):
   - Titolo della pagina e meta description: `[Città]`.
   - Benvenuto: `[Città]` nella riga sopra il titolo.
   - Trattamenti: nomi, descrizioni, durate e prezzi del listino; condizioni del pacchetto da 5 sedute.
   - Chi sono: `[titolo professionale]`, `[anni di esperienza]`, i tre badge, il ritratto di Camelia.
   - Contatti: telefono, email `[email]`, indirizzo e `[Città]`, orari.
   - Piè di pagina: `P.IVA [da inserire]`.
4. **Il numero di telefono compare in più punti**: nel testo dei contatti e nel link `https://wa.me/39...` del pulsante WhatsApp. Tenerli allineati.
5. **Verificare le parole sul tipo di servizio** ("massoterapia", "terapeutici", "dolori") in base al titolo professionale reale di Camelia.
6. **Aggiungere la pagina dell'informativa privacy** e il link nel piè di pagina. Il sito non usa cookie, quindi non serve il banner.
7. **Rigenerare logo, icone e `og.jpg`** dal logo originale.

## Pubblicazione

Hosting ancora da scegliere. Con GitHub Pages: Settings → Pages → Deploy from a branch → `main` / root, poi impostare il dominio personalizzato `muscleflextherapy.it` e configurare il DNS presso il registrar come indicato da GitHub.

## Crediti

- [three.js](https://threejs.org) r128, licenza MIT (`assets/vendor/LICENSE-three.txt`).
- Font [Figtree](https://github.com/erikdkennedy/figtree) e [Marcellus](https://fonts.google.com/specimen/Marcellus), licenza SIL Open Font License 1.1 (`assets/fonts/`).
