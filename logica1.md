# 1.1 Introduzione alla Logica di Programmazione

### **Cos’è la Programmazione?**

La programmazione è l’arte di comunicare con un computer attraverso istruzioni precise e non ambigue. Immaginate di spiegare a un bambino molto preciso come fare un panino: dovete essere specifici in ogni passaggio.

**Esempio della vita reale:**
“Fare colazione” per un umano vs per un computer:
- **Umano**: “Fai colazione”
- **Computer**:
1. Vai in cucina
2. Apri il frigorifero
3. Prendi il latte
4. Se il latte è scaduto, buttalo e prendi quello nuovo
5. Chiudi il frigorifero
6. Prendi una tazza dall’armadio
7. Versa il latte nella tazza
8. …e così via

### **Concetti Fondamentali**

### **1. Algoritmo**

Un algoritmo è come una ricetta di cucina: una sequenza precisa di passi per ottenere un risultato.

**Caratteristiche di un buon algoritmo:**
- **Finito**: Deve terminare in un numero finito di passi
- **Deterministico**: Dato lo stesso input, produce sempre lo stesso output
- **Effettivo**: Ogni passo deve essere eseguibile
- **Input/Output**: Deve essere chiaro cosa riceve e cosa produce

**Esempio: Algoritmo per attraversare la strada**

```
1. INIZIO
2. Guarda a sinistra
3. Guarda a destra
4. SE non ci sono macchine ALLORA
5.    Attraversa
6. ALTRIMENTI
7.    Aspetta 5 secondi
8.    Torna al passo 2
9. FINE SE
10. FINE
```

### **2. Variabili**

Le variabili sono come scatole con etichette dove mettiamo i nostri dati.

**Tipi di dati principali:**
- **Numeri interi**: 1, 42, -15
- **Numeri decimali**: 3.14, 2.5, -1.8
- **Testo (stringhe)**: “Ciao”, “PHP”, “123abc”
- **Valori logici**: vero/falso (true/false)

**Esempio pratico:**

```
età = 25
nome = "Mario"
altezza = 1.75
isStudente = vero
```

### **3. Operatori**

**Operatori Aritmetici:**
- `+` (addizione): 5 + 3 = 8
- `-` (sottrazione): 10 - 4 = 6
- `*` (moltiplicazione): 6 * 7 = 42
- `/` (divisione): 15 / 3 = 5
- `%` (resto): 17 % 5 = 2

**Operatori di Confronto:**
- `==` (uguale): 5 == 5 → vero
- `!=` (diverso): 5 != 3 → vero
- `<` (minore): 3 < 5 → vero
- `>` (maggiore): 8 > 2 → vero
- `<=` (minore o uguale): 4 <= 4 → vero
- `>=` (maggiore o uguale): 7 >= 5 → vero

**Operatori Logici:**
- `AND` (e): vero AND vero = vero
- `OR` (o): vero OR falso = vero

- `NOT` (non): NOT vero = falso

### **Strutture di Controllo**

### **1. Struttura Sequenziale**

Le istruzioni vengono eseguite una dopo l’altra, come leggere un libro.

```
1. Accendi il computer
2. Apri il browser
3. Vai su Google
4. Cerca "PHP tutorial"
```

### **2. Struttura Condizionale (IF-ELSE)**

Permette di prendere decisioni basate su condizioni.

**Sintassi base:**

```
SE (condizione) ALLORA
    fai questo
ALTRIMENTI
    fai quest'altro
FINE SE
```

**Esempio pratico:**

```
età = 18

SE età >= 18 ALLORA
    STAMPA "Puoi guidare"
ALTRIMENTI
    STAMPA "Non puoi ancora guidare"
FINE SE
```

**Condizioni multiple:**

```
voto = 85

SE voto >= 90 ALLORA
    STAMPA "Eccellente"
ALTRIMENTI SE voto >= 70 ALLORA
    STAMPA "Buono"
ALTRIMENTI SE voto >= 60 ALLORA
    STAMPA "Sufficiente"
ALTRIMENTI
    STAMPA "Insufficiente"
FINE SE
```

### **3. Struttura Iterativa (Cicli)**

**WHILE (Finché):**
Ripete un blocco di codice finché una condizione è vera.

```
contatore = 1

MENTRE contatore <= 5 FAI
    STAMPA "Numero: " + contatore
    contatore = contatore + 1
FINE MENTRE
```

**FOR (Per):**
Quando sappiamo esattamente quante volte ripetere.

```
PER i da 1 a 10 FAI
    STAMPA "Tavola del 2: 2 x " + i + " = " + (2 * i)
FINE PER
```

### **Il Pensiero Algoritmico**

### **1. Scomposizione del Problema**

Dividere un problema grande in problemi più piccoli.

**Esempio: Organizzare una festa**
- Problema grande: “Organizza una festa”
- Sottoproblemi:
- Scegli la data
- Fai la lista degli invitati
- Compra il cibo
- Prepara la location
- Invia gli inviti

