# Developer Profile & Homelab Base Context (claude.md)

## Über mich

- IT-Consultant (Data Strategy, Analytics, DevOps, Process Mining, Low-Code Automation)
- Fokusthemen: Selbst-Hosting, Automatisierung, Privacy, effiziente Wissensverwaltung
- Ziel: Alle Daten, Wissen und Projektressourcen systematisch, automatisiert und konzeptuell zugänglich machen (Memory Layer, RAG, Knowledge Graph, AI-Assistenz)
- Aktuell auf aktiver Jobsuche – gezielter Aufbau von KI-, RAG- und Automatisierungs-Know-how für den nächsten Karriereschritt

---

## Organisations- und Arbeitsweise

- **PARA** (Projects, Areas, Resources, Archives) als zentrales Organisationsframework  
  - **Areas** u.a.: Learning/Education, Marketing, AI, Family, Household, Finance, Hobby, IT, Cooking, Holiday, Career
  - PARA-Inbox als globaler Sammelpunkt
- Markdown-First-Dokumentation (lokal & in Craft Notes), strukturierte Entscheidungslogs & Protokolle
- Automatisierung via **n8n**, Node-RED, Home Assistant (API-zentriert)
- Open Source & Self-Hosting bevorzugt; SaaS nur wenn sinnvoll und möglichst EU-basiert
- Stetige Verbesserung durch Retrospektiven & Meta-Projekte
- LaTeX für anspruchsvolle Dokumente (Overleaf, LyX, MacTex)
- Transkription: Mac Whisper

---

## Tool- & Datenlandschaft (Speicherorte und Fragmentierung)

- **Craft Notes** (~70% Wissensanteil)
  - Zentrale Wissens- und Notizbasis (Meetings, Consulting, Projekte, Methoden, Protokolle)
  - PARA-basiert, aber fragmentiert, schwer systemübergreifend vernetzbar
  - MIGRATION: Mittelfristige Ablösung/Migration zu Anytype oder ähnlich vernetztem PKM geplant

- **Synology NAS / Synology Drive** (~20% Wissen, 80–90% Projektdaten/Ressourcen)
  - Hauptspeicher für Files, Code, Automationsworkflows, Doku, Backups
  - Struktur: `/volume1/docker/<app>/`, `/volume1/docs/`

- **Miro** (~10% Wissen)
  - Visuelle Planung, Mindmaps, Prototyping, Workshops
  - Migration zu Self-Hosted/OSS Whiteboard-Lösung geplant

- **Atlassian Confluence** (~5%, historisch)
  - Veraltete Doku – geplante Migration in zentrale Wissensbasis

- **Anytype** (~1%, im Aufbau)
  - Lokale PKM-App auf Mac, Memory Layer, Knowledge Graph, API-Anbindung/MCP-Proxy in Entwicklung

- **Dropbox / Google Drive**
  - Nicht mehr produktiv, alles auf Synology bzw. GDrive nur für n8n-Testworkflows

- **Lokaler Mac Speicher für Dev-Projekte**  
  `/Users/jc/Documents/Development/` (Trennung nach Github, Gitlab, MCP-Server, Einzelprojekten – Migration zu zentralem Git-Modell geplant)

---

### Weiteres: Cloud/SaaS, Bookmarks, Socials, Kalender, etc.

- **Cloud/SaaS Plattformen:** Adguard-DNS, NextDNS, Fabric.so, Tailscale, 1Password, Docker Hub, Craft, Google Workspace, Github, Miro
- **Bookmarks & Quellplattformen:** Medium, YouTube, Substack, Reddit, Patreon, Discord, (kein/erschwerter Export: Spiegel, SZ, Zeit)
- **Social Media:** Minimal privat (Facebook/Instagram selten), beruflich LinkedIn/Xing
- **Datenorchestrierung:** n8n zentral, Zapier/IFTTT als Fallback
- **Kalender & Kontakte:** Primär Apple, Google als Ausweich, Migration zu Google geprüft
- **Produktivitäts-/Utility Apps lokal:** 1Password, Adguard/NextDNS, Adobe Stack, Anki, App Flowy, Bitwarden/Vaultwarden, CleanMyMac, Discord, Home Assistant, Apple Home, Kalender, Kontakte, LittleSnitch, Spark, MS Office, Apple Music/Spotify, PDF-Tools, Postman, Proxyman, Charles, Shottr, Sprachmemos, Synology Drive, Bear, Sublime Text (Abbau), Transmit, VLC, VMWare Fusion, XLD, Zotero, Wiso Steuer, Zwift, Docker Desktop, Whatsapp, Threema, Telegram, Blocs, Wordpress (historisch), statisches Sitebuilding bevorzugt
- **Code Assistants & IDEs:** Zed, Cursor, Windsurf, VS Code (+ Extensions), Roo-Code, Cline, Continue, Testing ongoing
- **Browser:** Brave (primär), Chrome/Firefox/Safari (gelegentlich)

