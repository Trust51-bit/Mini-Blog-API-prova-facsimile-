# Mini-Blog-API-prova-facsimile-
prova facsimile esame

questa repository serve per creare un mini blog fittizio che utilizza le API di JSONPlaceHolder per popolare il sito con post e autori fittizzi

il progetto è un esempio di sito statico

## funzionalità

il progetto espone queste funzionalità:

- sito statico con multipagina
- homepage che riassume il sito
- pagina post che mostra i post presi dalle API esterne
- pagina autori che mostra gli autori fittizzi
- integra un design responsive per anche dispositivi mobile

## tecnologie utilizzate

- html
- css & bootstrap (per il design e la responsività)
- javascript (per fetchare i dati delle api)
- API di JASONPlaceHolder per i dati fittizzi


## requisiti
- un browser moderno
- connessione attiva a internet per Bootstrap e per fetchare
- git o github per clonare la repository

## API utilizzate

Risorsa Endpoint Uso nel sito
Post https://jsonplaceholder.typicode.com/posts Pagina posts.html
Utenti https://jsonplaceholder.typicode.com/users Pagina autori.html

## struttura

il sito è organizzato così:

```
mini-blog-api/
├── README.md
├── index.html #homepager del sito
├── posts.html #pagina che mostra i post
├── autori.html #pagina che mostra gli autori
├── style.css #foglio di stile del sito
├── script.js # Script Javascript per fetchare i dati delle API
├── docs/ #cartella relativa a tutta la documentazione
│ ├── installazione.md #guida all'installazione
│ ├── faq.md # domande frequenti
│ └── api.md # dettagli sulle API utilizzate
└── assets/
```

## LICENSE

il progetto utilizza una licenza MIT. Per info cliccare qui: [text](https://github.com/twbs/bootstrap/blob/main/LICENSE)