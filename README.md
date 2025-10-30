# 11) Hybrid Trust for E-Collecting

wir alle wollen die direkte Demokratie digitaler machen – aber nicht flacher.

Heute entstehen Initiativen aus Begegnung: am Bahnhof, auf dem Markt, im persönlichen Gespräch. Wenn wir E-Collecting komplett ins Web verlagern, öffnen wir die Tür für Bots, Massenmobilisierung und algorithmische Emotion statt echter Überzeugung.

Deshalb brauchen wir eine Grenze – aber keine künstliche.

Manche schlagen Obergrenzen oder Kontingente für digitale Unterschriften vor. Doch das wäre diskriminierend innerhalb der Sammelfrist:
Wer früher unterschreibt, zählt; wer später kommt, nicht mehr. Demokratie ist aber kein „first-come-first-served“-System.

Der richtige Weg ist hybrid:
Sammler:innen bleiben auf der Strasse – aber mit einer App, die über Near Field oder Bluetooth eine temporäre Signatur-Session öffnet.
Bürger:innen unterschreiben direkt vor Ort, digital, nachvollziehbar, aber mit persönlicher Interaktion.

So digitalisieren wir die Verwaltung, nicht die Überzeugung.
Wir schaffen Effizienz im Back-Office – aber halten den demokratischen Diskurs lebendig.

Unser Ziel: Technologie, die Demokratie stärkt, nicht ersetzt.


Unser Konzept heisst Hybrid Trust for E-Collecting.

Es basiert auf einem einfachen Prinzip:
Digitalisierung darf Prozesse beschleunigen, aber nicht Menschen ersetzen.

Jede Sammler:in wird digital authentifiziert und kann vor Ort einen kurzlebigen QR-Code erzeugen.
Bürger:innen scannen diesen Code mit ihrer eID- oder Wallet-App und signieren die Unterstützung.
Die Daten werden automatisch validiert, dedupliziert und im Audit-Ledger erfasst – aber die Begegnung bleibt physisch.

Damit verhindern wir populistische Massenkampagnen und gleichzeitig auch digitale Diskriminierung:
Kein Modell mit Obergrenzen oder Kontingenten, die Menschen ausschliessen,
sondern Gleichbehandlung aller Bürger:innen während der gesamten Sammelfrist.

Auf technischer Ebene:
– temporäre QR-Sessions über Bluetooth oder Near Field,
– Verifiable Credentials oder QeS-Signaturen,
– automatisierte Back-Office-Prüfungen per OCR und LLM-Validierung.

Das Ergebnis ist ein faires, inklusives, auditierbares System,
das Effizienz und Legitimität gleichzeitig wahrt – ein Schritt zu einer digital gestützten, aber weiterhin menschlichen Demokratie.

Digitalisierung der Verifikation – nicht der Überzeugung.
Democracy by Design, nicht by Algorithm.

Kernaussage: Wir behalten die physische Begegnung beim Sammeln bei (Stand, Markt, HB), digitalisieren aber Validierung, Dublettenprüfung und Audit. Keine viralen Web-Links, keine Bots – stattdessen ortsgebundene, kurzlebige QR-Sessions und ein Backoffice-Pipeline mit OCR + 4-Modell-Consensus.

## Inhaltsverzeichnis
	1.	Problem & Zielbild
	2.	Scope & Nicht-Ziele
	3.	User Journeys (Stimmberechtigte, Sammler:in, Gemeinde, BK)
	4.	Architektur (Mermaid: Flowchart & Sequenz)
	5.	Datenflüsse & Datenmodell
	6.	Sicherheit, Vertrauen & Governance
	7.	Barrierefreiheit (Accessibility)
	8.	Integration Papierkanal & Backoffice-Automatisierung (OCR + 4×LLM)
	9.	APIs (Beispiel-Endpoints & Payloads)
	10.	Audit, Monitoring & Metriken
	11.	Roadmap (Phase 1 Hybrid → Phase 2 Remote mit neuen Grenzwerten)
	12.	Topics-Mapping zum Leitfaden
	13.	PoC: Lokales Setup (Vorschlag)
	14.	Pitch-One-Pager (Kurztext)
	15.	Lizenz & Hinweis

