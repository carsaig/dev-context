# Developer Profile & Homelab Base Context (claude.md)

## Über mich

- IT-Consultant (Data Strategy, Analytics, DevOps, Process Mining, Low-Code Automation).
- Praxis in Scrum Mastery, Product Ownership, Technical Consulting.
- Fokus: Selbst-Hosting, Automatisierung, Privacy, effiziente Wissensverwaltung.

## Persönliche Arbeitsweise & Präferenzen

- Dokumentation & Protokolle immer in Markdown, verteilt auf Craft.do und lokalen .md-Files.
- PARA-System als Organisationsstandard (Projects, Areas, Resources, Archives) – Areas ergänze ich bei Bedarf.
- Automatisierung als zentrale Produktivitätsstrategie: n8n, Node-RED, Home Assistant.
- Open Source und Self-Hosting bevorzugt; SaaS nur, wenn notwendig und möglichst EU-basiert.
- Workflows klar, modular und API-zentriert. Architekturentscheidungen und Setup als Markdown-Changelog.

## Haupt-Produktivitäts- und Wissensmanagement-App

- **Craft.do** (Mac, iOS):  
  - Hauptsächliche Notizen- und Organisationslösung.
  - Dokumentbasiert, mit PARA-basiertem Ordnungssystem.
  - Wissensstruktur soll mittelfristig mit RAG- und Graph-Lösungen ergänzt werden, da Craft keine Memory Layer kennt.
  - Ziel: Bessere Verknüpfung mit PKM, AI-gestütztem Suchen, Agenten und Knowledge-Graphen.

## Infrastruktur & Technologien

### Synology NAS (DS-723+)

- SSD/NVMe-Fokus, Stromsparen, leise.
- Docker Engine für Self-Hosting, alles unter `/volume1/docker/<applikation>/`
- Docker Compose, Portainer als UI, Reverse Proxy (meist Synology, teils NGINX).
- Backups auf Backblaze, Monitoring via Uptime Kuma.
- Netz: Tailscale (Mesh, ACLs), Headscale gelegentlich, Cloudflare für DNS, Wildcard-SSL via ACME.
- Netzwerk: Fritzbox 6660, eero WLAN, 10 Gbit LAN, 2,5 Gbit Switch.

### Homelab & Cloud

- Zwei Oracle VPS (Amsterdam/CapRover, Zürich/Coolify). Webseiten certain.cc und parr.cc liegen auf VPS Amsterdam.
- n8n als zentrale Automatisierungsplattform (Workflows: PDF-Reparatur, API-Orchestration, Notifications).
- Vector DBs: Qdrant (NAS), Supabase (Cloud), Neo4j (Test).  
- LLM-Hosting: Ollama, Open WebUI (bisher kaum aktiv), Paperless-AI, Paperless-NGX.
- RAG-Projekte (in Entwicklung): Embedding-Pipeline lokal/Cloud, Qdrant/Supabase als Storage, LlamaIndex/LangChain für Prototyping.
- Home Assistant auf eigener Hardware (Home Assistant Yellow), Zigbee/Thread/Matter, Apple Home-Integration.
- Diverse Docker-Apps: siehe Abschnitt oben.

### Networking & Security

- Fritzbox, interne NAS-Firewall (GeoIP, Portfilter), Tailscale ACLs.
- Remote-Zugriff nur via Tailscale/VPN.
- Monitoring: Uptime Kuma, Dozzle, Watchtower.

## Wichtige Plattformen & Technologie-Spezifika

### n8n (Automatisierungsplattform)

- Zentraler Baustein für Automatisierung, Orchestration, API-Flows und Notifications.
- Läuft als Docker-Container auf NAS und VPS, orchestriert:  
  - PDF-Reparatur-Workflows  
  - API-Parsen (z.B. Apple Invoice Extraction)  
  - Notification Routing (Apprise, ntfy, Discord, WhatsApp via Webhook, etc.)