### **2. Riconoscimento di Pattern**

Identificare schemi ricorrenti per riutilizzare soluzioni.

**Esempio: Calcolare potenze**
- 2^1 = 2
- 2^2 = 2 * 2
- 2^3 = 2 * 2 * 2
- Pattern: moltiplicare il numero per se stesso n volte

### **3. Astrazione**

Concentrarsi sui dettagli essenziali ignorando quelli irrilevanti.

**Esempio: Guidare un’auto**
- Dettagli importanti: acceleratore, freno, sterzo
- Dettagli non importanti: colore dell’auto, marca del motore

---

## 1.2 Algoritmi e Complessità

### **Che cos’è un Algoritmo?**

Un algoritmo è una procedura computazionale ben definita che prende un input e produce un output. È la ricetta che il computer segue per risolvere un problema.

### **Proprietà Fondamentali di un Algoritmo**

**1. Finito**
L’algoritmo deve terminare dopo un numero finito di passi.

❌ **Esempio scorretto:**

```
numero = 1
MENTRE numero > 0 FAI
    numero = numero + 1  // Non terminerà mai!
FINE MENTRE
```

✅ **Esempio corretto:**

```
numero = 10
MENTRE numero > 0 FAI
    STAMPA numero
    numero = numero - 1  // Terminerà quando numero = 0
FINE MENTRE
```

**2. Deterministico**
Dato lo stesso input, deve sempre produrre lo stesso output.

**3. Effettivo**
Ogni operazione deve essere eseguibile dal computer.

**4. Input/Output ben definiti**
Deve essere chiaro cosa l’algoritmo riceve e cosa produce.

### **Qualità degli Algoritmi**

### **Correttezza**

L’algoritmo risolve effettivamente il problema per cui è stato progettato.

**Test di correttezza:**
- Casi normali
- Casi limite (bordi)
- Casi eccezionali

**Esempio: Algoritmo per trovare il massimo**

```
ALGORITMO trovaMax(lista)
INPUT: lista di numeri
OUTPUT: il numero più grande

1. SE lista è vuota ALLORA
2.    RITORNA errore
3. FINE SE
4. max = primo elemento della lista
5. PER ogni elemento dalla posizione 1 alla fine FAI
6.    SE elemento > max ALLORA
7.       max = elemento
8.    FINE SE
9. FINE PER
10. RITORNA max
```

**Test:**
- Caso normale: [3, 7, 2, 9, 1] → 9 ✅
- Caso limite: [5] → 5 ✅
- Caso eccezionale (Exception): [] → errore ✅

### **Efficienza**

Quanto velocemente l’algoritmo risolve il problema e quanta memoria usa.

### **Algoritmi di Ricerca Principali**

### **1. Ricerca Lineare (Sequential Search)**

![1_eTQoIHGdG58sy-iMwcp97w.png](attachment:98a3ba06-af03-426f-8cb3-b92c2825c27f:1_eTQoIHGdG58sy-iMwcp97w.png)

**Concetto:** Controlla ogni elemento uno per uno finché non trova quello cercato.

**Vantaggi:**
- Funziona su dati non ordinati
- Semplice da implementare
- Non richiede memoria aggiuntiva

**Svantaggi:**
- Lenta su grandi quantità di dati
- Nel caso peggiore esamina tutti gli elementi

**Quando usarla:**
- Liste piccole (< 100 elementi)
- Dati non ordinati
- Ricerche occasionali

### **2. Ricerca Binaria (Binary Search)**

![binary_search_algorithm.jpg](attachment:d2f2870e-6ca5-4ee5-a2c9-869657810a9d:binary_search_algorithm.jpg)

**Concetto:** Divide continuamente la lista a metà, eliminando la metà che non può contenere l’elemento.

**Requisiti:**
- Lista deve essere ordinata

**Vantaggi:**
- Molto veloce su grandi quantità di dati
- Efficienza logaritmica

**Svantaggi:**
- Richiede dati ordinati
- Più complessa da implementare

**Quando usarla:**
- Liste grandi (> 100 elementi)
- Dati ordinati
- Ricerche frequenti

---

## 1.3 Strutture Dati Fondamentali

### **Cosa sono le Strutture Dati?**

Le strutture dati sono modi di organizzare e memorizzare i dati per utilizzarli in modo efficiente. Sono come diversi tipi di contenitori, ognuno adatto a scopi specifici.

**Analogia della vita reale:**
- **Armadio**: Scaffali ordinati per tipo di vestito
- **Borsa**: Tutto insieme, devi cercare
- **Raccoglitore**: Pagine numerate in ordine
- **Mazzo di carte**: Pila ordinata

### **Array/Liste**

### **Definizione**

Un array è una collezione ordinata di elementi dello stesso tipo, memorizzati in posizioni contigue di memoria.

