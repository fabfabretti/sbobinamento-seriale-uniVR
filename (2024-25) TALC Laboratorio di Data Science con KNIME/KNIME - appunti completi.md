# Lezione 1

## Teoria

### Cos'è data analytics

<img src="./Lezione 1.assets/image-20241214220325296.png" alt="image-20241214220325296" style="zoom:20%;float:right;border-radius:40px;margin-left:30px" />Data analytics è un termine che indica **metodi** e **tecniche** per estrarre valore dai dati. Occasionalmente, lo stesso termine denota invece gli strumenti utilizzati per questa estrazione.

Distinguiamo tre tipi:

* Descrittivo
* Predittivo
* Prescrittivo

Convenzionalmente il termine di Buisness Intelligence si associa al livello descrittivo, e i livelli successivi sono detti advanced analytics. Tuttavia, a volte la linea di demarcazione non è così utile.

|                    Analytics descrittiva                     |                     Analytics predittiva                     |                    Analytics prescrittiva                    |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|           Risponde alla domanda "Cos'è successo?"            | Si concentra su risposte a domande successive all'aver appreso cosa è successo: "Perché è successo, cosa succederà?" |          Risponde alla domanda    "Che cosa fare?"           |
| È il punto di partenza: descrive i dati del passato per renderli interpretabili. | Si serve della creazione di modelli probanilistici, che cerchino relazioni fra i dati e modi per anticipare futuri possibili. | Guardano al passato e ci offrono una possibile vista del futuro e come agire. |
|      Si concretizza in dashboard interattive e report.       | Si concretizza in strumenti diagnostici o di alert e strumenti di forecast | Si concretizzano in sistemi di ottimizzazione, raccomandazione e agenti autonomi. |

#### Esempi

1. I membri del consiglio di amministrazione ricevono un report mensile via email in formato PDF che include lo stato riassuntivo del buisness e tabelle/frafici che mostrano le tendenze del KPI (key performance indicator) per paese e tipologia di hotel. 
   **⇝ Descrittivo/predittivo**
2. Manager di una catena alberghiera hanno accesso a un cruscotto online aggiornato settimanalmente con misure di interesse. La dashboard mostra tariffe e occupazione di hotel e camere.
   **⇝  Descrittivo**
3. Area manager è iscritta a un buisness alert, che dà notifiche quando una struttura smette di essere nella traiettoria che gli permetterebbe di raggiungere il target occupato.
   **⇝ Predittivo**
4. Sistema autoprise che gestisce dinamicamente il prezzo delle stanze d'albergo, simulando in base ai dati storici diversi livelli di occupazione guardando la stagione, l'interesse sul web...
   **⇝ Prescrittivo**
5. Programma fedeltà per i clienti, dove gli iscritti ricevono via mail proposte personalizzate per sconti o upgrade. Dietro c'è un propensity model, ovvero un algoritmo che propone sconti personalizzati per far accettare l'utente.
   **⇝ Tutti ma soprattutto prescrittivo**

Quindi capiamo che i tre tipi di analytics sono diversi, ma nella realtà non sono necessariamente alternativi: possono sovrapporsi fra loro.

<img src="./Lezione 1.assets/image-20241214221449342.png" alt="image-20241214221449342" style="zoom:25%;" />

Una frustrazione condivisa in molte aziende è il fatto che si dica "ci sono i dati ma non sappiamo dove trovarli!". Più si riesce a rendere fruibili i dati a tante persone, più è possibile che le persone potranno generare un valore dall'interpretazione dei dati stessi.

Più l'abalytics è complessa, più crescono le competenze e la sponsorship necessaria; in generale, è una buona idea procedere in maniera agile portando prima delle analitiche più semplici e poi portare valore crescenze.

### Chi fa data analytics?

Tutti i knowledge workers, ovvero colletti bianchi che hanno a che fare con i dati, possono interagire come utenti con report o dashboard o addirittura diventare creatori di capability avanzate.

Possiamo individuare 4 ruoli specifici.

#### Utenti di buisness / knowledge workers

