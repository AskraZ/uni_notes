# Ricorsione 
---
> [!abstract] Cos'è la Ricorsione
> La ricorsione è una tecnica utilizzata negli algoritmi e nelle strutture Dati in cui si va a richiamare la funzione più volte fino ad arrivare ad un caso base.

Ecco un esempio basico dell'utilizzo della ricorsione, applicato al calcolo fattoriale:
$$n! = \begin{cases}1 & se \ n=0 \\  n\cdot(n-1) & se \ n>0\end{cases}$$
> [!tip] 
> In breve diciamo che per calcolare il Fattoriale di $n$ ci basta saperlo fare per $n-1$, arrivando al caso base e ricostruendo all'insù.

**LE DUE FASI DELLA RICORSIONE**
- *Fase di Suddivisione:* si suddivide il problema in tanti piccoli problemi che si fermano al caso base. 
- *Fase di Ricombinazione:* si ricompongono i risultati della fase precedente per arrivare alla prima chiamata.

**STRUTTURE DATI DEFINITE RICORSIVAMENTE**
- Lista: un elemento iniziale $n$ seguito da una lista dello stesso tipo.
$$Lista=\begin{cases}
Lista\ vuota,  & oppure \\
(Elemento, Lista) & \text{se contiene almeno un elemento} 
\end{cases}$$
- Array: Un array di lunghezza $n$ può essere definito come un elemento $m$ seguito da un array di lunghezza $n-1$
$$A[]_{Ricorsivo}=m\cup A_{n-1}$$
- Alberi: ogni nodo dell'albero può essere considerato come la radice di un nuovo albero.
$$Albero=\begin{cases}
\text{nodo vuoto}, & \text{(Albero nullo)} \\
\text{(valore, sottoalbero sinistro, sottoalbero destro)},  & \text{(albero non vuoto)}
\end{cases}$$
**STRUTTURE GENERALE DI UN PROGRAMMA RICORSIVO** 
1. Caso base: la condizione che ferma l'algoritmo dall'andare all'infinito.
2. Passo Ricorsivo: sezione dove la funzione chiama sé stessa per suddividire il problema.
3. Combinazione: Unione di tutti i risultati per risolvere il macro-problema.
---
### COMPLESSITA' COMPUTAZIONALE
### STIME ASINTOTICHE
![[differenza-notazione-o-omega-theta.gif]]
>[!hint] Notazione $\theta$ 
indica il caso medio, ovvero l'insieme di tutte le funzioni che crescono alla stessa velocità di una funzione di riferimento $g(n)$.
$$\theta(g(n))=\{f(n)|\exists c_{1},c_{2},n_{0}>0 \ \text{tali che} \ 0\leq c_{1}g(n)\leq f(n)\leq c_{2}g(n), \forall n\geq 0\}$$

![[big-theta-tight-bound-graph.png]]

>[!Hint] NOTAZIONE $O$
indica il peggior scenario possibile, ovvero un limite che la funzione può raggiungere ma non supera mai.
$$O(g(n))=\{f(n)|\exists c>0,n_{0}>0 \ \text{tali che}\ 0\leq f(n)\leq cg(n), \forall n > n_{0}\}$$

>[!Hint] NOTAZIONE $\Omega$
con la notazione $\Omega$ indichiamo il caso migliore che la funzione può assumere.
$$\Omega(g(n))=\{f(n)|\exists c>0,n_{0}>0 \ \text{tali che } 0\leq cg(n)\leq f(n),\forall n>n_{0}\}$$

**EQUAZIONE DI RICORRENZA**
Un equazione di ricorrenza descrive la performance di un algoritmo con dimensione $n$:
$$T(n)=\sum_{i=0}^{K}T(n_{i})+f(n)$$
dove $T(n_{i})$ rappresenta il tempo necessario per risolvere il sotto problema $i-esimo$ e $f(n)$ rappresenta il tempo impiegato per la fase di divisione e ricomposizione.
**COSTRUZIONE DI UN EQUAZIONE DI RICORRENZA**
> [!example] 
> **Fattoriale**: ad ogni chiamata il problema riduce di $1$ la sua dimensione, quindi 
> $T(n)=T(n-1)+O(1)$
> **Somma di un Array**: se dividiamo l'array in due, allora avremo $T(n)=2T\left( \frac{n}{2} \right)+O(1)$
> **Merge Sort**: Ogni livello di ricorsione prevede una divisione in due sottoarray, ma la fase di merge richiede tempo lineare.
> $T(n)=2T\left( \frac{n}{2} \right)+O(n)=O(n\log n)$
#### ALBERO DI RICORSIONE 
Ricordiamo l'equazione generale di Ricorrenza: $T(n)=aT\left( \frac{n}{b} \right)+f(n)$
- La radice corrisponde al problema iniziale di dimensione $n$
- i nodi interni rappresentano le chiamate ricorsive generate a ciascun livello
- ogni nodo è etichettato con il costo del lavoro locale $f(n_{1})$ dove $n_{1}$ è la dimensione del sotto-problema.
- i figli di un nodo rappresentano le chiamate generate dal quel nodo.
quindi l'albero di ricorsione si calcola con $$\sum_{i=0}^{h}a^{i}f\left( \frac{n}{b^{i}} \right)$$  ![[OIP.webp]]
#### METODO DELLA SOSTITUZIONE 
>[!warning] metodo che all'esame viene richiesto per dimostrare il risultato 

