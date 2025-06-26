# Developer Profile & Homelab Base Context (claude.md)

## Über mich

- IT-Consultant (Data Strategy, Analytics, DevOps, Process Mining, Low-Code Automation).
- Fokus: Selbst-Hosting, Automatisierung, Privacy, effiziente Wissensverwaltung.
- Persönliches Ziel: Alle Daten, Wissen und Projektressourcen systematisch, automatisiert und konzeptuell zugänglich machen (Memory Layer / RAG / Knowledge Graph / AI-Assistenz).

## Persönliche Arbeitsweise & Präferenzen

- Bevorzuge strukturierte, dokumentierte Workflows in Markdown.
- PARA (Projects, Areas, Resources, Archives) als Meta-Framework für alle Organisationsebenen – die genaue Struktur/Area-Liste passe ich bei Bedarf projektbezogen an.
- Automatisierung (n8n, Node-RED, Home Assistant) und API-first-Prinzip.
- Open Source und Self-Hosting bevorzugt. SaaS-Lösungen nur, wenn sinnvoll und (möglichst) EU-basiert.
- Kontinuierliche Verbesserung der Arbeitsweise und Tool-Landschaft durch Retrospektiven und Dokumentation.

## Tool- und Datenlandschaft

### Speicherorte & Fragmentierung (Stand 2025-06)

- **Craft Notes** (ca. 70% meines Wissens)  
  - Haupt-Notiz- und Wissensspeicher.  
  - Enthält: Meeting-Notes, Consulting-Know-how, Projekte, Methoden, Entwürfe, Protokolle, Entscheidungslogs.
  - PARA-Struktur als Ordnungsrahmen, aber aufgrund des Dokumentenansatzes oft fragmentiert.

- **Synology Drive/NAS** (ca. 20% der Wissensinhalte, 80-90% aller Projektdaten und Ressourcen)  
  - Hauptspeicher für: Dateien, Projektunterlagen, Code, Ressourcen, Automations-Workflows, Doku, Backups.  
  - Struktur: Einheitliche Volumestruktur unter `/volume1/docker/<app>/` und `/volume1/docs/`
  - Zentrale Dateiablage, teilweise auch als Sync-Quelle für andere Tools genutzt.

- **Miro** (ca. 10% des Wissens, meist Visualisierungen & Prototypen)  
  - Verwendung: Visuelle Projektplanung, Mindmaps, schnelle Konzepte, Workshops.
  - Problem: Proprietär, sehr teuer, langfristig abzulösen. Bedarf: Mächtiges Board-Tool für Prototyping, Brainstorming, Visualisierung, aber lokal/self-hosted oder günstiger.
  - Ziel: Migration auf eine alternative Whiteboard/Diagramm-Lösung (offen, vernetzt, API-zugänglich).

- **Atlassian Confluence** (historisch, ca. 5%)  
  - Veraltete Dokumentationen, Alt-Projekte, kaum gepflegt.

- **Anytype** (Test, ca. 1%)  
  - PKM-Lösung, lokale App auf Mac (nicht auf NAS!), Ziel: künftige Integration als Memory Layer, Knowledge Graph, API-Zugriff über MCP/SSE-Proxy in Vorbereitung.

### Weiteres

- **Projektdaten und Ressourcen:**  
  - Liegen primär auf Synology NAS.
  - Wissen/Beschreibung dazu in Craft Notes, Überblick/Struktur oft in Miro.

- **KI/LLM-Tools:**  
  - Ollama (Mac, Testbetrieb), OpenAI, Gemini, Claude, OpenRouter für LLMs/Agents.
  - Bisher keine produktiv eingesetzte lokale LLM-Instanz (Performance ungenügend).

## Infrastruktur & Technologien

- Synology NAS DS-723+, SSD/NVMe, Docker Compose, Portainer, NGINX/Synology Proxy.
- VPS (Oracle, Ubuntu, Amsterdam/CapRover, Zürich/Coolify) für ausgelagerte Dienste (z.B. Karakeep, Budibase, Webseiten certain.cc und parr.cc).
- n8n als zentrale Automatisierung, Home Assistant auf Home Assistant Yellow (eigene Hardware).
- VectorDB: Qdrant (NAS), Supabase (Cloud), Neo4j (Test).
- RAG-Projekte im Aufbau, Ziel: Vollständig autonome und vernetzte Wissens- und Dokumenteninfrastruktur.

## Dokumentation & Entscheidungsfindung