- Workflows mit JSON, Webhooks, und Schnittstellen zu LLMs/DBs/Services.
- Dokumentation: [n8n Docs](https://docs.n8n.io/), [Community](https://community.n8n.io/), eigene Workflows dokumentiert in `/volume1/docker/n8n/` und Craft.do.
- Wichtig: Kontext zu Trigger-Typen, Auth-Handling, Error-Flows, und eigenen Node-Implementierungen.
- Bekannte Schwächen: Updates und Node-Kompatibilität, Langzeitstabilität bei langen Flows, gelegentliche Auth-Probleme bei APIs.

### Paperless-NGX (Dokumentenmanagement)

- Läuft als Docker-Container auf NAS.
- Genutzt für: Automatisiertes Dokumenten-Tagging, -Retitling, PDF-Ingestion (inkl. Pre-Processing via Ghostscript).
- Erweiterungen: Paperless-AI, Paperless-GPT für LLM-basierte Suche & Summarization (im Testeinsatz).
- Workflows: n8n importiert reparierte PDFs direkt ins `consume`-Verzeichnis.
- Pfade: `/volume1/docker/paperlessngx/`
- Dokumentation: [Paperless-NGX Docs](https://paperless-ngx.readthedocs.io/), [GitHub](https://github.com/paperless-ngx/paperless-ngx)
- Schwachstellen: OCR-Erkennung bei komplexen Dokumenten, PDF-Kompatibilität, API-Integrationen, Performance bei großen Beständen.

### Home Assistant

- Läuft auf Home Assistant Yellow (eigene Hardware), Zigbee/Thread, Matter, Apple Home-Integration.
- Automation, Sensorik, Steuerung Licht/Medien/Sport-Setup.
- YAML-basierte Automationen bevorzugt, visuelle Anpassungen im UI.
- Doku: [Home Assistant Docs](https://www.home-assistant.io/docs/), Automationen teils in Craft.do, teils im NAS-Dokumentationsordner.
- Schwächen: Zigbee/Matter-Integration bei neuen Geräten, gelegentliche Automations-Bugs, Edge Cases mit iOS-Präsenz.

### Anytype (PKM)

- Ziel: Anytype als zentrales PKM (Personal Knowledge Management).
- Testweise Self-Hosting auf NAS per Docker geplant.
- Bisher: Hauptwissen liegt noch in Craft notes, Transfer zu Anytype (inkl. API/MCP-Anbindung) in Vorbereitung.
- Vision: Verknüpfung mit RAG/Graph-DB für tiefere Wissensintegration.
- Doku: [Anytype Docs](https://docs.anytype.io/), [GitHub](https://github.com/anyproto/anytype-ts), [Community](https://community.anytype.io/)

### Craft.do / Craft notes (PKM/Produktivität)

- Haupt-App für tägliche Notizen, Protokolle, Ideen, Entscheidungslogs, Meeting Notes, Projektjournale.
- Organisation nach PARA, aber durch dokumentbasierten Ansatz oft fragmentiert.
- Vision: Automatisierte Extraktion, Memory Layer, Verknüpfung zu Anytype und AI-gestützte Suche (RAG, Agents).
- API limitiert, daher bisher keine tiefere Automatisierung – Experimentierfelder offen für Agentic AI.
- Doku: [Craft Help Center](https://support.craft.do/), eigene Struktur in Craft laufend gepflegt.

---

## Dokumentation & Entscheidungsfindung

- Alle Setups, Logs und Entscheidungsfindung in Markdown, verteilt auf NAS (`/volume1/docs/`), Craft notes, zum Teil in (veralteter) Atlassian Confluence.
- PARA-Standardisierung über Apps und Projekte, Ziel: Durchgängige, graphbasierte Wissenslandschaft.
- RAG- und Agenten-Lösung als mittelfristiges Ziel für kontextbasierte Suche und Wissensvernetzung.

---

## Arbeitsstil & Standards

- Jedes neue Projekt bekommt eine ausführliche Projektbeschreibung als `claude.md` im Root.
- Alle Konfigurationen, Shell-Skripte und Docker Compose Files sind verständlich kommentiert und dokumentiert.
- Einheitliche Volumestruktur für alle Container (`/volume1/docker/<app>`).
- Klare Entscheidung für lokale-first- und Open-Source-Lösungen, EU-Hosting bevorzugt.

---

## Bekannte Schwachpunkte & TODOs

- Reverse Proxy (Synology) limitiert → Migration/VPS-Auslagerung für kritische Apps.
- Qdrant UI schwach → Wechsel/Parallelbetrieb mit Supabase (Cloud), Neo4j als Knowledge Graph im Test.
- RAG/Agenten-Lösungen im Aufbau, Wissensstruktur in Craft.do chaotisch → Ziel: Konsolidierung via Anytype und RAG.
- Bisher keine produktive Graph- oder Memory-Layer-Lösung → Experimentierfeld für AI Agents.
- Home Assistant Automationen für Spezialfälle (Edge Cases) noch optimierungsbedürftig.

---

## [Optional] Häufig genutzte Projekte & Pfade

- Paperless-NGX: `/volume1/docker/paperlessngx/`
- Open WebUI: `/volume1/docker/openwebui/`
- Home Assistant: `/volume1/docker/homeassistant/`
- n8n: `/volume1/docker/n8n/`
- Qdrant: `/volume1/docker/qdrant/`
- Anytype Self-Hosting: `/volume1/docker/anytype/`
- Craft notes: lokal auf Mac, synchronisiert mit Craft Cloud

---

**Technologie-Spezifika für Claude:**  
Wenn Rückfragen zu n8n, Paperless-NGX, Home Assistant, Anytype oder Craft auftreten, ziehe zuerst die offizielle Dokumentation der jeweiligen Plattform heran.  
Berücksichtige stets die Architektur und Workflows aus diesem Grundkontext.  
Frage bei Unsicherheit gezielt nach Projekt-spezifischer `claude.md` oder relevanten Detail-Logs.
