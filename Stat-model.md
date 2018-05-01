## Lezione 1 - Stat model
### 5-03-2018

*prof. Vittadini*


Intro:
Il corso comprende 3 argomenti:
+ modello lineare classico e estensione
+ modello lineare multivariato
+ applicazione di questo modello su dati gerarchici

Lezioni teoriche (con approccio pratico) e laboratori (SAS e R) + tutor (daniele.riggi@gmail.com).

Esame:
2 domande teoriche tra 15 preordinate (bastano le slide, possibilità di approfondire sui libri indicati).
Esercizio da svolgere in classe o con SAS o con R.

Lezio:
1. Descrizione delle variabili e metriche.
2. Pulizia dei dati.
3. Statistiche descrittive: media, mediana, primo e terzo quantile, min e max, matrice di correlazione (eliminare variabili fortemente correlate, in quanto possono avere un'influenza negativa sul modello), scatter plot.
4. Costruzione di un modello statistico.

Quali sono gli indici che mi dicono se ho sviluppato un buon modello?
+ adattamento dei dati (fit dei dati)
+ semplicità del modello (numero dei parametri). Un modello serve per capire di più riguardo ad un fenomeno e non per complicarlo (parsimonia).

Qual è la differenza tra modello matematico e statistico?
$\rightarrow$ Incertezza. Il modello statistico è caratterizzato dall'errore. L'errore considera la variazione individuale.
$\rightarrow$ Variabili esplicative che possono essere considerate per migliorare il modello (quindi diminuire l'errore).
$\rightarrow$ Nel caso stocastico errori nel rapporto campione-popolazione.

Il lavoro nel costruire un modello statistico sta sia nel diminuire l'errore ma anche nel capire da dove nasce.

Come nasce l'elaborazione di un modello statistico?

+ Teoria, Ovvero formulazione di ipotesi, scoperta di relazion empiriche o rapporti di causa effetto tra variabili. Individuazione delle variabili esplicative.
+ Dati. Capire quale metodo di raccolta utilizzare in base anche alla disponibilità economica che si ha per sviluppare il modello. Trattamenti preliminari (pulizia ecc.) e poi tornare al modello. Tenere conto dell'eterogeneità dei dati (es. considerando per esempio il livello di pericolosità delle acque di un lago, se valutiamo tutte le aprticelle nella loro totalità potremmo non concludere che le acque sono pericolose, questo potrebbe infatti risultare valido nella sua totalità ma magari identifichiamo delle zone in cui avvengono più morti rispetto alla normalità. Questo perchè ci potrebbero essere delle zone maggiormente inquinate che non emergono da un'analisi totale delle acque. Quindi considerare anche campionamenti di questo tipo , utilizzare tutti i dati potrebbe non dirici nulla). In questa fase rientra anche una prima analisi preliminare dei dati.
+ Specificazione del modello (Probabilistico o descrittivo)
+ Stima dei parametri e verifica dell'adattabilità ai dati
+ Utilizzo 

Ripetere più volte (se necessario).

*Oss.*
Oggi un problema nella costruzione di un modello è anche la privacy. Ci sono modelli che potrebbero essere molto interessanti ma non si possono elaborare per problemi di privacy. Quindi devo usare il modello che ho per correggere i dati in questo senso (Teoria $\rightarrow$ Dati). Vale però anche il contrario, ovvero i Dati aiutano nell costruzione di un modello ($\Rightarrow \text{Dati} \rightarrow \text{Teoria}$)

Il modello di base è il *modello di regressione*. La regressione può essere *semplice*, *multipla* o *multivariata*.
*Semplice*, se si ha una sola variabile dipendente ed una sola variabile esplicativa.
*Multipla*, se si hanno più variabili esplicative e una sola dipendente.
*Multivariata*, se si ha più di una variabile esplicativa e più di una variabile dipendente.

**Stima**, ovvero trovare i parametri per il modello. Uno dei metodi di stima è quello di *regressione lineare*.

**Verifica** dei risultati sia in termini descrittivi (adattamento ai dati), poi test statistici sulla significatività. Se la verifica non conduce ad un rifiuto del modello stimato allora lo si utilizza altrimenti si torna alla ase di specificazione.

### Regressione multipla
Può essere espressa in termini matriciali. È costrutita a partire dal vettore delle x e dal vettore delle y. La prima colonna è composta da 1.
Come metodo di stima si utilizza il *metodo dei minimi quadrati*. La bontà di adattamento si stima in base a *devianza totale* e *devianza spiegata*.

*Oss.*
È necessario fare campioni anche nel caso in cui abbiamo molti dati, in quanto se ho molti dati la regione di accettazione diventa piccolissima

### Modello lineare classico
Estensione della regressione al caso stocastico.
Regole **necessarie** per avere un modello (che valgono sempre):
+ **Ipotesi di linearità**.
+ **Ipotesi di non sistematicità degli errori**. Vale per tutti i modelli, l'errore è considerato casuale ed ha valore atteso 0 (si aggira lì intorno), altrimenti è sistematico. 
+ **Sfericità degli errori**
	+ Non collinearità. Affinchè matrice dei minimi quadrati abbia un'inversa unica $x'x$ deve essere uguale al rango. Se c'è collinearità non ho soluzione unica del modello, questo perchè due variabili sono appunto colineari (si è inserita due volte la stessa variabile oppure una combinazione linearmente dipendente).
	+ Numerosità. Il numero di elementi nel campione che si sta utilizzando deve essere maggiore del numero dei parametri.