<img src="./Lezione 1.assets/image-20241214232425276.png" alt="image-20241214232425276" style="border-radius:40px;zoom:25%;float:left;margin-right:40px"/> Interagiscono quotidianamente con i dati in qualche misura; il loro ruolo principale è di fruitori, quindi hanno beneficio nel capire le cose di base,poiché il grosso valore è che queste competenze di base si integrano con le loro conoscenze specifiche aziendali e  possono prendere decisioni migliori interpretandoli correttamente.

Inoltre la loro produttività personale può essere influenzata positivamente dato che possono diventare in grado di automatizzare le proprie attività usando macro in Excel o KNIME.

Per loro è sufficiente avere una comprensioen di massima di quello che le AA (advanced analytics) possono fare con loro, senza bisogno di diventare esperte. È però importante che apprendaano queste basi, poiché altrimenti non riusciranno a capire le opportunità di applciazione.

#### Buissness analyst / data analyst

<img src="./Lezione 1.assets/image-20241215210311677.png" alt="image-20241215210311677" style="border-radius:40px;zoom:25%;float:left;margin-right:40px" />Hanno il compito di mettere in connessione il mondo del buisness con il mondo dei dati.

Hanno una comprensione solida dei processi del mercato, dei clienti, dei processi, etc. perchè sono sempre in contatto con vendite, marketing...

Hanno un forte background aziendale, e possono quindi tradurre le esigenze del mondo del buisness in requisiti tecnici.

Sono abili utilizzatori delle tecniche di data analytics, in quanto devono estrarre informazioni rilevanti per il buisness partendo dai dati, ma anche delle di data storytelling in quanto devono comunicare efficacemente le informazioni in loro possesso. Sono inoltre in grado di utilizzare strumenti di machine learning e possono creare anche prototipi di tecniche avanzate prima di passare il testimone ai data analyst.

Questa figura può chiaramente avere forte vantaggio dal saper scrivere codice, per poter costruire semplici query di estrazione o script di trasformazione di dati, ma non è richiesto.

#### Data scientist

<img src="./Lezione 1.assets/image-20241215010315545.png" alt="image-20241215010315545" style="border-radius:40px;zoom:25%;float:left;margin-right:40px" /> I data scientist predispongono le AA; sono i maggiori esperti di algoritmi di apprendimento automatico, e possono implementare qualunque tipo di analisi partendo da zero.

Collaborano attivamente con i BA, attraverso i quali rimangono a contatto con le necessità del buisness.

Sanno programmare abilmente e sanno codificare processi complessi di trasformazione dei dati, di machine learning anche attraverso l'uso di librerie.

#### Data engineer

<img src="./Lezione 1.assets/image-20241215210138672.png" alt="image-20241215210138672" style="border-radius:40px;zoom:25%;float:left;margin-right:40px" />Rientrano anche ruoli collegati, come system engineer e data architect. Assicurano il funzionamento della data analytics prendendosi cura e progettando l'infrastruttura.

Sono loro a costruire pipeline, ovvero flussi di dati che siano stabilmente disponibili per le applicazioni analitiche. Interagiscono con i data science e con il resto dell'IT.

<img src="./Lezione 1.assets/image-20241214234236247.png" alt="image-20241214234236247" style="zoom:33%;" />

### Modern Data Stack

<img src="./Lezione 1.assets/image-20241214234635303.png" alt="image-20241214234635303" style="zoom: 15%;border-radius:0;float:left;margin-right:40px" />È un termine usato per descrivere le tecnologie ospitate da cloud che lavorano insieme per consentire alle aziende di raccogliere, elaborare e analizzare grandi quantità di dati.

È chiaro che con l'avvento del cloud computing dovremmo includere pure quello nello schemino, ma "non scendiamo in questo tipo di dettaglio"

### Strumenti di analisi dei dati

Ne abbiamo quattro tipi+1:

* **Fogli elettronici di calcolo**: hanno capacità molto limitata, ma sono portabili e molto diffusi nelle aziende. Hanno la possibilità di raccogliere dati e offrire visualizzazioni grafiche, ma sono inadeguati a creare flussi di dati robusti e automatizzati.
  Va bene per piccoli campionamenti di dati, ma non si presta ad automatizzazione.
  * Google Sheets, Microsoft Excel, Libreoffice ???
