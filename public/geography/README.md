# Geografia pubblica - edizione Puglia

La cartografia pubblica dell'edizione Puglia comprende:

- `atlas_region.geojson`: confine regionale ISTAT 2026 (codice 16);
- `atlas_provinces.geojson`: 6 province ISTAT 2026: Foggia (071), Bari (072, città metropolitana), Taranto (073), Brindisi (074), Lecce (075), Barletta-Andria-Trani (110);
- `atlas_municipalities.geojson`: 257 comuni ISTAT al 1/1/2026.

Fonte: ISTAT, «Confini delle unità amministrative a fini statistici al 1° gennaio 2026», versione generalizzata (Limiti01012026_g.zip, SHA-256 in `metadata/SNAPSHOTS.tsv`), CC BY 4.0. Gli attributi dei DBF sono letti in UTF-8 e le coordinate sono convertite da EPSG:32632 a WGS84 da `scripts/build_istat_geography.py`.

Gli studi della letteratura curata stanno in layer distinti sotto `public/data/`. Solo due strutture sono punti, geocodificate su OSM Nominatim (ODbL) il 2026-11-20 con oggetti `amenity=hospital`: AOU Consorziale Policlinico di Bari (41.1116427 N, 16.8594522 E) e Ospedale SS. Annunziata di Taranto (40.4644182 N, 17.2484741 E). Per il P.O. Vito Fazzi (Lecce), il Policlinico di Foggia e la RSA Fondazione San Raffaele di Taranto Nominatim non restituisce un oggetto ospedaliero: gli studi stanno sul poligono comunale (`raw/nominatim/NOTE.md`). Aziende agricole, macelli, fiumi e centri di recupero non sono punti.
