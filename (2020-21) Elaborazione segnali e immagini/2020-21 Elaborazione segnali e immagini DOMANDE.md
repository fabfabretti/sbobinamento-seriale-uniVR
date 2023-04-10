## Domande di teoria di ESI

### Cosa si intende con rinforzo immagini? Dettagliare un'operazione di rinforzo puntuale.

Con rinforzo si intende, in generale, un tipo di operazione che ha il fine di migliorarne la qualità. Poiché la definizione di "qualità" è dipendente dal contesto, lo è anche il tipo di operazioni considerate tali: per esempio, data un'immagine sottoesposta potrei voler rendere l'immagine più gradevole con un'operazione di equalizzazione, oppure potrei voler essere interessato a evidenziare i dettagli in ombra, e di conseguenza sacrificare il realismo per evidenziare meglio i dettagli.

Esempi di operazioni di rinforzo puntuale:

- **Inversione/Negativo**
  
  - Visivamente, inverte i valori chiari e i valo1ri scuri dell'immagine. E' considerata di rinforzo in quanto, in alcune situazioni particolari, invertire i valori permette di visualizzare meglio i dettagli dell'immagine: è ad esempio il caso delle immagini biomediche. 
  
  - Il valore nuovo per ciascun livello di grigio è calcolato come $s = L-1-r$
    
    dove s è il nuovo valore, r è il valore originario e L è il massimo livello di grigio rappresentabile. 
    
  - La LUT risultante sarà una retta decrescente.
  
- **Clamping**
  
  - Visivamente, limita l'intensità dei valori dell'istogramma a un intervallo a,b. Serve a rimuovere i valori troppo chiari o troppo scuri - per esempio, può ridurre il rumore impulsivo.
  
  -  Il nuovo valore di ciascun livello di grigio è calcolato come
    $$
    s=
    \begin{equation*}
    \left\{
    \begin{array}{l}
    a\ \ \ \text{se}\ r<a\\ 
    r\ \ \ \text{se}\ a\leq r\leq b\\
    b\ \ \ \text{se}\ r>b
    \end{array}
    \right.
    \end{equation*}
    $$
    dove s è il nuovo valore, r il vecchio valore e a,b i due valori che vogliamo limitare.
  
  - La LUT appare come una costante fino ad a, poi la LUT dell'identità fino a b e nuovamente costante fino a L-1.
  
- **Stretching e shrinking**

  - Prende i valori e li restringe o allarga linearmente nel nuovo range. 

  - Il nuovo valore di ciascun livello di grigio è calcolato come
    $$
    s = \bigg[{{r-r_{min}}\over{r_{max}-r_{min}}}\bigg][b-a]+a
    $$
    Dove

    - $r$ = vecchio livello di grigio
    - $r_{min}$ = valore minimo da stretchare
    - $r_{max}$= valore massimo da stretchare
    - $a$ = valore minimo di arrivo
    - $b$ = valore massimo di arrivo

  - La LUT è un'identità che per un certo intervallo è sostituita da una retta con una slope diversa.

- **Logaritmica**

  - Visivamente, dà più valori ai livelli di grigio bassi, dando un effetto di schiarimento e migliorando la percezione dei colori scuri. E' utilizzata sulla mappa di trasformata di Fourier 2D per "compensare" il valore situato in (0,0), che per costruzione della trasformata di Fourier è molto più alto del resto della mappa.
  
  - Il nuovo valore è calcolato come $s = c log(r + 1)$ , dove:
  
    - All'argomento di log aggiungiamo un uno per evitare di avere valori che esplodono a meno infinito
  
    - c è una costante di normalizzazione che riporta il risultato nel range di valori rappresentabili, ed è definita come 
      $$
      c={{L-1}\over{log(L)}}
      $$
      
  
  - La LUT è a forma di logaritmo :) 
  
- **Logaritmica inversa**

  - Visivamente, dà più valore ai livelli di grigio alti.

  - Il nuovo valore è calcolato come $s = ({e^{r}})^{{1}\over{c}}-1$

    Con c costante di normalizzazione uguale alla logaritmica, ovvero 
    $$
    c={{L-1}\over{\log{(L)}}}
    $$

  - La LUT è a forma di esponenziale tbh

- **Trasformazione di potenza**

  - Tipicamente utilizzata per la calibrazione di monitor CRT.
    Per valori di $\gamma < 1$ si riduce alla trasformazione logaritmica.

  - I nuovi valori sono dati da  $s = ce^{\gamma r}$. In realtà, poiché il la costante è molto complessa da calcolare, si preferisce procedere in due passaggi calcolando prima la trasformazione pura come $\tilde s = r^\gamma$ e poi applicando uno stretch lineare per riportare il risultato nel range normale, come 
    $$
    s = \bigg[{{\tilde s-\tilde s_{min}}\over{\tilde s_{max}-\tilde s_{min}}}\bigg]\cdot L
    $$