# 1) Problem & Zielbild

Problem: 
E-Collecting ist eine notwendige Weiterentwicklung der direkten Demokratie.

Doch die derzeitige Diskussion konzentriert sich zu stark auf digitale Vereinfachung, statt auf demokratische Verantwortung.



Wenn Unterschriften künftig nur noch online gesammelt werden, entstehen erhebliche Risiken:

Populistische Massenmobilisierung über Bots und Social-Media-Kampagnen

Verlust der analogen Begegnung – des sozialen Kitts der Schweizer Demokratie

Diskriminierung durch technische Obergrenzen („max. 10 000 digitale Signaturen“)

Ungleichheit innerhalb der Sammelfrist – eine „First Come First Served-Demokratie“

Digitalisierung darf die Demokratie unterstützen, nicht ersetzen.

Darum braucht es eine klare Abgrenzung zwischen Effizienzsteigerung und Ersetzungsmechanismus.

Zielbild:
	•	Hybridität: Sammlung bleibt physisch initiiert, Signatur digital vor Ort (NFC/Bluetooth/Proximity) über zeitlich/örtlich gebundene QR-Sessions, faktisch neben dem Zettel für diskriminierungsfreie Unterschriftssammlung
	•	Einfaches Sammeln, statt Zettel drucken und Sammeln, nun einfach mit App sammeln, einfach auf der Webseite anonym sich als sammler mit der App melden, sodass die app nun unterschriften sammeln kann, also wie eine PDF runterladen und drucken.
	•	Digitalisierung im Backoffice: automatische Verifikation, Dubletten-Check, Audit-Trail.
	•	Fairness & Inklusion: Kein Ausschluss, keine Obergrenzen; Papier bleibt integriert.

Leitsatz: Digitalisiere die Verifikation – nicht die Überzeugung.

# 2) Scope & Nicht-Ziele

Scope
	•	Vor-Ort-Signatur via Wallet/eID nach Scan eines ephemeren QR-Codes, ausgestellt von verifizierter Sammler-App.
	•	Backoffice-Pipeline: OCR + 4-Modell-Consensus (Parser/Normaliser/Embedding-Dedup/Validator).
	•	Audit-Ledger (Merkle) und Anomalie-Erkennung.

Nicht-Ziele
	•	Kein reines Remote-Web-Signing in Phase 1.
	•	Keine virale Online-Verteilung statischer QR/URLs.
	•	Keine Veränderung der demokratischen Schwellenwerte in Phase 1.

# 3) User Journeys (ergänzt)

## 3.1 Stimmberechtigte Person (mit eID/QES + QR+BLE)
	1.	Begegnung am Stand → QR des/der Sammler:in scannen.
	2.	Wallet/eID-App öffnet die amtlichen Infos (Titel/Wortlaut etc.).
	3.	Automatisch startet ein Bluetooth-Handshake zwischen beiden Apps (Proximity-Proof).
	4.	Bürger:in signiert mit QES (oder VC-Proof) die Unterstützungsbekundung.
	5.	Backend prüft & stellt einen signierten Receipt (JWS/JAdES) mit Hash der Bekundung aus → wird in der Wallet gespeichert.

## 3.2 Sammler:in (pseudonym möglich, wie heute faktisch)
	•	App ist für alle frei verfügbar.
	•	Sammler:in wählt laufende Kampagne in der App und meldet sich pseudonym an (siehe Governance: rate limits / Missbrauchs-Sperre).
	•	Startet ephemere QR-Session, die BLE-Handshake erzwingt (kein Remote-Web-Signing).
	•	Sieht nur Zähler/Status (keine PII).