Questo metodo consiste nel formulare un ipotesi sulla forma asintotica della soluzione e dimostrare che l'ipotesi è corretta con un ragionamento induttivo.
**STEP DA SEGUIRE**
1. si formula un ipotesi del comportamento asintotico (con il teorema master)
2. si sostituisce l'ipotesi nell'equazione generale di ricorrenza 
3. Se necessario si aggiusta l'ipotesi e si riparte da (1)
>[!example] Esempio 1 - Ricerca Binaria
> consideriamo l'equazione della ricerca binaria trovata prima: $T (n) = T \left(  \frac{n}{2} \right) + 1$ 
> L'intuizione (l'albero di ricorsione) $n$ suggerisce una crescita logaritmica.
> Supponiamo quindi: $T (n) \leq c log_{2} n$ sostituendo otteniamo che:
>  $T (n) \leq c log_{2} \frac{n}{2} + 1 = c(log_{2} n − 1) + 1 = c log_{2} n − c + 1$ Affinché la disuguaglianza 
>  $T (n) \leq c log_{2} n$ sia rispettata, è sufficiente che: $−c + 1 \leq 0$ cioè $c \geq 1$Anche in questo caso la nostra ipotesi è coerente ed è $T (n) = O(\log n)$
#### TEOREMA MASTER 
$$T(n)=aT\left( \frac{n}{b} \right)+F(n)$$
$F(n)\to$ corrisponde al lavoro fatto alla radice dell'albero $n^{\log_{a}b}$
> [!info] 
> 1. $F(n)\in O(n^{\log_{b}a-\epsilon})\to T(n)\in \theta(n^{\log_{b}a})$
> 2. $F(n)\in \theta(n^{\log_{b}a}\log^{k}n)\to T(n)\in \theta(n^{\log_{b}a}\log^{k+1}n)$
>3. $F(n)\in \Omega(n^{\log_{b}a+\epsilon})\to T(n)\in \theta(F(n))$
> $\exists c<1:af\left( \frac{n}{b} \right)\leq cF(n)$

**ESEMPI** 
**Ricerca Binaria** $T(n)=T\left( \frac{n}{2} \right)+1$
$F(n)=1=n^0$
$a=1, b=2\to\log_{2} 1=0=n^0=1$
$n^{0}\in \theta(n^{0}\log^{k}n)\to T(n)\in (\log n)$
**Merge Sort**
$T(n)=2T\left( \frac{n}{2} \right)+n$ 
$a=2, b=2$
$F(n)=n^{1}$  $n^{\log_{b}a}=n^1$
$n^{1}=T(n)\in\theta({n^{1}\log^{k}n})\to T(n\log n)$
**Algoritmo di Strassen**
$T(n)=7T\left( \frac{n}{2} \right)+n^{2}$
$a=7, b=2$
$F(n)=n^{2}$
$\log_{2} 7=n^{\log_{2} 7}$
$T(n)\in\theta(n^{\log_{2} 7)}$
**Generico**
$T(n)=T\left( \frac{n}{2} \right)+n$  $a=1, b=2$
$F(n)=n^{1}$ $n^{\log_{2} 1}=n^{0}$
$T(n)\in \theta(n)$
**Generico**
$T(n)=2T\left( \frac{n}{4} \right)+n$
$a=2,b=4$
$F(n)=n$ 
$\log_{4} 2<n^1$
$aF\left( \frac{n}{b} \right)\leq cn$ 
$T\left( \frac{n}{4} \right)<c\frac{n}{4}$
---
