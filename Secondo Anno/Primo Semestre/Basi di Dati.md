Canale di Comunicazione: moodle
Esame: Prova Scritta + Progetto 
Itinere:
# 02/10/26
Un database è un insieme organizzato di dati che si evolvono nel tempo.
**DBMS** è un sistema software in grado di gestire collezioni di dati che sono:
- Grande dimensione
- Persistenti
- Condivise
---
**PROBLEMI**: Ridondanza (Informazioni Ripetute), Incoerenza (Informazioni non coincidono).
# 05/10/26
Siano $T_{1},T_{2},T_{3}$ tipi primitivi e $A_{1},A_{2},A_{3}$ etichette allora:
$\{A_{1}:T_{1},A_{2}:T_{2},A_{n}:T_{n}\}$ è detta una **n-upla di grado $n$.**
Il tipo di $A_{n}$ dev'essere uguale a $T_{n}$.

>La cardinalità di una relazione è il numero di n-uple presenti.

![[screenshot-2026-10-05_11-37-06.png]]
**VINCOLI DI INTEGRITA'**
1. Attribuzione di *Null*
2. Quali Attributi sono *Chiave*
3. Quali Attributi sono *Chiavi esterne*
**CHIAVI**
Diremo che $X$ è una superchiave se ogni istanza valida dello schema non contiene due record $t_{1}$ e $t_{2}$ con $t_{1}[X]=t_{2}[X]$
Una chiave è una superchiave minimale se rimuovendo degli attributi la proprietà non persiste.
Chiave $=$ Superchiave minimale
![[screenshot-2026-10-05_11-50-08.png]]
**CHIAVE PRIMARIA**

**CHIAVE ESTERNA**
## ALGEBRA RELAZIONALE 
OPERATORI:
- RIDENOMINAZIONE
- UNIONE
- DIFFERENZA
- PROIEZIONE
- RESTRIZIONE (O SELEZIONE)
- PRODOTTO
**RIDENOMINAZIONE**
$$\delta Matricola\to Codice \ studente(STUDENTE)$$
![[screenshot-2026-10-05_12-43-31.png]]
**UNIONE, DIFFERENZA, INTERSEZIONE**
Due relazioni $R$ e $S$ possono usufruire di que 

$$R\cup S=\{t|t\in R\ \vee t\in S\}$$
$$R-S=\{t|t\in R \wedge t\not\in S\}$$
$$R\cap S=\{t|t\in R\wedge t\in S\}$$
