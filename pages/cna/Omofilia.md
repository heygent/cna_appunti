tags:: cna
date:: [[2023-03-08]]
slide:: ![ns04](../assets/ns04.pdf)
ref:: ((64672afd-0fbd-499d-9a14-2a2c062919d3)), ((64673c06-91c0-4205-b32c-15fbcc9061dd))

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
  id:: 6465f708-5ab9-4d1a-a685-ad4cdeb70286
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
- # Misure di omofilia
  id:: 631cae09-e42e-4970-ad68-65042e72e647
	- L'idea è che se abbiamo una rete creata da dati reali e vogliamo capire se un tratto è caratterizzante di quella rete, dobbiamo compararla con una rete in cui lo stesso tratto è distribuito casualmente.
	- ((646877dc-bace-4f28-93e9-a1b4bf28afa8))
	- Si supponga di avere una rete in cui una frazione $p$ degli individui sono uomini, e una frazione $q$ sono donne.
	- Si consideri un arco casuale in questa rete. Se le etichette "uomo" e "donna" fossero assegnate casualmente rispettivamente con probabilità $p$ e $q$:
		- L'arco avrebbe entrambi gli estremi etichettati con "uomo" con probabilità $p^2$.
		- L'arco avrebbe entrambi gli estremi etichettati con "donna" con probabilità $q^2$.
		- L'arco avrebbe un estremo "uomo" e uno "donna" con probabilità $2pq$.
	- Se la frazione degli archi tra nodi diversi è significativamente inferiore di $2pq$, allora si ha un'indicazione di presenza di omofilia nella rete.
	  background-color:: red
	- ## Modularità #card
	  id:: 6468a11b-78cd-4b64-9e79-96d84f382f47
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-06-13T22:00:00.000Z
	  card-last-reviewed:: 2023-06-13T07:54:34.231Z
	  card-last-score:: 1
		- id:: 646a363f-b4cd-422d-9596-e37857062559
		  $$Q = \frac1{2m} \sum_{ij} \left(a_{ij} - \frac{k_i k_j}{2m} \right) \delta_{g_i g_j}$$
			- Misura delle connessioni tra nodi dello stesso tipo nella rete.
				- ha valori positivi quando ci sono più archi tra nodi dello stesso tipo di quanti ce ne aspetteremmo casualmente e negativo quando ce ne sono meno.
				- strettamente minore di 1
			- ### Spiegazione
				- ((6468aa5d-6b95-47aa-b2cf-68d6a45cc1e7))
				- Gruppo, classe, o tipo del nodo $i$
					- $g_i = 1 \ldots N$
				- **A**: Numero totale di archi tra nodi dello stesso tipo:
				  id:: 6468a1da-2604-4279-86ca-39e28120d040
					- id:: 6468e6fc-4229-42d3-b6c3-97afbd7ce202
					  $$\sum_{\text{edges}(i,j)}\delta_{g_i,g_j} = \frac{1}{2} \sum_{ij} a_{ij} \delta_{g_i, g_j}$$
						- $a$ è la ((646275b2-7887-4bef-83fa-dbaf2a264cd5))
						- $\delta_{g_i, g_j}$ è il ((6468a99e-a984-462c-a747-3d5e2fd3f54c)):
							- $$\delta_{ij} = \begin{cases} 0 & \text{se } i \neq j \\ 1 & \text{se } i = j \end{cases}$$
						- $\frac12$ fa sì che gli archi non vengano contati due volte ($i,j$ e $j,i$)
				- **B**: Numero atteso di archi tra coppie di nodi dello stesso tipo se i gruppi fossero assegnati causalmente:
					- id:: 64691261-7fd7-429e-bf6f-142e0820e585
					  $$\frac12 \sum_{ij} \frac{k_ik_j}{2m}\delta_{g_i,g_j}$$
						- Si consideri un arco che parte da un nodo $i$, di ((6422fb58-b14c-4f73-a8ce-c547d160c906)) $k_i$
						- Nella rete, ci sono per definizione $2m$ estremi di archi, dove $m$ è il numero di archi
						- La probabilità che all'altro estremo dell'arco ci sia uno dei $k_j$ estremi legati al nodo $j$ è $k_j/2m$
						- Contando $k_i$ archi connessi a $i$, il numero atteso di archi tra i vertici $i$ e $j$ è $k_i k_j/2m$
				- Modularità = (**A** - **B**) / $m$
			- **non raggiunge il valore 1, neanche per una rete perfettamente mescolata**
				- **rete perfettamente mescolata**
				  id:: 646a384b-eeb7-4ccf-8642-114eda9a0676
					- rete in cui ogni nodo è connesso solo a nodi dello stesso tipo
				- a seconda della dimensione dei gruppi e del grado dei nodi, il massimo valore di $Q$ può essere considerevolmente inferiore a 1
	- ## Coefficiente di assortatività #card
	  id:: 646a34c7-d0c3-458b-a08d-6a63272ed5ef
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-06-13T22:00:00.000Z
	  card-last-reviewed:: 2023-06-13T07:48:45.297Z
	  card-last-score:: 1
		- Normalizzazione della ((6468a11b-78cd-4b64-9e79-96d84f382f47)) rispetto al suo valore per una ((646a384b-eeb7-4ccf-8642-114eda9a0676)).
		- ### Spiegazione
		  collapsed:: true
			- Data la modularità per una qualunque rete $Q$ si vuole ricavare il valore della modularità per una rete perfettamente mescolata $Q_\text{max}$:
				- ((646a363f-b4cd-422d-9596-e37857062559))
			- in una rete perfettamente mescolata tutti gli archi cadono tra nodi dello stesso tipo
				- $\delta_{g_i g_j} = 1$ ogni volta che $a_{ij} = 1$
				- Il primo termine nella somma diventa $2m$
			- $$Q_\text{max} = \frac1{2m}\left(2m - \sum_{ij} \frac{k_i k_j}{2m} \delta_{g_i g_j}\right)$$
		- $$\frac{Q}{Q_\text{max}} = \frac{\sum_{ij} (A_{ij} - k_i k_j / 2m) \delta_{g_i g_j}}{2m - \sum_{ij}(k_i k_j / 2m) \delta_{g_i g_j}}$$
		- Questa quantità assume valore 1 in una rete perfettamente mescolata.
		- ### Feature scalari
			- #### Spiegazione
			  collapsed:: true
				- Sia $x_i$ il valore di una quantità scalare di interesse per un nodo $i$ (età, reddito, ecc.)
				  id:: 646a68e5-a507-47da-b64e-2d664bf3828b
				- Si consideri la coppia di valori $(x_i,x_j)$ per i nodi agli estremi di ogni arco $(i, j)$ nella rete.
				- Si definisce la media $\mu$ del valore di $x_i$ alla fine di un arco come segue:
					- ((646a6a08-234e-4188-ba1d-4318183b2284))
						- La media non è sui nodi, ma sugli archi ed è pesata con il grado.
				- Covarianza di $x_i$ e $x_j$ sugli archi:
					- $$\text{cov}(x_i,x_j) = \frac1{2m}\sum_{ij}\left(A_{ij} - \frac{k_i k_j}{2m} \right) x_i x_j$$
				- Si normalizza sulla base di una ((646a384b-eeb7-4ccf-8642-114eda9a0676)), dove gli archi esistono solo su valori precisamente uguali di $x_i$ (molto raro in pratica). Ponendo $x_i = x_j$ la covarianza per una rete perfettamente mescolata è:
					- ((646a6ea8-8ebb-4f8f-9d8b-44051eb68879))
			- ((646a472e-3ec0-4fd5-9fad-b8672ed19e91))
			- È un esempio di coefficiente di correlazione di Pearson
	- ## Coefficiente di assortatività per grado #card
	  id:: 646a7190-a9b7-458f-8088-358dbb593cee
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-06-13T22:00:00.000Z
	  card-last-reviewed:: 2023-06-13T07:52:03.901Z
	  card-last-score:: 1
		- Si prende il grado come feature scalare di ogni nodo:
			- ((646b3490-2f6a-46e3-a5f8-c12f77d8ab3f))
		- ### Struttura core-periphery
			- ((646c7fc0-5655-45df-8a7c-88c4049ad668))
			- In reti assortative per grado, dove nodi di grado alto tendono a essere connessi insieme, ci si aspetta di trovare un mucchio o **nucleo** di nodi di grado alto, circondati da una **periferia** meno densa di nodi di grado più basso
		- ### Struttura hub-and-spoke
			- ((646c7fdb-ab7c-49bb-8f8d-26817dd43eb6))
			- In reti non assortative per grado, i nodi di grado alto tendono a essere connessi a nodi di grado basso, creando strutture simili a stelle.
	- ## Degree correlation function
		- TODO ((646cd94d-1e7a-4cbc-aa31-898531c52ead))
		  :LOGBOOK:
		  CLOCK: [2023-05-23 Tue 17:18:55]--[2023-05-23 Tue 17:18:56] =>  00:00:01
		  CLOCK: [2023-05-23 Tue 17:18:59]--[2023-05-23 Tue 17:18:59] =>  00:00:00
		  CLOCK: [2023-05-23 Tue 17:18:59]--[2023-05-23 Tue 17:19:00] =>  00:00:01
		  :END:
- # Meccanismi sottostanti all'omofilia
  id:: 631cb450-b46e-427f-9747-442e03094845
	- Ci sono due meccanismi naturali per cui l'omofilia emerge:
		- **selezione**
		  id:: 631cbf8f-e240-4708-8447-f7a31eeb87f5
			- nodi simili diventano connessi
		- **influenza sociale**
		  id:: 631cbf9d-a8db-4f12-82e5-d747a71df7b5
			- nodi connessi diventano più simili
	- Può essere una cosa negativa. **Echo chambers** e **groupthink** sono situazioni dove i tuoi amici sono come te, la diversità è annientata, e sei esposto solo a opinioni che rafforzano le tue convinzioni preesistenti.
- # Reti di affiliazione
  id:: 631cc01b-8f07-470d-9924-40500a8a9d40
	- Possiamo rappresentare anche il ((631ca982-e61b-49de-8149-c2cd1801cace)) tramite reti
	- **FOCI**
		- punti focali, indicano attività, opinioni o affiliazioni di individui
	- **rete di affiliazione**
		- ((64368a97-1853-46f2-946d-aba0b766a52e))
		- $$
		  G = (U, V, E) \\
		  \forall(u, v) \in E : u \in U \land v \in V
		  $$
	- ((64632a86-5ed9-4a21-a210-fc4345e425d0))
	- **rete di affiliazione sociale**
		- rete in cui i dati sui rapporti sociali e sui FOCI vengono uniti.
	- ## Proiezioni
	  id:: 64691261-1cc5-4b32-847b-5b8396942cb0
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