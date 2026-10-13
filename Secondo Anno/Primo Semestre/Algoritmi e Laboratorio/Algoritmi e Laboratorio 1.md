ESAME: PROVA SCRITTA (DOMANDE APERTE) E ORALE
# 02/10/26 
> **Heap** = Coda con priorità.
> **Problemi di Ottimizzazione** = Categoria di problemi dove si cerca la soluzione migliore tra quelle disponibili.
### ORDINAMENTO

$A=<a_{1},a_{2},a_{3},a_{n}>$ è una sequenza di Input.
$A'= <a_{i_{1}},a_{i_{2}},\dots,a_{i_{n}}>$ con  $\forall 0<j\leq n\implies a_{i_{j}}\leq a_{i_{j+1}}$

---
>**SELECTION SORT**
>$O(n^2)$
``` Python
FOR p<--m downto 1 do
M <- Max(A,p)
SWAP(A,P,M)

\\ RICORSIVO
IF (n > 1) THEN
M = MAX(A,n)
SWAP(A,M,n)
SELECTIONSORTRIC(A,n-1)

```

>**INSERTION SORT**
``` python
FOR i <- 2 TO n DO
j <- i + 1
WHILE(j>1 && A[j-1]>A[J])
	SWAP(A[j-1], A[j])
	J <- J - 1
	
\\ RICORSIVO
IF n > 1 THEN
INSERTIONRIC(A, n-1)
j = n
WHILE(j>1 && A[J-1]>A[j]) DO
SWAP(A, j-1, j)
j = j - 1
![[Recording 20261002105853.m4a]]

```

**Algoritmi di Ordinamento in Loco**: Algoritmi che non allocano ulteriore memoria oltre a delle variabili temporanee.
**Stabilità**: Un algoritmo è stabile se dati $n$ elementi con lo stesso valore, mantiene l'ordinamento relativo tra questi $n$ elementi.
$$[5_{a},3_{a},6_{a},3_{b},5_{b},3_{c},6_{b},5_{c}]\to[3_{a},3_{b},3_{c},5_{a},5_{b},5_{c},6_{a},6_{b}]$$

**Adattività**: 

## RICORSIONE 
$P$ è un problema con dimensione $n$.
$P(n)=\begin{cases}P \\  P_{2} \\  P_{3} \\  \dots \\  P_{k}\end{cases}=S$

Soluzione di $P(n)=S$
 >**MERGE SORT**
 >$[a_{1},a_{2},a_{3},\dots,a_{n}]=\begin{cases}[a_1,a_2,a_3] \\  [a_{4},a_{5},a_{n}]\end{cases}\to merge\to [a_{1},a_{2},a_{3},\dots,a_{n}]$

>**QUICK SORT**
>$[a_{1},a_{2},a_{3},\dots,a_{n}]=\begin{cases}[a_1,a_2,a_3] <\\ < [a_{4},a_{5},a_{n}]\end{cases}\to [a_{1},a_{2},a_{3},\dots,a_{n}]$ ---

**Calcolo Fattoriale**
$n! =1\cdot 2\cdot 3\cdot \dots,\cdot n$
```C
// versione iterativa
FATT(n)=n!
F = i
FOR i <- 2 TO n DO
F <- F x i
RETURN F
```

$$n! = \begin{cases}
1 & se \ n=1 \\
n(n-1)! & se  \ n>1
\end{cases}$$
```C
FATT(n)
IF (n==1) THEN RETURN 1
RETURN n x FATT(n-1)
```

Si viene a creare un albero di ricorsione.

---
**Array Ricorsivo**

$\array{n}=\begin{cases} null & se \ n=0\\ Array[n-1] & se\ n > 0 \end{cases}$
---
**Sequenza di Fibonacci**
```
FIB(n)
IF n<=2 2 THEN RETURN 1
RETURN FIB(n-2)+FIB(n-1)
```
![[FibTree.gif]]
 **QUICK SORT**   
``` Python
// versione ricorsiva
QUICKS(A,i,j) 
m <- Partition(A,i,j); 
QUICKS(A,i,m); 
QUICKS(A,m,j);
``` 

```python
QUICKS(A,n)
i = 1;
j = n;
WHILE (i < j) DO


```

**Problema Dello Zaino**
$A=\{a_{1},a_{2},a_{3},\dots,a_{n}\}$
$\forall 1\leq i \leq n\implies P_{i}=1$
$S\subseteq A$
$S=\max\left\{ \sum_{a_{i}\in S}v_{i}:|S|\leq k  \right\}$
$k=$ peso massimo dello zaino.
Un ladro entra in una casa con uno zaino che ha $k$ massima resistenza di peso.
Nella casa ci sono $n$ oggetti di valori differenti ma di stesso peso.

$$Zaino(A,n,k)=\begin{cases}0 & k=0 \\  v_{n}+Zaino(A,n-1,k-1)\end{cases}$$
```C
Zaino(A,n,k)
IF n==0 OR k==0 RETURN 0
RETURN $v_n$ + Zaino(A,n-1,k-1)
```

---
Modifichiamo una proprietà, i pesi adesso sono differenti.
$$Zaino(A,n,k)=\begin{cases}
0 & se\ n=0\ || \ k= 0 \\ \\
\max\{v_{n}+Zaino(A,n-1,k-P_{n}),Zaino(A,n-1,k)\}
\end{cases}$$
$A=\{a_{1},a_{2},a_{3},a_{4}\}$
$P=\{5,6,3,2\}$
$v=\{10,2,5,9\}$
