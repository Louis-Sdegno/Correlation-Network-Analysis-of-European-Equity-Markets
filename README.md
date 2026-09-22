# Correlation-Network-Analysis-of-European-Equity-Markets
# European Equity Market Correlation Networks

Analisi a network della struttura dei mercati azionari europei tra il 2018 e il 2024, con un focus su come si comporta la rete durante i periodi di stress finanziario (crollo COVID-19 2020, crisi energetica 2022).

**Autori:** Luigi Sdegno, Giovanni Malavita

## Di cosa si tratta

Il progetto rappresenta 13 asset europei — 5 indici nazionali (DAX, CAC 40, FTSE MIB, IBEX 35, FTSE 100) e 8 ETF settoriali STOXX Europe 600 (Banks, Energy, Technology, Healthcare, Industrials, Food & Beverage, Utilities, Automobiles) — come nodi di una rete, collegati in base alla correlazione tra i loro rendimenti giornalieri.

Tre le domande di ricerca principali:
- Quali asset occupano le posizioni più centrali nella rete?
- Le community individuate con l'algoritmo di Louvain corrispondono a raggruppamenti economicamente sensati (geografici o settoriali)?
- La rete diventa più densa e sincronizzata durante i periodi di stress, e cosa implica questo per la diversificazione di portafoglio?

## Metodo

- Correlazione di Pearson sui log-return giornalieri
- Rete a soglia di correlazione (τ = 0.70 baseline, 0.75 come robustness check)
- Minimum Spanning Tree basato sulla distanza di Mantegna
- Community detection con l'algoritmo di Louvain
- Analisi dinamica con rolling window (252 giorni, passo di 21 giorni)

## Risultato principale

Durante il crollo COVID-19 la correlazione media tra gli asset è salita sopra 0.80 e la densità della rete è più che raddoppiata: i benefici della diversificazione si sono ridotti proprio nel momento in cui il rischio di mercato era più alto. La crisi energetica del 2022 ha mostrato un effetto simile ma più contenuto e meno uniforme.

## Dati

Prezzi di chiusura rettificati giornalieri, 1 gennaio 2018 – 31 dicembre 2024, scaricati da Yahoo Finance.

## Requisiti

R con i pacchetti: `tidyquant`, `tidyverse`, `igraph`, `ggraph`, `tidygraph`, `PerformanceAnalytics`

## Paper completo

[link al PDF, se lo pubblichi altrove]