**Caratteristiche principali:**
- **Ordinati**: Gli elementi hanno una posizione specifica
- **Indicizzati**: Ogni posizione ha un numero (indice)
- **Dimensione fissa o dinamica**: Dipende dal linguaggio
- **Accesso diretto**: Posso accedere direttamente all’elemento n

### **Rappresentazione Visuale**

```
Indici:  [0] [1] [2] [3] [4]
Valori:  [12][45][78][23][91]
```

### **Indici: Il Sistema di Coordinate**

**Perché si inizia da 0?**
Gli indici rappresentano l’offset (spostamento) dalla posizione iniziale:
- Indice 0: nessuno spostamento (primo elemento)
- Indice 1: spostamento di 1 posizione
- Indice 2: spostamento di 2 posizioni

**Esempio pratico:**

```
nomi = ["Alice", "Bob", "Charlie", "Diana"]

Posizione 0: "Alice"
Posizione 1: "Bob"
Posizione 2: "Charlie"
Posizione 3: "Diana"

Ultimo elemento: posizione (lunghezza - 1) = 4 - 1 = 3
```

### **Tipi di Array**

**Array Monodimensionali**

```
voti = [85, 92, 78, 88, 95]
```

**Array Bidimensionali (Matrici)**

```
tabella = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

Accesso: tabella[riga][colonna]
Esempio: tabella[1][2] = 6
```

### **Vantaggi e Svantaggi**

**Vantaggi:**
- **Accesso veloce**: O(1) per indice
- **Memoria efficiente**: Elementi contigui
- **Semplicità**: Facile da capire e usare
- **Cache-friendly**: Buone prestazioni di memoria

**Svantaggi:**
- **Dimensione fissa**: Difficile da ridimensionare
- **Inserimento/cancellazione costosi**: O(n) per posizioni intermedie
- **Spreco di memoria**: Se non tutti gli slot sono usati

### **Esempi Pratici d’Uso**

**1. Lista della spesa**

```
spesa = ["Pane", "Latte", "Uova", "Formaggio"]

// Aggiungere un elemento
spesa[4] = "Mele"

// Verificare se un elemento è presente
SE "Latte" in spesa ALLORA
    STAMPA "Latte è nella lista"
FINE SE
```

**2. Voti degli studenti**

```
voti = [85, 92, 78, 88, 95]

// Calcolare la media
somma = 0
PER ogni voto in voti FAI
    somma = somma + voto
FINE PER
media = somma / lunghezza(voti)
```

**3. Coordinate 2D**

```
scacchiera = [
    ["T", "C", "A", "D", "R", "A", "C", "T"],
    ["P", "P", "P", "P", "P", "P", "P", "P"],
    [" ", " ", " ", " ", " ", " ", " ", " "],
    // ... altre righe
]

// Muovere un pezzo
scacchiera[destinazione_riga][destinazione_colonna] = scacchiera[partenza_riga][partenza_colonna]
scacchiera[partenza_riga][partenza_colonna] = " "
```

---

# 2. ESEMPI PRATICI

## 2.1 Esempi di Logica Base

### **Esempio 1: Determinare se un numero è pari o dispari**

### **Analisi del Problema**

Un numero è pari se è divisibile per 2 senza resto, altrimenti è dispari.

**Concetto matematico:** Un numero n è pari se n % 2 = 0

### **Soluzione Algoritmica**

```
ALGORITMO controllaParità(numero)
INPUT: numero intero
OUTPUT: messaggio che indica se è pari o dispari

1. INIZIO
2. resto = numero % 2
3. SE resto == 0 ALLORA
4.    STAMPA numero + " è pari"
5. ALTRIMENTI
6.    STAMPA numero + " è dispari"
7. FINE SE
8. FINE
```

### **Traccia di Esecuzione**

**Test 1:** numero = 8
- Passo 2: resto = 8 % 2 = 0
- Passo 3: 0 == 0 è vero
- Passo 4: Stampa “8 è pari”

**Test 2:** numero = 7
- Passo 2: resto = 7 % 2 = 1
- Passo 3: 1 == 0 è falso
- Passo 6: Stampa “7 è dispari”

### **Esempio 2: Trovare il massimo in una lista**

### **Analisi del Problema**

Dato un array di numeri, trovare l’elemento con valore più grande.

**Strategia:** Assumere che il primo elemento sia il massimo, poi confrontarlo con tutti gli altri.

### **Soluzione Algoritmica**

```
ALGORITMO trovaMax(lista)
INPUT: lista di numeri (non vuota)
OUTPUT: il numero più grande

1. INIZIO
2. SE lista è vuota ALLORA
3.    RITORNA errore "Lista vuota"
4. FINE SE
5. massimo = lista[0]  // Assumo primo elemento come max
6. PER i da 1 a lunghezza(lista)-1 FAI
7.    SE lista[i] > massimo ALLORA
8.       massimo = lista[i]
9.    FINE SE
10. FINE PER
11. RITORNA massimo
12. FINE
```

