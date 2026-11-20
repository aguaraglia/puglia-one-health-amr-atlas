# Nominatim, 2026-11-20 (Puglia)

UA "CodexVitae-AMR-atlas/1.0 (info@codexvitae.it)", countrycodes=it, jsonv2, limit=3, pausa 1,1 s. Risposte grezze: results_2026-11-20.json (19 query).

Strutture nominate negli studi inclusi da geocodificare: AOU Consorziale Policlinico di Bari, Ospedale SS. Annunziata (Taranto), P.O. Vito Fazzi (Lecce), AOU Policlinico Riuniti (Foggia), RSA Fondazione San Raffaele Cittadella della Carità (Taranto).

Punti usati (solo oggetti amenity=hospital):
- policlinico_bari: "Policlinico di Bari", amenity=hospital, Piazza Giulio Cesare 11, Bari: lat 41.1116427, lon 16.8594522.
- annunziata_ta: "Ospedale SS. Annunziata, Via Francesco Bruno, Taranto", amenity=hospital, Via Francesco Bruno 1: lat 40.4644182, lon 17.2484741 (scartato l'ingresso del pronto soccorso emergency_ward_entrance restituito dalla prima query).

Query fallite o non utilizzabili (nessun oggetto ospedale):
- Vito Fazzi: "Ospedale Vito Fazzi Lecce" e "Ospedale Vito Fazzi" restituiscono solo lo svincolo della tangenziale (motorway_junction), scartato; "Presidio Ospedaliero Vito Fazzi Lecce", "Vito Fazzi, Piazza Filippo Muratore, Lecce": vuote; "hospital Lecce": solo sedi ASL Lecce (Viale Don Minzoni, Maglie, Gallipoli), non il presidio.
- Policlinico di Foggia: "Policlinico Riuniti Foggia", "Policlinico Riuniti", "Ospedale Policlinico Riuniti di Foggia", "Azienda Ospedaliero-Universitaria Policlinico Foggia", "Policlinico Riuniti Foggia Viale Luigi Pinto": vuote; "Ospedali Riuniti Foggia": solo fermate bus (bus_station), scartate.
- "Fondazione San Raffaele Cittadella della Carità Taranto": vuota.
- Due query con parametri strutturati non validi ({"amenity":"hospital","city":...}), ignorati da Nominatim: risultati non pertinenti (un ostello a Troia), scartati.

Esito: 2 punti. Gli studi del Vito Fazzi (3), del Policlinico di Foggia (1) e della RSA di Taranto (1) sono mappati sul comune, con il nome della struttura nel campo luogo. Nessuna coordinata inventata o dedotta.