* **Buisness intelligence**: sono applicazioni che creano delle dahboard interattive e user friendly, permettendo la democratizzazione dei dati che serve.
  Sono applicazioni dotate do una vasta scelta di tipo di visualizzazione, possono collegare varie visualizzazioni per esplorarei dati in modo guidato.
  Offrono delle capacità limitate di applicazioine di algoritmi di machine learning, ma questi strumenti da soli non riescono ad abilitare l'AA.
  * Power BI, Tableau, Google Data Studio...
* **Low-code/no-code analytics**: permettono di costruire rapidamente soluzioni avanzate di data analytics senza codice, usando il paradigma della programmazione visuale e creando dei cosiddetti workflow. Ci interfacciamo ai dati con uno strumento che ci fa disegnare il flusso di elaborazione dei dati.
  Il workflow può essere eseguito con nuovi dati senza essere modificato; una volta che è impacchettato, può essere usato anche da un utente con poche conoscenze.
  * KNIME, RapidMiner, Alteryx Designer.
* **Code-based analytics**: l'approccio più tradizionale è scrivere codice con linguaggi di programmazione e librerie. Un data scientist può usarli per costruire soluzioni altamente personalizzate, e incorporarle anche in altre applicazioni. Il livello di complicazione si alza.
  * Python, R, Scala

<img src="./Lezione 1.assets/image-20241215012211201.png" alt="image-20241215012211201" style="zoom: 50%;" />

* Il nuovo tipo: **generative AI**
  Si può usare l'AI per generare codice che facci analisi dei dati. Claude è il migliore, e a pagamento permette di caricare dati e analizzarli direttamente online.

## KNIME

<img src="./Lezione 1.assets/image-20241215013911962.png" alt="image-20241215013911962" style="zoom:30%; float:right; margin-left:40px" />KNIME (Konstantz Information Miner) è una piattaforma open source con licenza GPLv3 che unisce analisi dati, reportistica e integrazione con componenti di machine learning e data mining. L'interfaccia grafica permette di assemblare nodi per la preprocessazione dei dati (ETL - Extraction Transformation Loading), per la modellazione, l'analisi e la visualizzazione.

KNIME non è lo strumento migliore sul mercato; IBM e altri hanno strumenti più diffusi e più efficaci, così come con i linguaggi di programmazione riusciamo a fare di più. Tuttavia, nel suo insieme, è uno strumento che nel suo fare "un po' di tutto" si colloca fra i migliori.

È inoltre il leader assoluto in open source.

### Concetti chiave

* **Nodo**: è l'unità di base di computazione. Un nodo implementa una specifica operazione sui dati. 
* **Workflow**: è l'intera sequenza di nodi.

Le finestre sono: <img src="./Lezione 1.assets/image-20241215014031744.png" alt="image-20241215014031744" style="zoom:33%; float:right" />

* **Explorer**: organizziamo i workflow. Ci troviamo:
  * **LOCAL**: spazio di lavoro locale, aka le cartelle memorizzate sul pc
  * **Server pubblico KNIME**: troviamo workflow di esempio organizzati per argomento
  * **My-KNIME-Hub**: è collegato al nostro spazio utente nella piattaforma, e possiamo condividervi workflow e componenti riusabili. Bisogna però iscriversi a KNIME Hub per usarla, il che è consigliato dato che KNIME ha una gran community.
* **Node repository**: è il menu dei nodi KNIME; per esempio, cercando excel, troviamo tutti nodi per esportare ed importare dati da .xls.
* **Workflow editor**: è dove con drag and drop diamo vita al workflow.
* **Node description**: vediamo informazioni sul nodo selezionato; come funziona, parametri e ingresso/uscita.
* **Outline**: offre una vista larga del workflow; aiuta se ho decine di nodi.
* **Console**: vediamo errori e lista dei dati per capire se tutto va bene.

#### Nodi

Il nodo è l'unità minima di azione. <img src="./Lezione 1.assets/image-20241215014921154.png" alt="image-20241215014921154" style="zoom:30%;float:right;margin-left:40px" />