Pseudonym ≠ Verantwortungslosigkeit: Die Plattform erzwingt Device-Attestation, Session-Limits & Revocation. Eine allfällige Deanonymisierung erfolgt ausschliesslich bei Missbrauch gemäss Governance (gerichtlich/behördlich).

# 4) Architektur

## 4.1 Flowchart

flowchart TD
 flowchart TD
  A[Citizen Wallet/eID] -- Scan QR --> B[Collector App]
  A <--> |BLE Handshake (ECDH, nonces)| B
  A --> |QES/VC Signed Support + Transcript Hash| C[E-Collecting API]
  B --> |Collector Device Attest + Session Proof| C
  C --> D[Verifier & Dedup]
  D --> E[Backoffice OCR+4-LLM Consensus]
  D --> F[Receipt Service (JWS/JAdES)]
  F --> A
  E --> G[Commune Review UI]
  D --> H[Audit Merkle Ledger]
  G --> I[BK Aggregation]

## 4.2 Sequenzdiagramm

sequenceDiagram
  sequenceDiagram
  participant Collector as Collector App
  participant Citizen as Wallet/eID
  participant API as E-Collecting API
  participant Back as Backoffice
  participant Rec as Receipt Service

  Collector->>Collector: Start QR Session (ttl, geo)
  Citizen->>Collector: Scan QR (session_id)
  Citizen<->>Collector: BLE handshake (nonces, ECDH -> session_key)
  Citizen->>Citizen: QES sign (support + transcript_hash)
  Collector->>API: session_id + device_attest + collector_sig
  Citizen->>API: support_payload + QES_sig + transcript_hash
  API->>Back: verify QES, dedup, store, audit append
  API->>Rec: issue signed receipt (JWS/JAdES)
  Rec-->>Citizen: receipt_token
  Back-->>Collector: counter/status (no PII)

# 5) Datenflüsse & Datenmodell
Handshake-Transcript (beidseitig gebunden):
	•	transcript = H(session_id || nonce_citizen || nonce_collector || ecdh_pubkeys || ts)
	•	transcript_hash wird in QES-Signatur (Citizen) eingebettet und vom Backend geprüft.

Receipt (Bürger-Quittung):
	•	receipt_token = JWS/JAdES, enthält:
receipt_id, support_hash, transcript_hash, ts, initiative_id, ledger_leaf_ref, sig_platform

Sammler Pseudonymisierung:
	•	collector_pseudo_id = H(device_attest_key || platform_salt)
	•	Keine PII erforderlich; Missbrauch → revocation des attestierten Geräts/Keys.

Neue/ergänzte Felder:
	•	sessions(..., bt_required=true, ble_session_pubkey, ...)
	•	supports(..., transcript_hash, qes_sig, receipt_id, ...)
	•	collector_devices(device_attest_key, attest_vendor, revoked)
	•	receipts(receipt_id, support_hash, transcript_hash, jws_blob, ts)

# 6) Sicherheit, Vertrauen & Governance (präzisiert)
	•	BLE-Pflicht: Jede Signatur setzt BLE-Handshake voraus → harte Proximity.
	•	ECDH-Session-Key: Schutz gegen Replay/MITM; transcript_hash bindet beide Seiten.
	•	QES/VC-Bindung: Bürger:in signiert Support + Transcript → Nachweis: „Ich war physisch da“.
	•	Receipt by Design: Signierter Rückschein (JWS/JAdES) mit Merkle-Referenz → Bürger:in kann später Existenz prüfen, ohne PII offenzulegen.
	•	Pseudonyme Sammler: Offen für alle (niedrige Eintrittsschwelle wie heute), aber accountable via Device-Attestation, Rate-Limit & Revocation-List.
	•	Anti-Missbrauch: Session-TTL (5–10 min), kein statischer QR/Link, Geo-Anomalien-Detektor, Volumen-Heuristiken, manuelle Audit-Flags.
	•	Datenschutz: Data-Minimisation (nur Hashes/Proofs), Verschlüsselung, strenge Retention.
	•	Governance: Kurzschulung in-App, Code of Conduct, klarer Sperrprozess (Missbrauch → Revoke).

