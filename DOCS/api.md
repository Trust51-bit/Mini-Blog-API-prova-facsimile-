# API utilizzate

Questa pagina descrive le API utilizzate dal progetto **Mini Blog API**.

Il sito recupera dati fittizi dal servizio gratuito **JSONPlaceholder**, utile per testare chiamate API senza creare un backend o un database reale.

## Base URL

Tutte le chiamate partono da questo indirizzo:

```text
https://jsonplaceholder.typicode.com
```

Nel file `script.js` il base URL è salvato nella costante:

```javascript
const JSONPLACEHOLDER_BASE = "https://jsonplaceholder.typicode.com";
```

## Endpoint principali

| Risorsa | Endpoint | Pagina del sito | Utilizzo |
| --- | --- | --- | --- |
| Post | `/posts` | `posts.html` | Mostra i post del blog |
| Utenti | `/users` | `autori.html` | Mostra gli autori |
| Utenti | `/users` | `posts.html` | Associa ogni post al nome dell'autore |

## Endpoint dei post

Endpoint completo:

```text
https://jsonplaceholder.typicode.com/posts
```

Questo endpoint restituisce una lista di post fittizi.

Nel progetto viene usato nella pagina `posts.html` per mostrare i primi 12 post.

Esempio di struttura di un post:

```json
{
  "userId": 1,
  "id": 1,
  "title": "titolo del post",
  "body": "contenuto del post"
}
```

Campi utilizzati nel sito:

- `id`, per mostrare il numero del post
- `userId`, per collegare il post al suo autore
- `title`, per mostrare il titolo
- `body`, per mostrare il testo del post

## Endpoint degli utenti

Endpoint completo:

```text
https://jsonplaceholder.typicode.com/users
```

Questo endpoint restituisce una lista di utenti fittizi.

Nel progetto viene usato:

- nella pagina `autori.html`, per mostrare gli autori
- nella pagina `posts.html`, per associare ogni post al nome dell'autore

Esempio di struttura di un utente:

```json
{
  "id": 1,
  "name": "Nome Autore",
  "email": "email@example.com",
  "address": {
    "city": "Nome citta"
  },
  "company": {
    "name": "Nome azienda"
  }
}
```

Campi utilizzati nel sito:

- `id`, per identificare l'utente
- `name`, per mostrare il nome dell'autore
- `email`, per mostrare l'indirizzo email
- `address.city`, per mostrare la citta
- `company.name`, per mostrare il nome dell'azienda

## Come vengono caricate le API

Le chiamate API vengono gestite nel file:

```text
script.js
```

Il caricamento avviene quando la pagina HTML è pronta, tramite l'evento:

```javascript
document.addEventListener("DOMContentLoaded", () => {
  // caricamento dei dati
});
```

Il file JavaScript controlla quale contenitore è presente nella pagina:

- se trova `#posts-list`, carica i post
- se trova `#authors-list`, carica gli autori

## Funzione per recuperare i dati

Il progetto usa la funzione `fetch()` di JavaScript per recuperare dati dalle API.

La funzione principale è:

```javascript
async function getJSON(url) {
  const response = await fetch(url);
  if (!response.ok) {
    throw new Error(`Errore HTTP: ${response.status}`);
  }
  return await response.json();
}
```

Questa funzione:

- invia una richiesta HTTP all'URL passato
- controlla se la risposta è corretta
- converte la risposta in formato JSON
- segnala un errore se la richiesta non va a buon fine

## Caricamento dei post

Per caricare i post, il progetto richiama contemporaneamente:

```text
/posts
/users
```

Questo permette di mostrare sia il contenuto del post sia il nome dell'autore.

Nel file `script.js` questa operazione viene gestita con:

```javascript
const [posts, users] = await Promise.all([
  getJSON(`${JSONPLACEHOLDER_BASE}/posts`),
  getJSON(`${JSONPLACEHOLDER_BASE}/users`)
]);
```

## Caricamento degli autori

Per caricare gli autori, il progetto richiama:

```text
/users
```

I dati ricevuti vengono inseriti nel contenitore HTML:

```text
#authors-list
```

## Gestione degli errori

Se una chiamata API fallisce, il sito mostra un messaggio di errore nella pagina.

Esempi di possibili cause:

- connessione internet assente
- endpoint non raggiungibile
- errore temporaneo del servizio esterno
- risposta HTTP non valida

Nel codice, gli errori vengono gestiti con `try...catch`.

## Note

JSONPlaceholder fornisce dati fittizi. Questo significa che:

- i post non sono reali
- gli autori non sono reali
- i dati possono essere usati liberamente per test e progetti didattici
- non è necessario configurare un database