* Il nome sintetizza quello che fa il nodo.
* Il quadrato spiega in che condizione si trova il nodo.
* Ogni nodo ha un commento, di default il numero progressivo di nodo.
* Sono collegati fra loro attraverso porte di I/O. Hanno fforme e colori diversi in base al contenuto:
  * i triangoli sono dati
  * i quadrati sono modelli statistici, connessioni remote o immagini
  * i cerchi sono variabili.

##### Tipi di nodi 

* **<img src="./Lezione 1.assets/image-20241215023542065.png" alt="image-20241215023542065" style="zoom:30%;float:right;margin-right:40px" />I/O**: Input permettono di portar dentro CSV, JSON, DB remoti, web scraping... Output permettono di salvare su file o altrove.

* **Manipolazione**: Aggregano, ordinano, filtrano...

* **Analytics**: Implementano modelli statistici 

* **Controllo flusso**: posso creare cicli condizionati!
* **Altri**: ad esempio posso accedere a social network o basi di dati fornite da servizi esterni tramite API.

## Demo!

### Esercizio 1 - Hello world

*Riferimento: data analytics per tutti pag 27, https://aboutbigdata.net*

<img src="./Lezione 1.assets/image-20241217145750906.png" alt="image-20241217145750906" style="border-radius:20px" />

### Esercizio 2 -  GIGO

<img src="./Lezione 1.assets/image-20241217150227427.png" style="zoom:40%;float:right; margin-left:40px;border-radius:20px" alt="image-20241217150227427" />Vogliamo ripulire dei dati; è una rottura di palle ma statisticamente va fatto.

Vogliamo sistemae:

* Togliere righe duplicate
* Maiuscole e minuscole incoerenti
* Indirizzi email con formattazione errata
* Valori numerici mancanti
* Alcuni valori di credito sono negativi, e sono quindi utenti inattivi che vogliamo rimuovere
* Colonne inutili

Alla fine vogliamo ottenere una lista pulita di utenti contattabili, e poiché la lista cambia giornalmente vogliamo un workflow che pulisca sistematicamente i dati ogni volta che vogliamo aggiornare la mailing list.

![image-20241217162919993](./Lezione 1.assets/image-20241217162919993.png)

<img src="./Lezione 1.assets/image-20241217164249870.png" alt="image-20241217164249870" style="border-radius:20px" />

# 2 - Trasformare i dati

## Il data model

Il **data model** è la rappresentazione visiva di come sono interconnessi i dati.

Noi trattiamo un modello a tabelle.

Possiamo distinguere diversi tipi di tabelle:

* ==Tabelle master / anagrafiche==
  Ddescrivono le entità rilevanti per il business, come ad esempio prodotti, fornitori, impiegati. Ogni riga corrisponde ad una istanza dell'entità
* ==Tabelle transazionali/ eventi e fatti==
  Descrivono fatti che si verificano in un momento preciso (es. vendite, ordini). Ogni riga corrisponde ad un evento, le colonne descrivono l'evento e le entità che ne hanno fatto parte.
* ==Relazioni==
  Le tabelle in un DB relazionale sono collegate tra di loro. Le colonne usate per collegare più tabelle sono dette chiavi.

### Combinare tabelle

<img src="./Lezione 2.assets/image-20241221092414370.png" alt="image-20241221092414370" style="zoom:30%;float:right;margin-left:30px" />Le join normalmente si fanno in SQL ma non lo trattiamo.

Ci sono diversi tipi di join: non necessariamente le tabelle hanno piena corrispondenza fra i campi. Nel nostro esempio, alcune tabelle potrebbero non essere aggiornatissime (quindi ho vendite di prodotti non ancora censiti in magazzino o al viceversa ho un prodotto censito ma non ancora venduto).

Distinguiamo i seguenti tipi.

* <img src="./Lezione 2.assets/image-20241221092647521.png" alt="image-20241221092647521" style="zoom:50%;float:right;margin-left:30px" />==Inner join==: combina due o più tabelle e mette nel risultato solo gli elementi di cui ci sono le corrispondenze
* ==Right/left join==: mantengo tutta la tabella di sinistra/destra e aggiungo le corrispondenze di destra; potrei avere dei buchi
* ==Full outer join==: posso avere buchi da una parte o dall'altra.