Hinweis: Diese Ausgestaltung erfüllt die Leitfaden-Anforderung nach Vertrauenswürdigkeit, Sicherheit, Barrierefreiheit sowie Integration mit Papierkanal (Backoffice-Automatisierung bleibt unverändert).  ￼

⸻

# 8) Integration Papierkanal & Backoffice (unverändert gültig)
	•	OCR → 4×LLM-Consensus bleibt der gleiche (Auto-Validate bei 4/4; sonst Gemeinde-Queue).
	•	BLE/Receipt-Logik betrifft nur den digitalen Vor-Ort-Kanal; Papier-Import ist davon unabhängig.

# 9) APIs (Beispiele)

## 9.1 Session starten (Sammler:in)

**POST** `/api/session/init`

**Request**
```json
{
  "initiative_id": "init-2025-xyz",
  "ttl_sec": 600,
  "geo_hash": "u0ndh",
  "bt_required": true
}
```

**Response**
```json
{
  "session_id": "sess-abc",
  "qr_png": "data:image/png;base64,...",
  "ble_advert": "BLE:team11:e23f...",
  "expires": "2025-10-31T10:05:00Z"
}
```
## 9.2 BLE-Handshake (Citizen ↔ Collector)

**POST** `/api/handshake/commit`

**Request**
```json
{
  "session_id": "sess-abc",
  "collector_attest": "attest-jws",
  "collector_sig": "jws(transcript_hash)",
  "citizen_transcript_hash": "base64(H(...))"
}
```
**Response**
```json
{
  "status": "ok",
  "session_state": "active"
}
```

## 9.3 Support abgeben (Bürger:in, eID/QES)

**POST** `/api/support`

**Request**
```json
{
  "session_id": "sess-abc",
  "support_payload": {
    "initiative_id": "init-2025-xyz",
    "transcript_hash": "base64(H(...))",
    "citizen_proof": "VC-or-IdRef"
  },
  "qes_signature": "JAdES/JWS",
  "ts": "2025-10-31T10:01:23Z"
}
```
**Response**
```json
{
  "decision": "accepted",
  "receipt_token": "JWS/JAdES ...",
  "ledger_leaf_ref": "merkle-idx-12345"
}
```

## 9.4 Review-Queue für Gemeinden

**GET** `/api/review/queue?status=flagged`

**Response**
```json
[
  {
    "row_id": "r-0001",
    "reason": "model_disagreement",
    "ocr_conf": 0.83,
    "models_agree": 2
  }
]
```

## 9.5 Gemeinde entscheidet

**POST** `/api/review/{row_id}`

**Request**
```json
{
  "decision": "accept | reject | edit",
  "note": "Korrektur nach manuellem Check"
}
```

**Response**
```json
{
  "status": "updated"
}
```

## 9.6 Receipt (Signatur-Bestätigung abholen)

**GET** `/api/receipt/{receipt_id}`

**Response**
```json
{
  "receipt_id": "rcpt-88921",
  "support_hash": "sha256:abc123...",
  "transcript_hash": "sha256:def456...",
  "initiative_id": "init-2025-xyz",
  "ledger_leaf_ref": "merkle-idx-12345",
  "issued_at": "2025-10-31T10:02:00Z",
  "platform_signature": "JWS/JAdES..."
}
```

## 10) Audit, Monitoring & Metriken
	•	Audit: pro Zeile Merkle-Leaf; täglicher Root veröffentlichbar.
	•	Metriken: Auto-Validation-Rate, OCR-Confidence-Verteilung, False-Positive-Quote (Audit-Sample), Zeit bis Validierung, Queue-Backlog, Model-Disagreement.
	•	Dashboards: Kommune/BK Live-Überblicke (Heatmap Sessions, Anomalien).