- Markdown-Dokus verteilt auf NAS, Craft Notes, teils Confluence.
- Entscheidungslogs, Changelogs und technische Doku so weit möglich zentral auf NAS, aber faktisch oft fragmentiert (daher Meta-Projekt: Wissenskonsolidierung).
- PARA als Ordnungs- und Meta-Framework.

---

## Wichtige Plattformen & Technologie-Spezifika

### n8n  
- Haupt-Automatisierungsplattform (Docker), orchestriert alle Datenflüsse zwischen Systemen/Apps/Dateien.
- Workflows: API-Orchestration, PDF-Reparatur, Parsing, Notification-Routing.
- Kontext: [n8n Docs](https://docs.n8n.io/)  
- Eigene Flows und Schnittstellen möglichst in Markdown dokumentiert.

### Paperless-NGX  
- Dokumentenmanagement, automatische Verschlagwortung und Integration mit n8n-Workflows.
- Kontext: [Paperless-NGX Docs](https://paperless-ngx.readthedocs.io/)

### Home Assistant  
- Zentrale Smarthome-Steuerung, YAML-basierte Automationen bevorzugt.
- Kontext: [Home Assistant Docs](https://www.home-assistant.io/docs/)

### Anytype  
- PKM-Experiment, lokal auf Mac.  
- Ziel: Mittelfristige Nutzung als Memory Layer, Graph und für API-gesteuerte Automation.
- MCP-Server-Proxy in Vorbereitung (Ziel: Protokollumwandlung STDIO → SSE).

### Craft Notes  
- Haupt-Produktivitäts- und Wissens-App (Mac, iOS, Craft Cloud).
- PARA-Struktur, aber Daten oft schwer durchsuchbar/vernetzt.
- Ziel: KI-gestützte, agentenbasierte Suche, Memory Layer, Knowledge-Graph-Anbindung.

### Miro  
- Visuelles Prototyping, Projektvisualisierung, Mindmaps.
- Akuter Bedarf an Miro-Alternative (Self-Hosting oder Open Source).

---

## Arbeitsstil & Standards

- Jedes neue Projekt: Projektbeschreibung als `claude.md` im Root.
- Alle Docker Compose Files, Skripte, Setups verständlich kommentiert.
- Offene Baustelle: Einheitliches Datenmodell über alle Apps/Plattformen hinweg (Meta-Projekt „Wissens- und Dateimodellierung“).

---

## Meta-Projekt: Datenmodellierung & Wissensstrukturierung

- Aktuelle Herausforderung: Datenfragmentierung, fehlende einheitliche Kontext- und Wissensstruktur, keine zentrale Abbildung von Beziehungen und Kontexten zwischen Dateien, Ressourcen und Notizen über App-Grenzen hinweg.
- Ziel: Entwicklung eines homogenen Datenmodells/Kontextmodells, das PARA ergänzt und über alle Apps und Systeme anwendbar ist (z.B. über Knowledge Graph, RAG, PKM-API-Integration, Agentic AI).
- Tasks:  
  - Modellierung der wichtigsten Entitäten und Beziehungen (z.B. Projekt ↔ Dateien ↔ Notizen ↔ Ressourcen ↔ Visualisierungen).
  - Schaffung von Schnittstellen zu Craft, Synology, Miro, Anytype, Home Assistant, n8n.
  - Konsolidierung der Entscheidungs-, Changelog- und Ressourcenverwaltung über alle Systeme hinweg.

---

## Bekannte Schwachpunkte & TODOs

- Daten und Wissen stark fragmentiert auf Craft, NAS, Miro, Confluence, Anytype.
- Übersicht, Quervernetzung und effiziente Suche aktuell nur eingeschränkt möglich.
- Miro als Visualisierungs-Tool zu teuer, Alternativen werden gesucht.
- Anytype als PKM-Tool lokal, API-Anbindung in Entwicklung, keine zentrale Integration bisher.
- Kein universelles Datenmodell für Wissens- und Dateistrukturen – Entwicklung als zentrales Meta-Projekt.
- Consulting- und Projektmanagement-Know-how muss aufgefrischt, systematisiert und durch intelligente Workflows/Agents gestützt werden.

---

**Hinweis für Claude:**  
Berücksichtige stets die oben skizzierten Speicherorte, Workflows und Fragmentierungen bei Kontext-, Wissens- und Automatisierungsaufgaben. Nutze für Deep Dives oder bei Unklarheiten die Dokumentation der jeweiligen Plattform und hinterfrage Datenstrukturen, wenn uneinheitlich.  
Wichtige Anforderung: Ergebnisse müssen robust, durchsuchbar und über Systemgrenzen hinweg integrierbar werden.