Esempi:

| Inner join<br /><img src="./Lezione 2.assets/image-20241221092829680.png" alt="image-20241221092829680" style="zoom:50%;" /> | Left outer join<br /><img src="./Lezione 2.assets/image-20241221093005141.png" alt="image-20241221093005141" style="zoom:50%;" /> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Right outer join<br />![image-20241221093134334](./Lezione 2.assets/image-20241221093134334.png) | Full outer join<br />![image-20241221093149429](./Lezione 2.assets/image-20241221093149429.png) |

## Applicazione a KNIME

### Nodo Joiner

In KNIME, il nodo che applica la Join è il nodo **joiner**, dove dobbiamo specificare le corrispondenze e anche che colonne includere nel risultato. *In Excel corrisponde a VLOOKUP.*

### Altri nodi per combinare le tabelle

Ci sono anche altri modi per combinare tabelle, con column appender e concatenate; 

* <img src="./Lezione 2.assets/image-20250109173644661.png" alt="image-20250109173556560" style="zoom:70%;float:left;margin-right:20px" />==Column Appender== 
  Mi aggiunge una colonna; devo accertarmi io che ci sia lo stesso numero di righe e corrispondono.
* <img src="./Lezione 2.assets/image-20250109173736058.png" alt="image-20250109173556560" style="zoom:50%;float:left;margin-right:20px" />==Concatenate==
  Appiccica alla fine di una tabella la seconda; devo essere ovviamente sicuro che i dati siano corrispondenti!!

* <img src="./Lezione 2.assets/image-20241221093847920.png" alt="image-20241221093847920" style="zoom:50%;float:right;margin-left:30px" />==<img src="./Lezione 2.assets/image-20250109173556560.png" alt="image-20250109173556560" style="zoom:40%;float:left;margin-right:20px" />Group by==
  In KNIME come in Excel posso raggruppare i valori e riassumere le righe; il nodo per farlo è Group By.  Nella Group By posso usare diversi operatori.

* <img src="./Lezione 2.assets/image-20250109173843573.png" alt="image-20250109173843573" style="zoom:70%;float:left;margin-right:20px" />==Nodo Pivot==
  Un altro modo per aggregare i dati è l'operazione Pivot. Mentre nella Group By i gruppi sono righe nella tabella di output, possiamo "ruotare" alcuni gruppi in modo che appaiano verticalmente, come colonne, nella tabella di output.

## Esercizio 1

![image-20241221094257846](./Lezione 2.assets/image-20241221094257846.png)

![image-20250109174213663](./Lezione 2.assets/image-20250109174213663.png)

1. ==Dieci prodotti con fatturato più alto==

![image-20250109184311590](./Lezione 2.assets/image-20250109184311590.png)

2. ==Tre prodotti più venduti per ogni categoria==

Per poterlo fare mi serve un nodo loop :(

<img src="./Lezione 2.assets/image-20250109184512328.png" alt="image-20250109184512328" style="zoom:50%;" />

Ho tre categorie:

* <img src="./Lezione 2.assets/image-20250109184537286.png" alt="image-20250109173556560" style="zoom:40%;float:left;margin-right:20px" /> ==Counting loop start==
  Ripeto la stessa operazione per un numero fisso di volte
* <img src="./Lezione 2.assets/image-20250109184704309.png" alt="image-20250109173556560" style="zoom:40%;float:left;margin-right:20px" />==Chunk loop start==
  Ripeto la stessa operazione per ogni chunk, ovvero per ogni gruppo di dimensioni fisse all'interno del file d input. Se il chunk è 1, succede per ogni riga.
* <img src="./Lezione 2.assets/image-20250109184712791.png" alt="image-20250109173556560" style="zoom:50%;float:left;margin-right:20px" />==Group loop start==
  Ripeto le operazioni per ogni gruppo di righe, dove il gruppo è definito da una combinazione una di valori nelle colonne di selezione. E' group by sotto steroidi.

<img src="./Lezione 2.assets/image-20250109185420762.png" alt="image-20250109185420762" style="zoom:50%;" />

3. ==Paese verso cui vendiamo di più==

![image-20250109190006356](./Lezione 2.assets/image-20250109190006356.png)

4. ==Capire, durante l'anno, quanto abbiamo ricavato per ogni categoria==

Vogliamo quindi formattare le date come date :)