### **Traccia di Esecuzione Dettagliata**

**Input:** lista = [3, 7, 2, 9, 1, 5]

| Passo | i | lista[i] | massimo | Confronto | Azione |
| --- | --- | --- | --- | --- | --- |
| 5 | - | - | 3 | - | Inizializzazione |
| 7 | 1 | 7 | 3 | 7 > 3 | massimo = 7 |
| 7 | 2 | 2 | 7 | 2 > 7 | Nessuna azione |
| 7 | 3 | 9 | 7 | 9 > 7 | massimo = 9 |
| 7 | 4 | 1 | 9 | 1 > 9 | Nessuna azione |
| 7 | 5 | 5 | 9 | 5 > 9 | Nessuna azione |

**Risultato:** massimo = 9

### **Varianti dell’Algoritmo**

**Trovare anche la posizione:**

```
ALGORITMO trovaMaxConPosizione(lista)
1. massimo = lista[0]
2. posizioneMassimo = 0
3. PER i da 1 a lunghezza(lista)-1 FAI
4.    SE lista[i] > massimo ALLORA
5.       massimo = lista[i]
6.       posizioneMassimo = i
7.    FINE SE
8. FINE PER
9. RITORNA {valore: massimo, posizione: posizioneMassimo}
```

**Trovare massimo e minimo insieme:**

```
ALGORITMO trovaMaxMin(lista)
1. max = lista[0]
2. min = lista[0]
3. PER i da 1 a lunghezza(lista)-1 FAI
4.    SE lista[i] > max ALLORA
5.       max = lista[i]
6.    FINE SE
7.    SE lista[i] < min ALLORA
8.       min = lista[i]
9.    FINE SE
10. FINE PER
11. RITORNA {massimo: max, minimo: min}
```

### **Esempio 3: Contare le occorrenze di un valore**

### **Analisi del Problema**

Contare quante volte un determinato valore appare in una lista.

### **Soluzione Algoritmica**

```
ALGORITMO contaOccorrenze(lista, valoreCercato)
INPUT: lista di elementi, valore da cercare
OUTPUT: numero di occorrenze

1. INIZIO
2. contatore = 0
3. PER i da 0 a lunghezza(lista)-1 FAI
4.    SE lista[i] == valoreCercato ALLORA
5.       contatore = contatore + 1
6.    FINE SE
7. FINE PER
8. RITORNA contatore
9. FINE
```

### **Traccia di Esecuzione**

**Input:** lista = [2, 4, 2, 7, 2, 1], valoreCercato = 2

| Passo | i | lista[i] | Confronto | contatore |
| --- | --- | --- | --- | --- |
| 2 | - | - | - | 0 |
| 4 | 0 | 2 | 2 == 2 | 1 |
| 4 | 1 | 4 | 4 == 2 | 1 |
| 4 | 2 | 2 | 2 == 2 | 2 |
| 4 | 3 | 7 | 7 == 2 | 2 |
| 4 | 4 | 2 | 2 == 2 | 3 |
| 4 | 5 | 1 | 1 == 2 | 3 |

**Risultato:** 3 occorrenze

### **Esempio 4: Calcolare la media di una lista**

### **Soluzione Completa con Gestione Errori**

```
ALGORITMO calcolaMedia(lista)
INPUT: lista di numeri
OUTPUT: media aritmetica

1. INIZIO
2. SE lista è vuota ALLORA
3.    RITORNA errore "Impossibile calcolare media di lista vuota"
4. FINE SE
5. somma = 0
6. PER ogni elemento in lista FAI
7.    SE elemento non è un numero ALLORA
8.       RITORNA errore "Elemento non numerico trovato"
9.    FINE SE
10.   somma = somma + elemento
11. FINE PER
12. media = somma / lunghezza(lista)
13. RITORNA media
14. FINE
```

### **Esempio con Calcoli Aggiuntivi**

```
ALGORITMO statisticheBase(lista)
1. media = calcolaMedia(lista)
2. max = trovaMax(lista)
3. min = trovaMin(lista)
4.
5. // Calcola mediana
6. listaOrdinata = ordina(copia(lista))
7. metà = lunghezza(lista) / 2
8. SE lunghezza(lista) % 2 == 1 ALLORA
9.    mediana = listaOrdinata[metà]
10. ALTRIMENTI
11.   mediana = (listaOrdinata[metà-1] + listaOrdinata[metà]) / 2
12. FINE SE
13.
14. RITORNA {media: media, mediana: mediana, massimo: max, minimo: min}
```

---

---

# PARTE 3: ESERCIZI PRATICI

## 3.1 Esercizi Guidati

### **Esercizio Guidato 1: Secondo Elemento Più Grande**

### **Analisi del Problema**

Trovare il secondo valore più grande in una lista, gestendo casi particolari come liste corte o valori duplicati.

### **Strategia di Risoluzione**

