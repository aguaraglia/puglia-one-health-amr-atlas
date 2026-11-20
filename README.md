# Atlante One Health AMR · Puglia

Edizione regionale `puglia_amr_atlas`, pubblicata da Codex Vitae ETS sulla stessa
base delle altre edizioni regionali. Il portale nazionale è [atlanteamr.it](https://atlanteamr.it).

## Stato

La letteratura pubblicata con collegamento territoriale esplicito alla Puglia
è concentrata su Bari. Ne restano 41 inclusi (20 novembre 2026): 6 di struttura,
16 di comune, 3 di provincia e 16 a scala regionale.

Due strutture sono punti, geocodificate su OSM Nominatim il 20 novembre 2026
(© OpenStreetMap contributors, ODbL), oggetti `amenity=hospital`:

- AOU Consorziale Policlinico di Bari: 5 studi (41,1116427 N, 16,8594522 E);
- Ospedale SS. Annunziata di Taranto: 1 studio (40,4644182 N, 17,2484741 E).

Il P.O. Vito Fazzi di Lecce (3 studi), il Policlinico Riuniti di Foggia
(1 studio) e la RSA Fondazione San Raffaele di Taranto (1 studio) non hanno un
oggetto ospedaliero su Nominatim e stanno sul comune. Aziende agricole, macelli,
depuratori e centri di recupero non sono punti.

Bari ha 13 studi. Foggia, Lecce e Taranto ne hanno 3 ciascuna. Brindisi ne ha 1
(Carovigno-Torre Guaceto). Barletta-Andria-Trani non ha studi con luogo
provinciale esclusivo. Due studi coprono più province: Foggia e Lecce; Bari,
Brindisi e Barletta-Andria-Trani. Sedici studi a scala regionale usano il
contorno della regione.

Per settore: 25 AMR clinica, 2 consumo, 2 stewardship, 2 veterinaria, 2 animali
d'affezione, 4 alimentare, 1 ambientale, 3 fauna selvatica.

L'IZS di Puglia e Basilicata copre le due regioni: sono inclusi solo gli studi
che separano i dati pugliesi.

L'edizione pubblica AR-ISS 2024 (copertura 58,7%, 13 laboratori referenti,
CC BY 4.0; attribuzione Istituto Superiore di Sanità) e AIFA Open Data 2024,
antibatterici J01 (CC BY 4.0; codreg 160; convenzionata 5.858.469 confezioni e
48,19 milioni di euro, acquisti diretti 963.054 confezioni e 14,42 milioni di
euro; attribuzione Agenzia Italiana del Farmaco). Nessun rapporto regionale o
ISTISAN/ISS sulla Puglia è stato trovato.

Sei layer (AMR umana, veterinaria, alimentare, ambientale, fauna selvatica,
contorno regionale):

- AMR umana: 8 elementi, 20 studi (2 punti: Policlinico di Bari e SS. Annunziata di Taranto; comuni di Bari, Lecce, Taranto, Foggia e Manfredonia; province di Bari, Brindisi e Barletta-Andria-Trani);
- AMR veterinaria: 3 elementi, 4 studi (regione; province di Foggia e Lecce; comune di Bari);
- AMR alimentare: 1 elemento (regione), 4 studi;
- AMR ambientale: 1 elemento (provincia di Foggia, fiumi della Capitanata), 1 studio;
- AMR nella fauna selvatica: 3 elementi (regione; Carovigno-Torre Guaceto; Taranto), 3 studi;
- studi a scala regionale: 1 elemento, 9 studi umani sul contorno.

I layer vuoti e le aree senza segnaposto sono nessuna evidenza pubblicata,
non resistenza zero. In questa edizione nessun layer di studi è vuoto. Ogni
popup cita lo studio e il DOI (o il record PubMed se il DOI non è assegnato)
e ricorda che il segnaposto è il luogo dello studio, non una prevalenza.

Confini ISTAT 2026 (257 comuni, 6 unità sovracomunali, regione 16), letti in
UTF-8. Il portale regionale, PugliaSalute, l'OER, dati.puglia.it, ARPA Puglia,
il sito del Policlinico di Bari, il sito dell'IZSPB e il PDF OsMed sono esclusi
o non disponibili: vedi `metadata/EXCLUDED_SOURCES.md`.

Il conteggio in homepage e in pubblicazioni legge
`public/data/literature-catalog.json` (41).

## Pagine

Sorgente su `main`. Il sito statico è pubblicato dal branch `gh-pages`
(GitHub Pages, cartella `/`). Nessun file `CNAME`: il dominio
`puglia.atlanteamr.it` si configura a parte. Analitica: GoatCounter
`https://atlanteamr.goatcounter.com/count`, come le altre edizioni.

## Build locale

```bash
python3 -m http.server 8000
```

Aprire `http://localhost:8000/`.

Per rigenerare i dati pubblici servono gli input in `raw/` e, per i confini,
l'archivio ISTAT indicato in `metadata/SNAPSHOTS.tsv`. I DBF ISTAT si leggono
in UTF-8:

```bash
pip install -r requirements-geodata.txt
python3 scripts/build_istat_geography.py --source-root <Limiti01012026_g> --output-root public/geography
python3 scripts/build_literature_catalog.py
python3 scripts/build_study_evidence_layers.py
```

## Directory

- `public/`: dati e asset approvati per il sito;
- `metadata/`: fonti, snapshot, ambito pubblico e fonti escluse;
- `raw/`: curatela, esummary e risposte Nominatim;
- `scripts/`: ricostruzione del catalogo e dei layer;
- `private/`: nessun dato riservato in questa edizione.