Per farlo usiamo i nomi

* **String to Date&Time**: converte da testo a data
* **ExtractFate&Time Fields**: estrae elementi specifici es. giorno, mese
* **Date&Time row filter**: indovina indovinello.

<img src="./Lezione 2.assets/image-20250110101800394.png" alt="image-20250110101800394" style="zoom:50%;" />

5. Qual è il peso relativo di ogni categoria sul portafoglio totale di prodotti per l'anno in corso

Dobbiamo dividere le vendite generate nelle varie categorie per il totale generato da tutte le categorie messe insieme. Il totale è un dato che non abbiamo nelle tabelle ma possiamo calcolarlo a parte e salvarlo in una.. variabile!

<img src="./Lezione 2.assets/image-20250110101907965.png" alt="image-20250110101907965" style="zoom:33%;float:left;margin-right:30px" />Possiamo farlo con il nodo Table Row to Variable, che trasforma tutti i valori della prima riga di una tabella in variabili. Che bello ehehe

![image-20250110121624396](./Lezione 2.assets/image-20250110121624396.png)

6. ==Consolida l'output in un unico file excel.==

C'è un nodo apposta e supporta fino a 4 archi entranti.

![image-20250110125606659](./Lezione 2.assets/image-20250110125606659.png)



7. ==In quali mesi dell'anno dobbiamo aspettarci un picco di vendite epr le nostre categorie stagionali?==

Quindi devo

* aggregare per mese
* visualizzare con un grafico a linee.

![image-20250110130858932](./Lezione 2.assets/image-20250110130858932.png)

<img src="./Lezione 2.assets/image-20250110130914273.png" alt="image-20250110130914273" style="zoom: 25%;" />





# 3 - Social media data, estrazione e analisi

## Database

<img src="./Lezione 3.assets/image-20241221123442739.png" alt="image-20241221123442739" style="zoom:50%;float:right;margin-left:30px" />Ogni tabella è formata da righe in cui sonon immagazzinati i dati. SQL è il linguaggio usato per programmare l'accesso e la modifica ai DB.

Alcuni strumenti sono:

* MySQL
* FreeSQLdatabase
* phpMyAdmin

### Setup

Usiamo le credenziali:

* https://www.phpmyadmin.co/
* Host: `sql8.freesqldatabase.com`
* DB name: `sql8756933`
* DB user: `sql8756933`
* DB password: `negu5sLUHm`
* Port: 3306



### DB in Knime

E' un'estensione preinstallata chiamata KNIME Database Extension.

Esiste un nodo per ciascun tipo di database, e un nodo generico da configurare per eventuali altri.

A questo punto ci sono altri nodi dedicati per scegliere la tabella e leggerla. Quando sono nel nodo DBreader, finalmente posso collegarmi ai nodi visti fino ad ora.

Possiamo anche eseguire operazioni direttamente sul DB, spostando il motore di esecuzione sul server anziché sul mio pc.

![image-20250113170220737](./Lezione 3.assets/image-20250113170220737.png)

### Esercizio

1. Leggi da un DB in mysql.

![image-20250115160345424](./Lezione 3.assets/image-20250115160345424.png)

## Report sui social

Osserviamo il report Digital 2024 Global Overview Report, che viene rilasciato ogni 6 mesi.

<img src="./Lezione 3.assets/image-20250115160837060.png" alt="image-20250115160837060" style="zoom:50%;" />

E' sempre in incremento. (Ma va?)

<img src="./Lezione 3.assets/image-20250115160943662-1736953784475-1.png" alt="image-20250115160943662" style="zoom:50%;" />

I paesi nuovi digitalizzati spendono più tempo sui social.

<img src="./Lezione 3.assets/image-20250115161004151.png" alt="image-20250115161004151" style="zoom:50%;" />

