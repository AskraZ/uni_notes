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
>$[a_{1},a_{2},a_{3},\dots,a_{n}]=\begin{cases}[a_1,a_2,a_3] <\\ < [a_{4},a_{5},a_{n}]\end{cases}\to [a_{1},a_{2},a_{3},\dots,a_{n}]$
 