## 11) Roadmap 
	•	Phase 1 – Hybrid Vor-Ort: QR + BLE-Handshake zwingend, QES/VC, Receipt, pseudonyme Sammler mit Attestation & Revocation.
	•	Phase 2 – Kontrollierte Remote-Öffnung nur bei gleichzeitiger Anpassung demokratischer Parameter (Quoren/Fristen/Gewichtungen) und zusätzlichen Missbrauchs-Schranken.

## 12) Topics-Mapping 
	•	Topic 1 (Journey): Vor-Ort-Journey + Prävention viraler Links.  ￼
	•	Topic 2 (Infos/Tracking): Dashboard + optionaler Citizen-Receipt/Tracker-Hash.  ￼
	•	Topic 3 (Zuschreibung): Session enthält collector_id; Zuschreibung ohne Bias-Liste.  ￼
	•	Topic 4 (Argumente): Nur amtliche Texte im Wallet-Screen; Komitee-Infos klar abgetrennt.  ￼
	•	Topic 5 (Unrechtmässige Ausschliessen): starke Auth, Signatur/Proof + Dedup.  ￼
	•	Topic 6 (Unterschlagung verhindern): Public Audit-Merkle + (optional) Citizen-Tracker.  ￼
	•	Topic 7 (Stimmgeheimnis): Pseudonymisierung, minimierte Metadaten, Löschkonzept.  ￼
	•	Topic 8 (Integration Papier): OCR + 4-LLM-Consensus, Manual Queue.  ￼
	•	Topic 9 (Einführung Gemeinden): Lightweight: Exporte, Druckoptionen, Bestehendes nutzen.  ￼
	•	Topic 10 (Föderale Ebenen): Schlanke Schnittstellen; Parameterisierbare Rollen/IDs.


## 13) PoC: Lokales Setup (Vorschlag)

	•	Eine React app die zwei rollen hat, einmal kann jemand eine PDF starten, und dann signaturen sammeln, die mit eID und bluetooth handshake gelöst wird
	•	python Backend der Gemeinde kriegt eingescante unterschriften oder diese PDF signiert von App wegen zugehörigkeit der App und dann die ganzen unterschriften, die über bluetooth mit eID und der app gelöst wurden
	•	Geminde hat automatischen validator und LLM Komitee mit einer Open Source gehosteten Model, die das eingescante analsiert. Die Namen die automatisch gelesen werden konnten, werden gleich mit dem Einwohnerregister und Gemeindenzugehörigkeit verglichen, die, die nicht automatisch eingelesen werden konnten, müssen manuell als ticket zu einem Gemeindemitarbeiter gehen.

## 14) Pitch-One-Pager 
Problem: Web-Signing macht Sammeln anonym/viral; Obergrenzen diskriminieren.
Lösung: Vor-Ort-Hybrid mit QR + Bluetooth-Handshake (Proximity-Proof) und QES/VC.
Receipt: Signierter JWS/JAdES-Beleg mit Merkle-Referenz (prüfbar ohne PII).
Sammler: Offen & pseudonym, aber accountable (Device-Attestation, Limits, Revocation).
Backoffice: OCR + 4×LLM-Consensus → Auto-Validate/Flag; Gemeinde sieht nur Konflikte.
Roadmap: Phase 1 Hybrid (kein Remote). Phase 2 Remote nur mit neuen Grenzwerten/Regeln.



## Lizenz & Urheberrecht

Copyright © 2025 Roman Zoun

Dieses Konzept, Design und die technische Spezifikation unterliegen dem Urheberrecht.
Eine Nutzung, Reproduktion oder Weiterentwicklung des hier beschriebenen Modells ist nur nach vorheriger schriftlicher Zustimmung des Autors zulässig.

Eine Umsetzung in jeder Form erfordert meine ausdrückliche Genehmigung.

Kontakt für Lizenzanfragen: Roman Zoun (roman.zoun(at)gmail.com)