![image-20250115161056881](./Lezione 3.assets/image-20250115161056881.png)

L'età media è in aumento.

<img src="./Lezione 3.assets/image-20250115161144480.png" alt="image-20250115161144480" style="zoom: 33%;" />

Tiktok batte tutti per tempo di permanenza.

![image-20250115161306007](./Lezione 3.assets/image-20250115161306007.png)

### Come minare le conversazioni?

Esistono dei prodotti specifici che forniscono informazioni. Sono strumenti molto molto expensive, anche decine-migliaia al mese per strumento. Chi è nel mondo accademico, quindi, si deve arrangiare e recuperare i dati in altro modo.

Le piattaforme social offrono API a pagamento e gratuitamente.; in alternativa è permettere di comprare i dati dai Data Reseller, che rivendono i dati in gran quantità :')

Quindi famo scraping. Lesgo!

Vediamo in demo due strumenti:

* APIfy
* Phantom Buster

Costano qualche decina di dollaro al mese e permettono di raccogliere i dati. Usano direttamente il tuo account per fare le cose grazie ai cookie di sessione. :)

### Demo

<img src="./Lezione 3.assets/image-20250115163132909.png" alt="image-20250115163132909" style="zoom: 50%; float: left; margin-right: 30px;" />Praticamente il prof come foto ha scelto quella dove sembra il cugino di Amadeus sotto sostanze. (No harm meant, è assolutamente bravissimo a spiegare e si vede che ci tiene un sacco!)

Possiamo esportare tutto in JSON. 

## Esercizio Social Media Data Analysis

![image-20250115164233568](./Lezione 3.assets/image-20250115164233568.png)

1. Quali sono i 20 post che hanno ricevuto più like
2. Quali sono i 20 utenti più attivi in termini di post pubblicati
3. Alcuni post sono geolocalizzati, quali sono le 20 città più rappresentate?
4. Quali sono i giorni della settimana nei quali si pubblicano più post?
5. Quali sono i 20 utenti più menzionati?

![image-20250115171924814](./Lezione 3.assets/image-20250115171924814.png)

# Lezione 4

## Accesso a Google Sheets

Per accedere a Google sheets ci servono questi nodi:

* <img src="./Lezione 4.assets/image-20250128154346431.png" alt="image-20250128154346431" style="zoom:25%;" /> ==Google Authenticator==: nodo autenticatore a Google
* <img src="./Lezione 4.assets/image-20250128154407187.png" alt="image-20250128154407187" style="zoom: 25%;" /> ==Google Sheets Connector==: connettore all'ambiente di Sheets
* <img src="./Lezione 4.assets/image-20250128154443098.png" alt="image-20250128154443098" style="zoom: 25%;" /> ==Google Sheets Reader==: fa l'effettiva lettura.

Esistono, come per i database, dei nodi che permettono di creare, aggiungere, scrivere o aggiornare un google sheet; sono operazioni dedicate.

### Demo

Ha un file City Living, excel caricato in google sheer, che è generato con PhantomBuster.

<img src="./Lezione 4.assets/image-20250128153545627.png" alt="image-20250128153545627" style="zoom:50%;" />

## Certificazioni KNIME

I corsi vanno da livello 1 a 4; l'1 è gratis. Lui ha dei *coupon* gratuiti per i livelli successivi!

Ogni corso ha risorse online da studiare.

15 domande prese da un pull di 100.

Argomenti missati:

### Path

* ==File system==: un percorso fisico sulla macchina
* ==Mountpoint:== è un path e si riferisce a sistemi linux e unix; è un percorso che permette di caricare file su sistemi remoti.
* ==KNIME URL==: esiste un repository che si chiama Knime Hub dove chiunque può pubblicare risorse; quindi, chiunque può scaricarle da qui
* ==Relative to==: nel workflow knime, oltre al workflow stesso ho anche i dati

### Metanodi

Sono dei raggruppamenti di nodi. Impostando un workflow knime, possiamo raggruppare ad esempio tutti i nodi per la carica dei dati in un metanodo. Questo ci facilita la lettura.