- **Binarizzazione**

  - Produce un'immagine con due soli livelli di grigio, dividendo i livelli preesistenti in funzione di una soglia T. In generale, funziona bene quando l'immagine è composta da un soggetto in contrasto su uno sfondo uniforme.

    - Per calcolare la soglia T si utilizza il metodo di Otsu, che assume che ci siano due "picchi" nell'istogramma e cerca di separarli trovando iterativamente una T che minimizzi la varianza interna di ciascuna delle due aree.
      In particolare, per ciascun T possibile si vuole minimizzare la formula
      $$
      T = min(W_b(T)\cdot\sigma(T)_b^2 + W(T)_f\cdot \sigma(T)_f^2)
      $$
      con  $W$ = somma dei pixel totali di una zona e $\sigma $=varianza di una zona.

- **Equalizzazione**

  - E' un'operazione venduta come "generale miglioramento dell'immagine"; quello che fa intuitivamente è ridistribuire i livelli di grigio in modo che il contribuito di ciascun livello di grigio sia simile.

  - A livello pratico, quello che facciamo è cercare di rendere la funzione di ripartizione dell'istogramma della nostra immagine il più simile possibile alla funzione di ripartizione ideale - ovvero la funzione di ripartizione dell'istogramma uniforme.

  - I nuovi valori si calcolano come:

    - Per ciascun livello di grigio, calcola la frequenza cumulativa  (=funzione di ripartizione)
    - Moltiplica i valori trovati per il valore massimo di grigio -1
    - Normalizza i valori dividendoli per il numero di pixel dell'immagine (M $\cdot$ N)
    - Arrotondamento 
    - Applicazione del mapping ottenuto all'immagine.

    Questo procedimento si riassume anche nella seguente formula:
    $$
    s_k={{L-1}\over{M\cdot N}}\sum_{j=0}^k H(r_j)
    $$

### Differenza fra operazione di rinforzo locale e puntuale

Un'operazione di rinforzo puntuale è un tipo di operazione nel quale il valore risultante in un pixel dipende esclusivamente dal valore  originario del pixel stesso. Può essere espresso con una LUT. Alcuni esempi sono l'inversione, la trasformazione di potenza o la binarizzazione.

Al contrario, un'operazione di rinforzo locale calcola il risultato anche in funzione dei pixel di un certo intorno del pixel preso in considerazione.  Alcuni esempi sono il filtro di media, mediana.

### Descrivere l'istogramma in versione classica e probabilistica

L'istogramma classico è un tipo di rappresentazione statistica che mostra, per ciascun livello di grigio, la sua frequenza assoluta nell'immagine.

La versione probabilistica si ricava dividendo l'istogramma classico per il numero di pixel dell'immagine e può essere visto come la probabilità di un pixel di avere un certo livello di grigio. 

Entrambi permettono di avere una visione generale dell'immagine (per esempio, mostrano se l'immagine è chiara o scura).

### A che operazioni sono state sottoposte le immagini 2 e 3? A che tipo di rumore è soggetta 1?
![IL BUTEL](image-20210325184607550.png)
- La prima immagine è soggetta a rumore impulsivo, o sale e pepe.
- Le altre due immagini sono state passate rispettivamente per un filtro mediana e per un filtro media.

### Descrivere cos'è un filtro passa-alto

Un passa-alto è un tipo di filtro che rimuove le basse frequenze e preserva le alte frequenze. In generale, il risultato è quello di esaltare le discontinuità forti, come per esempio i bordi, e il rumore.

In Fourier corrisponde a una mappa con valori bassi al centro e valori alti agli estremi.

Può essere espresso come $H_{HP} = 1-H_{LP}$.

Ne esistono diversi tipi:

- **Ideale:** è una box. Ha una frequenza di taglio molto netta ma produce molti artefatti.

- **Gaussiano:** frequenza di taglio poco netta ma dà problemi e sbianca sensibilmente se non viene rispettata la proporzione $W = 5\sigma$, dove $W$ è la dimensione del filtro e $\sigma$ è la varianza della gaussiana. 

- **Butterworth:** l'inclinazione del fronte di taglio è tanto più ripida quanto più alto è l'ordine del filtro, ovvero il polinomio della formula. Produce ringing per ordine > 20.
  $$
  H(u,v)={{1}\over{1+({{D(u,v)}\over{D_0}})^{2n}}}
  $$

### Con che grandezza si misura il rumore?

Il rumore si misura attraverso l'SNR, _signal to noise ratio,_ che quantifica quanto rumore ci sia nell'immagine. Rappresentando l'immagine come
$$
\tilde f(n,m) =f(n,m)+ \varepsilon(n,m)
$$
Allora un SNR alto, in generale, indica un'immagine poco rumorosa. L'SNR può essere formulato in diversi modi:

- **Scarto quadratico**: 
  $$
  SNR = {{\sum_{m=1}^M\sum_{n=1}^N\tilde f(n,m)^2}\over{\sum_{m=1}^M\sum_{n=1}^N(\tilde f(n,m)-f(n,m))^2}}
  $$

- **Varianza**:
  $$
  SNR_{\sigma} = {{\sigma_{\tilde f}}\over{\sigma_e}}
  $$

### Cosa rappresenta la LUT?

La LUT rappresenta un'operazione puntuale in forma di tabella, dove mostriamo il mapping fra i livelli di grigio in ingresso e in uscita. Possiamo rappresentarvi operazioni quali il negativo, lo stretching, il clamping o l'equalizzazione.



