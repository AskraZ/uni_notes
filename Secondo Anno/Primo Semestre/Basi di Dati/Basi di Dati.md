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
###### **VINCOLI DI INTEGRITA'**
1. Attribuzione di *Null*
2. Quali Attributi sono *Chiave*
3. Quali Attributi sono *Chiavi esterne*
#### **CHIAVI**
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
Due relazioni $R$ e $S$ possono usufruire di queste operazioni:

$$R\cup S=\{t|t\in R\ \vee t\in S\}$$
$$R-S=\{t|t\in R \wedge t\not\in S\}$$
$$R\cap S=\{t|t\in R\wedge t\in S\}$$
**PROIEZIONE**
Serve ad estrapolare colonne e si indica con $\pi$
![[screenshot-2026-10-07_08-18-40.png|432]]
**RESTRIZIONE**
$$\sigma(R)=\{t|t\in R\vee\lambda(t)=VERA\}$$
con $\lambda$ che indica un predicato vero o falso.
![[screenshot-2026-10-07_08-20-57.png|427]]
**PRODOTTO CARTESIANO**
$$R\times S=\{tu|t\in R\vee u\in S\}$$
con $R=\{A_{1}:T_{1},\dots,A_{n}:T_{n}\}$ e $S=\{A_{n+1}:T_{n+1},\dots,A_{n+m}:T_{n+m}\}$

**JOIN**
- Natural JOIN
- $\theta$ JOIN
$$R\bowtie S=\{t|t[XY]\in R\vee t[YZ]\in S\}\implies R\bowtie S=t[XYZ]$$![[screenshot-2026-10-07_08-28-14.png|497]]
$$R\bowtie_{\sigma_{F}}S={\sigma(R\times S)}$$
###### QUERY 
ESERCIZIO 
![[screenshot-2026-10-07_08-52-36.png|607]]$$Employees\bowtie_{Number=Employee}Supervision$$
**ESERCIZI**

---
Trovare gli impiegati che guadagnano più di 40k€
$\pi_{NAME,SURNAME,AGE}=[\sigma_{sal>40}(Employees)]$
---
Trovare i responsabili che guadagnano più di 40k€
$\pi_{Head}=[Supervision \bowtie_{Employee=Number} \sigma_{sal >40}(Employees)]$
---
Trovare nome e salario dei responsabili degli impiegati che guadagnano più di 40k€
$\pi_{Name, Salary}=[Employees \bowtie_{Number=Head}\pi_{Head}(Supervision \bowtie_{Employee=Number}\sigma_{sal>40}(Employees))]$
---
Trovare gli impiegati che guadagnano più dei loro responsabili e visualizzare numero, nome, salario sia dell'impiegato che del responsabile.
$\pi(\sigma_{Sal>salH}(\sigma_{Number\to NumbH,Name \to NameH, Age\to AgeH, Salary\to SalH}\bowtie_{Number=Head}(Employees)\bowtie Supervision \bowtie_{Employee=Number}Employees))$
---
Trovare numero e nome dei responsabili i cui impiegati guadagnano tutti meno di 40k€.
$\pi_{Head}(Supervision)-\pi_{Head}[Supervision \bowtie_{Employee=Number}\sigma_{sal<40}(Employees)]$