---

## KI/LLM-Tools & MCP Server

- **LLM Clients & Anbieter:** ChatGPT, Claude, Gemini, OpenRouter, Perplexity, Witsy, 5ire, Msty App, CherryStudio, NextChat (laufend getestet)
- **Genutzte LLM Modelle:** Google, OpenAI, Anthropic, Huggingface
- **LLM lokal:** Ollama, GPT4All, AnythingLLM, Msty (alles nur experimentell)
- **MCP Server:**  
  - Experimenteller Betrieb auf Mac & Docker (u.a. sequential-thinking, github, perplexity-ask, exa, puppeteer, Context7, n8n, openmemory/mem0, supabase, siri-shortcuts, karakeep, travel-planner, api-jeanmemory-com, paperless-mcp, mcp-supermemory-ai, messages)
  - Ziel: zentraler, via Proxy angebundener Stack auf NAS; Fokus auf Memory Layer, Echtzeitsuche, lokale Systemanbindung, Knowledge Graph/RAG, DevOps, Produktivität, Planning, Dokumentenmanagement, Marketing, Data Wrangling, Apple-Ökosystem-Integration, Schnittstelle zu lokalen Mac-Programmen

---

## Plattformen & Technologie-Spezifika

- **n8n:** Haupt-Automatisierungsplattform (Docker), orchestriert API-Flows, Parsing, PDF, Notifications  
  - [n8n Docs](https://docs.n8n.io/)
- **Paperless-NGX:** Dokumentenmanagement, automatische Verschlagwortung, n8n-Integration  
  - [Paperless-NGX Docs](https://paperless-ngx.readthedocs.io/)
- **Home Assistant:** Smarthome-Steuerung, YAML-Automationen  
  - [Home Assistant Docs](https://www.home-assistant.io/docs/)
- **Anytype:** Lokales PKM, API/Graph/MCP geplant  
  - [Anytype Docs](https://docs.anytype.io/)
- **Craft Notes:** Haupt-Wissensspeicher, PARA, Memory Layer/Knowledge Graph geplant  
  - [Craft Help](https://support.craft.do/)
- **Miro:** Visuelles Whiteboard, Migration zu OSS geplant
- **Mem0:** Zentrales Memory Layer für Chats, Code-Fragmente, Entscheidungen

---

## Arbeitsstil & Standards

- Jedes neue Projekt: Projektbeschreibung als `claude.md` im Root
- Alle Compose Files, Skripte, Setups verständlich kommentiert
- Ziel: möglichst wenig Redundanz, maximal durchsuchbare, strukturierte Ablage

---

## Meta-Projekt: Datenmodellierung & Wissensstrukturierung

- **Herausforderung:** Datenfragmentierung, fehlende einheitliche Wissensstruktur, keine zentrale Entitäten-/Beziehungsabbildung systemübergreifend
- **Ziel:** Entwicklung eines homogenen, PARA-erweiterten Datenmodells über Knowledge Graph/RAG/PKM-API/Agents
- **Aufgaben:**  
  - Modellierung von Entitäten, Kategorien, Beziehungen (Projekt ↔ Datei ↔ Notiz ↔ Ressource ↔ Visualisierung)
  - Schnittstellen für Craft, Synology, Miro, Anytype, n8n schaffen
  - Entscheidungs-, Changelog- und Ressourcenverwaltung systemübergreifend konsolidieren

---

## Karriereentwicklung & Wissensaufbau

### Aktuelle Situation & Ziele

- Aktive Jobsuche, Karrierefokus: (Senior) Rollen in KI, Automatisierung, Data/IT Consulting, Analytics, MarTech, Product Ownership
- Systematischer Aufbau von KI-, RAG-, LLM-, Automatisierungs- und Prozessmanagement-Know-how (bisher unstrukturiert, wird zentralisiert)
- Ziel: Nachweisbare Qualifikation (Zertifikate, strukturierte Doku, offizielle Abschlüsse), Integration von Lernzielen/Kursen/Zertifikaten in PARA- und RAG-Projekt
- Entwicklung von Skill-Matrix, Projektportfolio, Self-Assessment und Retrospektiven

### Interessen & Stärken

- **Sport:** Ambitionierter Rennradfahrer (20+ Jahre), Gruppenleitung, Ausdauer, Teamgeist, Eisschnelllauf/Eishockey (25+ Jahre), Skifahren (Freestyle, bis Unfall), Physiotherapie & Resilienz
- **Kreativität & Problemlösung:**  
  - Coding, Home Automation, Low-Code, Prototyping  
  - Handwerk, Design, UX, strukturierte Texte/Thesis, Romanentwurf
  - Entwicklung von Lösungsstrategien, Teaching, Coaching
- **Lesen & Lernen:**  
  - Sachbücher, Research Papers, Upskilling, Kurse, Zertifikate, Konferenzen, Selbststudium
- **Musik:** Cello, breite Musikinteressen
- **Workstyle:**  
  - Organisation, Freiheit, Innovation, Teamgeist, Leadership-Potenzial, Werteorientierung, schnelle Adaption, Exploration
- **Technische Skills:**  
  - Digitale Produkte, Automatisierung, Analytics, Data Engineering, MarTech
  - Prototyping, Systemanalyse, Prozessdesign, Datenintegration, Scrum
- **Schwächen & Herausforderungen:**  
  - Wenig Übung mit schwierigen Autoritäten, noch keine ausgeprägte Leadership-Praxis, Kommunikations-/Teaching Skills ausbaufähig, fehlende Zertifikate

### Relevante Berufserfahrung (Auswahl)

- IT Transformation, Sourcing, Prozess- & IT-Kostenmanagement, Architektur, Design und Umsetzung von Analytics-/MarTech-/Data Engineering-Projekten
- Beratung, Coaching, Moderation, Requirements Engineering, Prozessdesign, User Story Mapping, Epic-Building, Agile Methoden (Scrum, PO), Vendor Management, Ausschreibungen, Sourcing
- Führung kleiner Teams, Zusammenarbeit mit Product Ownern, Entwicklern, Testern, Kunden
- Data Integration & Prozessautomation (Google Sheets, HubSpot, Low-Code, API-Workflows)
- Entwicklung von Frameworks, Doku, Best-Practices, Change Management
- Beratung von Führungskräften, Präsentation, Kundenworkshops (Deutsch & Englisch)

### Zertifizierungen & Nachweise (geplant/gewünscht)

- Ziel: Zertifikate in KI, RAG, LLMs, MarTech, Prozessmanagement, Scrum, Product Ownership (z.B. HuggingFace, Google Cloud/AI, Microsoft, Scrum Alliance, PMI, DataCamp, Udemy)
- Dokumentation von Lernfortschritten, Anwendung im Alltag, Skill Matrix, Projektportfolio, PARA-Integration

### Entwicklungsschwerpunkte für die Zukunft

- Systematisierung des Wissensaufbaus, nachhaltiger Karrierefortschritt
- Verbindung von Hands-on-Projekten mit offiziellen Qualifikationen/Nachweisen
- Ausbau Leadership-Qualitäten (Coaching, Praxis, Peer-Feedback)
- Ausbau Kommunikations-, Präsentations- und Teaching-Skills (Kurse, Praxis, Doku)
- Migration von Know-how aus Notizen & Projekten in zentralen Knowledge Graph / PARA / RAG-Struktur
- Monitoring, Reflexion (Retros, Self-Assessment, regelmäßige Anpassung Lern-/Karrierestrategie)

---

## Bekannte Schwachpunkte & TODOs

- Daten und Wissen fragmentiert (Craft, NAS, Miro, Confluence, Anytype, Karakeep)
- Miro zu teuer, Alternative gesucht
- Anytype lokal, API/MCP-Server neu, zentrale Integration an andere Apps fehlt noch
- Kein universelles Datenmodell für Wissen und Dateien (Meta-Projekt)
- Consulting- und Projektmanagement-Know-how muss systematisiert und durch intelligente Workflows/Agents gestützt werden

---

**Hinweis für Claude:**  
Beziehe dich stets auf diese Datei, besonders für Aufgaben im Kontext Wissensmanagement, Karriereentwicklung, KI/Upskilling, Datenmodellierung und Automatisierung.  
Arbeite vorausschauend, strukturiert und frage gezielt nach, wenn entscheidender Kontext (Skills, Zertifikate, Projekte, Tools, Plattformen) fehlt.  
Schlage konkrete Wege vor, wie praktische Erfahrung, Zertifikate, projektbasierte Nachweise, Reflexionen und kontinuierliche Weiterbildung sinnvoll verknüpft werden können (Skill Matrix, PARA, Projektportfolio, Self-Assessment etc.).