1. Tenere traccia di due variabili: max e secondoMax
2. Aggiornare entrambe man mano che esaminiamo gli elementi
3. Gestire i casi speciali

### **Sviluppo Guidato dell’Algoritmo**

**Passo 1: Versione base (con problemi)**

```
ALGORITMO secondoMassimo_v1(lista)
1. max = lista[0]
2. secondoMax = lista[1]
3. PER i da 2 a lunghezza(lista)-1 FAI
4.    SE lista[i] > max ALLORA
5.       secondoMax = max
6.       max = lista[i]
7.    FINE SE
8. FINE PER
9. RITORNA secondoMax
```

**❌ Problemi identificati:**
- Non gestisce liste con meno di 2 elementi
- Se lista[1] > lista[0], secondoMax è sbagliato all’inizio
- Non aggiorna secondoMax per valori tra max e secondoMax

**Passo 2: Versione migliorata**

```
ALGORITMO secondoMassimo_v2(lista)
1. SE lunghezza(lista) < 2 ALLORA
2.    RITORNA errore "Lista troppo piccola"
3. FINE SE
4.
5. max = -infinito
6. secondoMax = -infinito
7.
8. PER ogni elemento in lista FAI
9.    SE elemento > max ALLORA
10.      secondoMax = max
11.      max = elemento
12.   ALTRIMENTI SE elemento > secondoMax E elemento != max ALLORA
13.      secondoMax = elemento
14.   FINE SE
15. FINE PER
16.
17. SE secondoMax == -infinito ALLORA
18.    RITORNA errore "Tutti gli elementi sono uguali"
19. FINE SE
20.
21. RITORNA secondoMax
```

### **Traccia di Esecuzione Completa**

**Input:** lista = [3, 7, 1, 9, 7, 2]

| Elemento | max (prima) | secondoMax (prima) | Confronto | max (dopo) | secondoMax (dopo) |
| --- | --- | --- | --- | --- | --- |
| 3 | -∞ | -∞ | 3 > -∞ | 3 | -∞ |
| 7 | 3 | -∞ | 7 > 3 | 7 | 3 |
| 1 | 7 | 3 | 1 < 7, 1 < 3 | 7 | 3 |
| 9 | 7 | 3 | 9 > 7 | 9 | 7 |
| 7 | 9 | 7 | 7 < 9, 7 = 7 | 9 | 7 |
| 2 | 9 | 7 | 2 < 9, 2 < 7 | 9 | 7 |

**Risultato:** secondoMax = 7

### **Test con Casi Particolari**

**Test 1: Lista con elementi uguali**

```
Input: [5, 5, 5, 5]
Risultato: errore "Tutti gli elementi sono uguali"
```

**Test 2: Lista con due elementi diversi**

```
Input: [10, 3]
max = 10, secondoMax = 3
Risultato: 3
```

**Test 3: Lista con valori negativi**

```
Input: [-1, -5, -2, -8]
max = -1, secondoMax = -2
Risultato: -2
```

### **Esercizio Guidato 2: Prima Posizione con Ricerca Binaria (15 min)**

### **Analisi del Problema**

Modificare la ricerca binaria standard per trovare la PRIMA occorrenza di un elemento che può apparire più volte in una lista ordinata.

### **Differenza dalla Ricerca Binaria Standard**

- Ricerca binaria normale: trova una qualsiasi occorrenza
- Versione modificata: trova specificatamente la prima occorrenza

### **Strategia**

Quando troviamo l’elemento cercato, non ci fermiamo immediatamente. Continuiamo a cercare verso sinistra per vedere se ci sono occorrenze precedenti.

### **Sviluppo Guidato**

**Passo 1: Comprendiamo il problema**

```
Lista: [1, 2, 2, 2, 5, 7, 7, 9]
Cerchiamo: 2
Posizioni di 2: 1, 2, 3
Prima posizione: 1 (quello che vogliamo)
```

**Passo 2: Modifichiamo l’algoritmo**

```
ALGORITMO primaPosizioneBinaria(listaOrdinata, valoreCercato)
INPUT: lista ordinata, valore da cercare
OUTPUT: indice della prima occorrenza, -1 se non trovato

1. INIZIO
2. sinistra = 0
3. destra = lunghezza(listaOrdinata) - 1
4. risultato = -1  // Variabile per memorizzare il risultato
5.
6. MENTRE sinistra <= destra FAI
7.    medio = (sinistra + destra) / 2
8.
9.    SE listaOrdinata[medio] == valoreCercato ALLORA
10.      risultato = medio  // Memorizza questa posizione
11.      destra = medio - 1  // Continua a cercare a sinistra
12.
13.   ALTRIMENTI SE listaOrdinata[medio] < valoreCercato ALLORA
14.      sinistra = medio + 1  // Il valore è a destra
15.
16.   ALTRIMENTI
17.      destra = medio - 1    // Il valore è a sinistra
18.   FINE SE
19. FINE MENTRE
20.
21. RITORNA risultato
22. FINE
```

