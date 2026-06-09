# Installazione

Questa guida spiega come scaricare e avviare il progetto **Mini Blog API** sul proprio computer.

Il progetto è un sito statico, quindi non richiede installazione di pacchetti o configurazioni particolari. Sono necessari solo un browser moderno, Git e una connessione a internet.

## Requisiti

Prima di iniziare assicurarsi di avere:

- Git installato sul computer
- un browser moderno, ad esempio Chrome, Firefox, Edge o Safari
- una connessione internet attiva

La connessione internet serve per caricare Bootstrap tramite CDN e per recuperare i dati dalle API di JSONPlaceholder.

## Verificare Git

Aprire il terminale e digitare:

```bash
git --version
```

Se Git è installato correttamente, il terminale mostrerà la versione installata.

Se il comando non viene riconosciuto, installare Git dal sito ufficiale:

```text
https://git-scm.com/
```

## Clonare la repository

Dal terminale, scegliere la cartella in cui si vuole salvare il progetto e lanciare il comando:

```bash
git clone https://github.com/Trust51-bit/Mini-Blog-API-prova-facsimile-.git
```

Entrare poi nella cartella del progetto:

```bash
cd Mini-Blog-API-prova-facsimile-
```

## Avviare il sito

Essendo un sito statico, è possibile aprire direttamente il file:

```text
index.html
```

con un browser moderno.

Dalla homepage sarà possibile navigare verso:

- `posts.html`, per visualizzare i post caricati dalle API
- `autori.html`, per visualizzare gli autori caricati dalle API

## Avvio con server locale

In alternativa, è possibile avviare un piccolo server locale dalla cartella del progetto.

Con Python 3:

```bash
python3 -m http.server 8000
```

Poi aprire nel browser:

```text
http://localhost:8000
```

Per interrompere il server locale, tornare nel terminale e premere:

```text
CTRL + C
```

## Struttura principale

I file principali del progetto sono:

```text
Mini-Blog-API-prova-facsimile-/
├── index.html
├── posts.html
├── autori.html
├── style.css
├── script.js
├── README.md
└── DOCS/
    ├── installazione.md
    ├── faq.md
    └── api.md
```

## Problemi comuni

Se i post o gli autori non vengono caricati, controllare che la connessione internet sia attiva.

Se il layout non viene visualizzato correttamente, controllare che Bootstrap venga caricato dal CDN.

Se il sito non si apre, verificare di essere nella cartella corretta e di aprire il file `index.html`.

## Aggiornare il progetto

Se il progetto è già stato clonato e si vogliono scaricare eventuali aggiornamenti dalla repository, entrare nella cartella del progetto e usare:

```bash
git pull
```
