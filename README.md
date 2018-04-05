# Database

Tipi di database:

Gerarchico:  -> DL/1
Reticolare: ogni entità ha altre entità correlate, si crea un reticolo di entità in un grafo delirante (eh?) -> Supra
Relazionale: si creano entità e si creano relazioni tra queste entità usando delle chiavi esterne -> SQL based
			 MySql, Access, Oracle sono tutti SQL based, ovvero utilizzano le query SQL (solo per le letture);
			 ogni casa ha i propri tipi di dato specifici, cosa che rende la migrazione molto lunga e complicata;
			 se si lavora con i database relazionali USARE SOLO I TIPI DI DATO BASE per facilitare la migrazione;
Ad oggetti: sono praticamente quelli relazionali, ma al posto ci sono gli oggetti e le maniglie -> Zope
			sfrutta gli ORM;
Documentale: come un relazionale dove le colonne in ogni riga possono variare di numero -> MongoDB
			 è come se ogni riga fosse un ArrayList;


In linea di massima, un database è un software server che gira insieme al programma.
Per accedere ad un database (che in genere è crittato) si usa un DBMS -> MySqlD
Il DBMS si prende periodicamente cura del database ribilanciando le tabelle (gli indici).
Il DBMS non va mai staccato brutalmente o si rischia di fulminare il database, si fa una call.
Se si ha bisogno di dati, si usa un client per stabilire una ->connessione<- con il DBMS, lavorare e poi chiudere la connessione.
ODBC: interfaccia dei DBMS relazionale, tramite la quale è possibile relazionarsi con un DB relazionale (questa cosa ha senso)
In sostanza ODBC è uno stantard API per far comunicare client e server per quanto riguarda i DB relazionali.
Per modificare i dati su un database si avvia una transazione
	se la transazione non va a buon fine si può usare una rollback per annullare i cambiamenti
	se si vuole confermare i cambiamenti si usa commit, e solo in quel momento i dati vengono veramente cambiati
	fino a che non si fa commit il software lavora su una specie di buffer
	
DB embedded: database incastonato nel software, aggiunto tramite include -> sqlite
Sqlite è utile per creare prototipi, in quanto la sintassi OBCD è identica ai db normali
Se si vuole poi passare ad un vero database l'unica cosa da cambiare è la connect


//-----------------------------------------------------------------------------------------------------------------------
ORM: insieme di accorgimenti software per rendere persistente (permane anche dopo la chiusura del programma) un oggetto