### **Punti Chiave dell’Algoritmo**

- **Linea 10**: Salviamo la posizione corrente come candidato
- **Linea 11**: Continuiamo a cercare a sinistra per trovare occorrenze precedenti
- **Linea 4**: Usiamo una variabile per tenere traccia del miglior risultato finora

### **Traccia di Esecuzione Dettagliata**

**Input:** lista = [1, 2, 2, 2, 5, 7, 7, 9], valoreCercato = 2

**Setup iniziale:**
- Lista: [1, 2, 2, 2, 5, 7, 7, 9]
- Indici: 0, 1, 2, 3, 4, 5, 6, 7
- sinistra = 0, destra = 7, risultato = -1

**Iterazione 1:**

```
sinistra = 0, destra = 7
medio = (0 + 7) / 2 = 3
lista[3] = 2
2 == 2 → TROVATO!
risultato = 3
destra = 3 - 1 = 2  (cerca a sinistra)
```

**Iterazione 2:**

```
sinistra = 0, destra = 2
medio = (0 + 2) / 2 = 1
lista[1] = 2
2 == 2 → TROVATO ANCORA!
risultato = 1  (aggiorna con posizione precedente)
destra = 1 - 1 = 0  (cerca ancora a sinistra)
```

**Iterazione 3:**

```
sinistra = 0, destra = 0
medio = (0 + 0) / 2 = 0
lista[0] = 1
1 < 2 → cerca a destra
sinistra = 0 + 1 = 1
```

**Fine:**

```
sinistra = 1, destra = 0
sinistra > destra → TERMINA
RITORNA risultato = 1
```

### **Visualizzazione del Processo**

```
Passo 1: [1, 2, 2, 2, 5, 7, 7, 9]
              ↑     ↑
         sin=0    des=7
              medio=3, valore=2 ✓
              risultato=3, cerca a sinistra

Passo 2: [1, 2, 2, | 2, 5, 7, 7, 9]
              ↑   ↑
         sin=0  des=2
              medio=1, valore=2 ✓
              risultato=1, cerca a sinistra

Passo 3: [1, | 2, 2, 2, 5, 7, 7, 9]
          ↑  ↑
     sin=0 des=0
          medio=0, valore=1 ≠ 2
          sin=1 > des=0 → FINE
```

### **Algoritmo Complementare: Ultima Posizione**

```
ALGORITMO ultimaPosizioneBinaria(listaOrdinata, valoreCercato)
1. sinistra = 0, destra = lunghezza(listaOrdinata) - 1
2. risultato = -1
3.
4. MENTRE sinistra <= destra FAI
5.    medio = (sinistra + destra) / 2
6.
7.    SE listaOrdinata[medio] == valoreCercato ALLORA
8.       risultato = medio
9.       sinistra = medio + 1  // Cerca a destra per ultime occorrenze
10.   ALTRIMENTI SE listaOrdinata[medio] < valoreCercato ALLORA
11.      sinistra = medio + 1
12.   ALTRIMENTI
13.      destra = medio - 1
14.   FINE SE
15. FINE MENTRE
16.
17. RITORNA risultato
```

### **Applicazione Combinata: Contare Occorrenze**

```
ALGORITMO contaOccorrenzeBinarie(listaOrdinata, valoreCercato)
1. prima = primaPosizioneBinaria(listaOrdinata, valoreCercato)
2. SE prima == -1 ALLORA
3.    RITORNA 0  // Elemento non presente
4. FINE SE
5. ultima = ultimaPosizioneBinaria(listaOrdinata, valoreCercato)
6. RITORNA ultima - prima + 1
```

**Test:**

```
Lista: [1, 2, 2, 2, 5, 7, 7, 9]
valoreCercato = 2
prima = 1, ultima = 3
occorrenze = 3 - 1 + 1 = 3 ✓
```

---

---

## Introduzione allo Pseudocodice

### **Cos'è lo Pseudocodice?**

Lo pseudocodice è un linguaggio di programmazione "finto" che usa parole e frasi in italiano (o inglese) per descrivere gli algoritmi. È come scrivere una ricetta di cucina usando un linguaggio strutturato ma comprensibile a tutti.

**Definizione:** Lo pseudocodice è una descrizione informale di un algoritmo che usa le convenzioni strutturali di un linguaggio di programmazione, ma è progettato per essere letto dagli esseri umani piuttosto che dalle macchine.

### **Perché Usare lo Pseudocodice?**

### **1. Indipendenza dal Linguaggio**

Lo pseudocodice non dipende dalla sintassi specifica di PHP, Python, Java o altri linguaggi. Puoi progettare un algoritmo una volta e poi tradurlo in qualsiasi linguaggio.

**Esempio:**

```jsx
Pseudocodice:
SE età >= 18 ALLORA
   STAMPA "Maggiorenne"
FINE SE

PHP:
if ($età >= 18) {
    echo "Maggiorenne";
}

Python:
if età >= 18:
    print("Maggiorenne")
```

