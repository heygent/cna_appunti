tags:: cna
date:: [[2023-03-08]]
slide:: ![ns04](../assets/ns04.pdf)

- # Contesto circostante
	- **contesto circostante**
	  id:: 631ca982-e61b-49de-8149-c2cd1801cace
		- fattori che esistono al di fuori dei nodi e degli archi di una rete ma che possono avere effetto sull'evoluzione del sistema.
	- Ci concentriamo su:
		- **proprietà strutturali**
			- come i nodi sono collegati a vicenda
		- **processi di formazione dei link**
			- come si formano i link
			- questo ci permette di introdurre modelli predittivi di quali link si formino rispetto ad altri
		- **caratteristiche personali**
			- le proprietà strutturali vengono collegate a caratteristiche personali (come ponti e legami deboli) e con questo otteniamo **similarità tra individui**
- # Omofilia
	- Il principio per cui tendiamo a essere simili ai nostri amici.
		- Incontrando qualcuno casualmente al di fuori del nostro circolo sociale la probabilità è alta che questa persona sia diversa da me.
		- Questo fa sì che i tuoi amici non siano significativi come campione casuale di una popolazione.
	- Similarità:
		- **caratteristiche immutabili**
			- gruppo etnico di appartenenza
		- **caratteristiche mutabili**
			- interessi in musica, film, ecc.
	- ((6463296a-522a-474e-91b5-f2b3f50b4bf5))
		- Ci sono diversi tratti (rappresentato da un colore) e vogliamo contare
			- i **link intragruppo** tra nodi con lo stesso tratto.
			- i **link intergruppo** tra nodi con tratti diversi.
		- Strutturalmente parlando, l'idea è:
			- se osservo che il numero di link intragruppo è molto maggiore dei link intergruppo, allora abbiamo **omofiliia**
			- questo significa che è molto più probabile che ci sia una connessione tra due nodi simili che tra due nodi diversi.
	- ## Misurare l'omofilia
	  id:: 631cae09-e42e-4970-ad68-65042e72e647
		- Tre passi:
			- assegnare un colore casuale a ogni nodo
			- contare il numero di archi tra colori diversi
			- comparare il numero con la rete reali
		- L'idea è che se abbiamo una rete creata da dati reali e vogliamo capire se un tratto è caratterizzante di quella rete, dobbiamo compararla con una rete in cui lo stesso tratto è distribuito casualmente.
- # Meccanismi sottostanti all'omofilia
  id:: 631cb450-b46e-427f-9747-442e03094845
	- Ci sono due meccanismi naturali per cui l'omofilia emerge:
		- **selezione**
		  id:: 631cbf8f-e240-4708-8447-f7a31eeb87f5
			- nodi simili diventano connessi
		- **influenza sociale**
		  id:: 631cbf9d-a8db-4f12-82e5-d747a71df7b5
			- nodi connessi diventano più simili
	- Può essere una cosa negativa. **Echo chambers** e **groupthink** sono situazioni dove i tuoi amici sono come te, la diversità è annientata, e sei esposto solo a opinioni che rinforzano le tue convinzioni preesistenti.
- # Reti di affiliazione
  id:: 631cc01b-8f07-470d-9924-40500a8a9d40
	- Possiamo rappresentare anche il ((631ca982-e61b-49de-8149-c2cd1801cace)) tramite reti
	- **FOCI**
		- punti focali, indicano attività, opinioni o affiliazioni di individui
	- **rete di affiliazione**
		- grafo bipartito
		- $$
		  G = (U, V, E) \\
		  \forall(u, v) \in E : u \in U \land v \in V
		  $$
	- ((64632a86-5ed9-4a21-a210-fc4345e425d0))
	- **rete di affiliazione sociale**
		- rete in cui i dati sui rapporti sociali e sui FOCI vengono uniti.
	- ## Proiezioni
		- Metodo per complementare una rete di affiliazione con una rete sociale.
		- ((64632af3-0948-406b-b883-1d2af50a11b2))
			- Proiezione 1: rete di interazione tra membri delle compagnie
				- ((64632b62-4ad0-49f8-8a63-b89abccd0ef2))
			- Proiezione 2: rete di interazione tra compagnie
				- ((64632b72-7fb6-448f-a441-d25d9b508b78))
	- ## Chiusure
		- ### Friendship transitivity
			- ((64632b9a-ef30-417a-838d-7e4e7ae2deaa))
			- amicizie nate per ((64625526-7abe-416b-8538-8f2d05123946))
		- ### Focal closure
			- ((64632bb0-bba8-4417-899d-1eff21a0bb04))
			- $A$ è un focus (attività) e $B$ e $C$ sono individui connessi a quest'attività.
			- Possiamo predire che $B$ e $C$ prima o poi diventeranno amici.
			- Questa chiusura avviene per ((631cbf8f-e240-4708-8447-f7a31eeb87f5))
		- ### Membership closure
			- ((64632bd6-9e4d-4f70-ab77-0e923ffcfb59))
			- $A$ e $B$ sono connessi da una relazione, e $A$ ha un focus
			- Si può predire che $B$ interagirà con lo stesso focus
			- Questa chiusura avviene per ((631cbf9d-a8db-4f12-82e5-d747a71df7b5))
-