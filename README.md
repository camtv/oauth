# Cam.TV Login API
Tramite Cam.TV Login API è possibile integrare la funzionalità di login a Cam.TV su siti di terze parti. 

### Procedura di integrazione: 
* Aggiungere all'interno della tua pagina HTML un tag script come indicato qui di seguito:

```
<script src="https://www.cam.tv/login/extern_login.js"></script>
```

* Aggiungi un click handler ad un qualunque elemento UI del dom, tipicamente un button che chiama la seguente funzione dell'API di login di Cam.TV:

```
CTV.ExternalLogin(redirectUrl[, action, channelName]);
```

### Parametri dell'API:

I parametri accettati dall'API di login sono:

* redirectUrl	È l'URL al quale verrà effettuato il reindirizzamento una volta completato il login da parte dell'utente
* action	(opzionale) Determina quale modulo di login verrà mostrato
    * CTV.ACTION.CREATE: (default) da usare qualora l'utente abbia intenzione di creare un nuovo account
    * CTV.ACTION.LOGIN: da usare qualora l'utente abbia intenzione di effettuare il login
    * CTV.ACTION.CREATE_CHANNEL: da usare qualora l'utente venga invitato ad iscriversi tramite un canale già esistente su Cam.TV
* channelName	(opzionale) Solo con parametro action uguale a CTV.ACTION.CREATE_CHANNEL. Permette di specificare il nome del canale di un utente cha fa già parte di Cam.TV

### Esempio completo

Di seguito è riportato un esempio di invocazione dell'API di login tramite la gestione dell'evento click su un button. E' possibile provare operativamente l'esempio al seguente url:


```
<script src="https://www.cam.tv/login/extern_login.js"></script>
<button onclick="Login()">Login</button>
<script>
    function Login() {
        var redirectUrl = "https://www.miosito.it";
        var action = CTV.ACTION.CREATE;
        CTV.ExternalLogin(redirectUrl[, action, channelName]);
    }
</script>
```