### **2. Chiarezza e Semplicità**

Concentrati sulla logica senza distrarti dalla sintassi.

**Confronto:**

```jsx
❌ PHP (confuso per principianti):
for ($i = 0; $i < count($array); $i++) {
    if ($array[$i] % 2 == 0) {
        echo $array[$i] . " è pari\n";
    }
}

✅ Pseudocodice (chiaro):
PER ogni numero nella lista FAI
    SE numero è pari ALLORA
        STAMPA numero + " è pari"
    FINE SE
FINE PER
```

### **3. Comunicazione**

Permette ai programmatori di comunicare algoritmi senza barriere linguistiche.

### **Convenzioni dello Pseudocodice**

### **Struttura Base**

```jsx
ALGORITMO nomeAlgoritmo(parametri)
INPUT: descrizione degli input
OUTPUT: descrizione degli output

1. INIZIO
2. // Passi dell'algoritmo
3. FINE
```

### **Parole Chiave Principali**

**Controllo di Flusso:**

- `SE... ALLORA... ALTRIMENTI... FINE SE`
- `MENTRE... FAI... FINE MENTRE`
- `PER... FAI... FINE PER`
- `RIPETI... FINCHÉ`

**Operazioni:**

- `ASSEGNA` o `=` per assegnazioni
- `STAMPA` o `SCRIVI` per output
- `LEGGI` per input
- `RITORNA` per restituire valori

**Logica:**

- `E` (AND), `O` (OR), `NON` (NOT)
- `==` (uguale), `!=` (diverso), `<`, `>`, `<=`, `>=`

### **Indentazione e Struttura**

```jsx
SE condizione ALLORA
    // Blocco indentato
    istruzione1
    istruzione2
    SE altra condizione ALLORA
        // Blocco doppiamente indentato
        istruzione3
    FINE SE
FINE SE
```

### **Esempi Pratici di Pseudocodice**

### **Esempio 1: Calcolo della Media**

```jsx
ALGORITMO calcolaMedia(numeri)
INPUT: lista di numeri
OUTPUT: media aritmetica

1. INIZIO
2. somma = 0
3. contatore = 0
4. 
5. PER ogni numero in numeri FAI
6.    somma = somma + numero
7.    contatore = contatore + 1
8. FINE PER
9. 
10. SE contatore > 0 ALLORA
11.    media = somma / contatore
12.    RITORNA media
13. ALTRIMENTI
14.    RITORNA errore "Lista vuota"
15. FINE SE
16. FINE
```

### **Esempio 2: Ricerca in Lista**

```jsx
ALGORITMO cercaElemento(lista, elementoCercato)
INPUT: lista di elementi, elemento da cercare
OUTPUT: posizione dell'elemento o -1 se non trovato

1. INIZIO
2. PER i da 0 a lunghezza(lista)-1 FAI
3.    SE lista[i] == elementoCercato ALLORA
4.       RITORNA i
5.    FINE SE
6. FINE PER
7. RITORNA -1
8. FINE
```

### **Esempio 3: Ordinamento (Selection Sort)**

```jsx
ALGORITMO ordinaLista(lista)
INPUT: lista di numeri disordinata
OUTPUT: lista ordinata in modo crescente

1. INIZIO
2. PER i da 0 a lunghezza(lista)-2 FAI
3.    minimoIndice = i
4.    
5.    PER j da i+1 a lunghezza(lista)-1 FAI
6.       SE lista[j] < lista[minimoIndice] ALLORA
7.          minimoIndice = j
8.       FINE SE
9.    FINE PER
10.   
11.   // Scambia elementi
12.   temp = lista[i]
13.   lista[i] = lista[minimoIndice]
14.   lista[minimoIndice] = temp
15. FINE PER
16. RITORNA lista
17. FINE
```

### **Regole di Scrittura**

### **1. Usa Verbi Imperativi**

```jsx
✅ CORRETTO:
CALCOLA la somma
TROVA il massimo
STAMPA il risultato

❌ SBAGLIATO:
La somma viene calcolata
Il massimo si trova
Il risultato è stampato
```

### **2. Sii Specifico ma Conciso**

```jsx
✅ CORRETTO:
SE voto >= 60 ALLORA
    STAMPA "Promosso"
FINE SE

❌ TROPPO GENERICO:
SE lo studente ha un voto sufficiente
    Comunica l'esito positivo

❌ TROPPO SPECIFICO:
SE voto è maggiore di 59 E voto è minore di 101 ALLORA
    STAMPA sulla console il messaggio "Promosso"
FINE SE
```

### **3. Usa Nomi Significativi**

```jsx
✅ CORRETTO:
contatorePari = 0
sommaDispari = 0

❌ SBAGLIATO:
x = 0
y = 0
```

### **Differenze con i Linguaggi Reali**

