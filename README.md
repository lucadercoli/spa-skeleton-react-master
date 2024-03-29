# Single Page Application Skeleton (in React)

Questo progetto è parte del corso di ReactJS e il suo utilizzo è a solo scopo didattico.
Per crearlo è stato utilizzzata la CLI [Create React App](https://github.com/facebook/create-react-app).

# Attività da svolgere

1. Aggiungere la list view con l'elenco dei Tickets

   - Open New Ticket (button)
   - Edit / Delete del singolo Ticket

2. Aggiungere la form di inserimento nuovo Ticket

3. Aggiungere la form di modifica di un Ticket esistente

4. Aggiungere la cancellazione di un Ticket

_Tutte le funzionalità dovranno utilizzare un servizio che
implementa le funzionalità CRUD (GET, POST, PUT, DELETE)
comunicando con le REST API disponibili all'URL indicato
nella documentazione._

# Documentazione

## Accesso al servizio REST

**URL (Anonymous):** https://crudcrud.com/ e copiare la url completa aggiungendo "/tickets" come suffisso es: https://crudcrud.com/api/56ced3c2e13b455795de69ef2ff9fd6f/ticktes

**Come specificare HTTP Verb, Body e Headers nelle chiamate HTTP**

```ts
// "Accept" e "Content-Type" sono NECESSARI per le richieste PUT e POST
// "Authorization" serve se si usa il servizio con Basic authentication
basicHeaders: Headers = new Headers({
  Accept: "application/json",
  "Content-Type": "application/json",
  //Authorization: "Basic " + btoa(this.basicAuthAccount),
});

const promise = await fetch(this.apiURL, {
  method: "POST",
  headers: this.basicHeaders,
  body: JSON.stringify(ticket),
});
```

## Form di Creazione Ticket

**Campi**

- _Title_ (testo)
- _Description_ (testo multi linea)
- _Category_ (combo)
  - Unknown (valore = 1)
  - Development (2)
  - System (3)
- _Priority_ (combo)
  - Low (valore = 1)
  - Normal (2)
  - High (3)

## Form di Modifica Ticket

**Campi**

- _Title_ (testo)
- _Description_ (testo multi linea)
- _Category_ (combo, valori come sopra)
- _Priority_ (combo, valori come sopra)
- _State_ (combo)
  - New (valore = 1)
  - On Going (2)
  - Close (3)

## Nota sul modello Ticket

Nella cartella Models è presente una classe Ticket,
da utilizzarsi per il popolamento della vista tabellare (punto 1).
Questo modello NON è adatto per il salvataggio di un nuovo Ticket / Ticket modificato.

## Script disponibili

### `npm start`

Runs the app in the development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br>
You will also see any lint errors in the console.

### `npm run build`

Builds the app for production to the `build` folder.<br>
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br>
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.