### **Pseudocodice vs Linguaggi di Programmazione**

### **Esempio Comparativo**

**Problema:** Trova il numero più grande in una lista

**Pseudocodice:**

```jsx
ALGORITMO trovaMax(lista)
1. max = primo elemento
2. PER ogni elemento rimanente FAI
3.    SE elemento > max ALLORA
4.       max = elemento
5.    FINE SE
6. FINE PER
7. RITORNA max
```

**PHP:**

php

```jsx
function trovaMax($lista) {
    $max = $lista[0];
    for ($i = 1; $i < count($lista); $i++) {
        if ($lista[$i] > $max) {
            $max = $lista[$i];
        }
    }
    return $max;
}
```

### **Errori Comuni nello Pseudocodice**

### **1. Troppi Dettagli Implementativi**

```jsx
❌ SBAGLIATO:
Inizializza un array di interi di dimensione 100
Alloca memoria per 400 bytes
Usa il registro EAX per il contatore

✅ CORRETTO:
Crea una lista vuota
Inizializza contatore a 0
```

### **2. Ambiguità**

```jsx
❌ AMBIGUO:
Processa la lista

✅ SPECIFICO:
PER ogni elemento nella lista FAI
    SE elemento è negativo ALLORA
        RIMUOVI elemento
    FINE SE
FINE PER
```

### **3. Inconsistenza nelle Convenzioni**

```jsx
❌ INCONSISTENTE:
SE x > 0 ALLORA
    stampa "positivo"
FINE SE
while y < 10 do
    y = y + 1
end while

✅ CONSISTENTE:
SE x > 0 ALLORA
    STAMPA "positivo"
FINE SE
MENTRE y < 10 FAI
    y = y + 1
FINE MENTRE
```

### **Esercizio di Comprensione**

**Leggi questo pseudocodice e spiega cosa fa:**

```jsx
ALGORITMO misterioso(lista)
1. risultato = lista vuota
2. PER i da lunghezza(lista)-1 a 0 FAI
3.    aggiungi lista[i] a risultato
4. FINE PER
5. RITORNA risultato
```

**Risposta:** Inverte l'ordine degli elementi in una lista.

### **Vantaggi dello Pseudocodice per l'Apprendimento**

### **1. Focus sulla Logica**

- Permette di concentrarsi sul "cosa fare" prima del "come farlo"
- Riduce la frustrazione della sintassi complessa

### **2. Debugging Conceptual**

- Più facile trovare errori logici
- Tracciare l'esecuzione passo-passo

### **3. Comunicazione**

- Facilita la discussione degli algoritmi in classe
- Permette di spiegare concetti senza barriere tecniche

### **4. Transizione Graduale**

- Ponte naturale verso i linguaggi reali
- Facilita l'apprendimento di multiple sintassi

### **Preparazione per PHP**

### **Concetti che Useremo in PHP:**

1. **Array PHP**: `$array = [1, 2, 3, 4];`
2. **Cicli**: `for`, `foreach`, `while`
3. **Condizioni**: `if`, `else`, `elseif`
4. **Funzioni built-in**: `array_search()`, `in_array()`, `count()`

### **Esempio di Traduzione:**

**Pseudocodice:**

```
ALGORITMO cerca(lista, valore)
1. PER i da 0 a lunghezza(lista)-1 FAI
2.    SE lista[i] == valore ALLORA
3.       RITORNA i
4.    FINE SE
5. FINE PER
6. RITORNA -1
```

**PHP:**

```php
function cerca($lista, $valore) {
    for ($i = 0; $i < count($lista); $i++) {
        if ($lista[$i] == $valore) {
            return $i;        }
    }
    return -1;}
```


## **Esercizio 1: Diagramma di Flusso - "Preparare una Colazione"**

**Obiettivo**: Comprendere sequenze logiche e condizioni

**Istruzioni**:

1. Crea un diagramma di flusso in Miro che descriva i passaggi per preparare una colazione
2. Usa forme diverse per:
    - **Ovali** per inizio/fine
    - **Rettangoli** per azioni (es. "Accendi fornello")
    - **Rombi** per decisioni (es. "Hai le uova?")
    - **Frecce** per collegare i passaggi

**Esempio di flusso**:

- Inizio → Controlla frigo → Hai le uova? → Se SÌ: Cuoci uova → Se NO: Prendi cereali → Fine

**Concetti appresi**: Sequenze, condizioni if/else, flusso logico

---

## **Esercizio 2: Algoritmo Visivo - "Indovinare un Numero"**

**Obiettivo**: Comprendere cicli e logica iterativa

**Istruzioni**:

1. Crea un diagramma che rappresenti il gioco "indovina il numero da 1 a 10"

**Flusso da rappresentare**:

- Genera numero casuale → Chiedi tentativo → Confronta → Dai feedback → Ripeti fino a vittoria

**Concetti appresi**: Variabili, loop, confronti, input/output
