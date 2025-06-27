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
- LaTeX für strukturierte, professionelle Dokumentenerstellung (Overleaf, LyX, MacTex)
- Mac Whisper Transcription

## Tool- und Datenlandschaft

### Speicherorte & Fragmentierung (Stand 2025-06)

- **Craft Notes** (ca. 70% meines Wissens)  
  - Haupt-Notiz- und Wissensspeicher.  
  - Enthält: Meeting-Notes, Consulting-Know-how, Projekte, Methoden, Entwürfe, Protokolle, Entscheidungslogs.
  - PARA-Struktur als Ordnungsrahmen, aber aufgrund des Dokumentenansatzes oft fragmentiert.
  - Muss eigentlich durch AnyType oä. ersetzt, der Content weitgehend migriert werden. Bin etwas ratlos, wie ich mit dem Informationsüberschuss und dessen strukturierter Organisation am besten umgehe.

- **Synology Drive/NAS** (ca. 20% der Wissensinhalte, 80-90% aller Projektdaten und Ressourcen)  
  - Hauptspeicher für: Dateien, Projektunterlagen, Code, Ressourcen, Automations-Workflows, Doku, Backups.  
  - Struktur: Einheitliche Volumestruktur unter `/volume1/docker/<app>/` und `/volume1/docs/`
  - Zentrale Dateiablage, teilweise auch als Sync-Quelle für andere Tools genutzt.

- **Dropbox & Gdrive**
  - Dropbox auf dem System aber nicht aktiv (habe alles zu Synology lokal migriert)
  - Gdrive auf dem System aber nur für experimentelle Workflows aus N8N heraus im Einsatz, sonst ungenutzt.

- **Miro** (ca. 10% des Wissens, meist Visualisierungen & Prototypen)  
  - Verwendung: Visuelle Projektplanung, Mindmaps, schnelle Konzepte, Workshops.
  - Problem: Proprietär, sehr teuer, langfristig abzulösen. Bedarf: Mächtiges Board-Tool für Prototyping, Brainstorming, Visualisierung, aber lokal/self-hosted oder günstiger.
  - Ziel: Migration auf eine alternative Whiteboard/Diagramm-Lösung (offen, vernetzt, API-zugänglich).

- **Atlassian Confluence** (historisch, ca. 5%)  
  - Veraltete Dokumentationen, Alt-Projekte, kaum gepflegt --> muss zu Anytype migriert werden!

- **Anytype** (Test, ca. 1%)  
  - PKM-Lösung, lokale App auf Mac (nicht auf NAS!), Ziel: künftige Integration als Memory Layer, Knowledge Graph, API-Zugriff über MCP/SSE-Proxy in Vorbereitung.

- **Lokaler Speicherort auf dem Mac für Entwicklungsprojekte**
  - /Users/jc/Documents/Development/
  - Sub-Verzeichnisse:
    - ./mcp-servers/<name_mcp_server>
    - ./Github/<Github-projekt> --> Github repositories
    - ./Gitlab/<Gitlab-Projekt> --> Gitlab repositories (aktuell ungenutzt)
    - ./Projekt1/<subfolder>/<datei> --> sonstige Dev Projekte, müssen noch in Github migriert werden
    - ./Projekt2/<subfolder>/<datei>
    - ./etc.

### Weiteres

- **Cloud Plattformen, Hybride oder SaaS im Einsatz**
  - Adguard-DNS, NextDNS
  - Fabric.so
  - Tailscale
  - 1Password
  - docker Hub
  - Craft Notes
  - Google Workspace
  - Github
  - Miro

- **Projektdaten und Ressourcen:**  
  - Liegen primär auf Synology NAS.
  - Wissen/Beschreibung dazu in Craft Notes, Überblick/Struktur oft in Miro.

- **KI/LLM-Tools:**  
  - Ollama (Mac, Testbetrieb), OpenAI, Gemini, Claude, OpenRouter für LLMs/Agents.
  - Bisher keine produktiv eingesetzte lokale LLM-Instanz (Performance ungenügend). Testweise verschiedene Modelle über GPT4All, Msty App und AnythingLLM geladen und für Experimente genutzt. 
  - LLM Chat Clients: Bisher hauptsächlich ChatGPT, inzwischen verstärkt Claude, vereinzelt Perplexity und testweise Witsy, 5ire, msty app, CherryStudio, NextChat.
  - Teste weiterhin verschiedene LLM Chat Clients mit MCP Anbindung auf MacOS, iOS für optimalen cross-plattform Betrieb.
  - Primäre LLM Modelle & Anbieter: Google, OpenAI, Anthropic, Huggingface

- **MCP Server:**
  - Kämpfe mit dem aktuellen Marktzustand, dass MCP Server noch für die experimentelle Ausführung auf lokalen Maschinen über das STDIO Protokoll gebaut sind. Versuche sie alle lokal auf Docker oder noch besser auf meinem NAS via Docker zu hosten und via SSE Protokoll anzusprechen, sofern sie das unterstützen
  - leider noch chaotischer Zustand: noch keine zentrale Stelle für Bereitstellung/ Betrieb von MCP Servern in meinem Stack: Einbindung erfolgt im Moment noch in jedem Client einzeln (Windsurf, Witsy, Zed, Cursor, Claude, VS Code, Goose), in Docker lokal, Docker auf dem NAS oder vereinzelt über remote Services wie Composio, Zapier, Glama, pipedream oä.
  - Experimentiere derzeit mit verschiedenen Einbindungsmethoden, versuche einen remote Proxy auf Synology als Dockercontainer aufzubauen

- **Code-Assistants und IDEs**
  - Habe mich noch nicht für einen Code-Assistant entschieden, teste derzeit folgende: zed, cursor, windsurf, vs Code und VS-Code Extensions wie Roo-Code, Cline, Continue
 
- **Browser**
  - Brave (Lieblingsbrowser)
  - Chrome (Ausweichroute, kaum genutzt)
  - Firefox (Ausweichroute für Debugging, etc.)
  - Safari (KOntextabhängig für Einzelfälle)
- **Weitere produktivitäts-Apps Lokal auf dem Mac**
  - 1Password (Enthält sauber gepflegt alle Keys, Passwörter, etc.), inkl. Browser Plugins in allen Browsern
  - Adguard DNS für die Steuerung meines bezahlten Adguard-DNS Werbefilters. Bisher mein Haupt Werbefilter. Alle Client Geräte waren angebunden aber die Server fielen immer wieder aus, drum migriere ich aktuell zu NextDNS. Bisher erscheint das stabiler aber in der Bedienung des Backends ist es schlechter gelöst als Adguard-DNS. 
  - Adobe Stack: Illustrator, Photoshop, Indesign
  - Anki Cards
  - App Flowy (Bisher nicht genutzt, muss mich noch damit auseinander setzen und entscheiden, ob ich es nutzen möchte)
  - Bitwarden (bisher ungenutzt, sollte ursprünglich als kostenloser Ersatz für 1Password herhalten, um Kosten zu sparen. Noch sehe ich von einer Migration ab. Eine selbst gehostete Vaultwarden Instanz stünde auf meinem Oracle VPS in Zürich bereit, alternativ habe ich einen Account auf der gehosteten Bitwarden Lösung, falls mir Stabilität für so sensible Dinge doch lieber ist)
  - CleanMyMac für lokale Bereinigungsaufgaben
  - Discord für vereinzeltes Kommunizieren mit Entwickler- oder App Kanälen
  - Fabric.so (bezahlte Dropbox Alternative mit einer art RAG im Hintergrund. Eine Kreuzung aus Bookmarking Dienst und Dropbox Pendent mit AI Features). Stabiler, schicker Service. Ich bin mir noch unsicher, ob ich ihn weiterhin nutze. Sobald ich einen eigenen, zuverlässigen Stack habe, baue ich das wieder ab. Denn: ich möchte meine Daten lokal auf dem NAS wissen, habe extra alle Daten von Dropbox und Gdrive zu Synology Drive migriert und nutze das ausschließlich als Datengrab und Ablage.
  - Homeassistant (täglich zur Steuerung meines Smarthomes im Einsatz)
  - Apple Home (ebenfalls täglich zur Steuerung einzelner Kernelemente meines Smarthomes im Einsatz
  - Apple Ökosystem: AppleTV, HomePods, Macbooks, iPhones, iCloud, Apple Health (intensiv genutzt) etc.
  - Kalender: Apple Kalender (Primär), Google Kalender als Ausweichroute eingebunden. Ich überlege mir so langsam von Apple Contacts und Kalender auf Google Contacts und Kalender zu migrieren. Das Apple Ölosystem ist hinsichtlich Automatisierung schlicht zu restriktiv. Ich komme von Außen schlecht oder gar nicht an Apple Kalender dran. Sehr ärgerlich in Bezug auf Einbindung in künftige RAG Szenarien.
  - Kontakte in Apple Contacts: mehr schlecht als recht gepflegt, würde mir nahtlose integration in CRM, Automatisierung und RAG wünschen, zur Produktivitätssteigerung in Bezug auf Kundendaten
  - LittleSnitch
  - Kindle Previewer
  - Spark (Mail Client). Ich nutze den Apple Mail Client nicht.
  - Microsoft Stack: Word, Excel, Teams, Powerpoint (ich hasse Microsoft, nutze es nur im geschäftlichen Kontext, wenn ich muss, nutze Apple Keynote, Numbers und Pages, wenn es klassisches office handling sein soll)
  - Apple Music, Spotify als Ausweichroute
  - PDF Bearbeitung: PDF Expert, Apple Vorschau, Foxit PDF Reader (Für eSignaturen)
  - API Testing: Postman, Proxyman, Charles
  - Screenshots: Shottr (ist ok, suche naber noch was besseres)
  - Apple Sprachmemos
  - Synology Drive Client (Für Filesync zum NAS) - Wichtigstes Asset zur File Synchronisation und Ablage
  - Text Editoren: Bear (experimentell als Craft ersatz im Test), Sublime Text (bisher für Code-Snippets genutzt, soll aber durch einen Coding Assistant vollständig ersetzt werden und vom System fliegen)
  - Transmit (FTP Client)
  - VLC Media Player
  - VmWare Fusion für vereinzelten Einsatz von Windows Spielen
  - XLD für Audio Konvertierung
  - Zotero für Bibliographie Management bei Wissenschaftlichen Arbeiten
  - Wiso Steuer
  - Zwift (indoor cycling)
  - Docker für lokale Experimente, das bauen von Images und experimentellem Betrieb von MCP Servern
  - Chat Clients: Whatsapp Primär, Discord für Entwickler Gemeinde, Threema für Familie, Telegram für Notification meines Techstacks
  - Website Development Editor: WYSIWYG Blocs Editor (Mangels tieferem Frontend Dev KNow-how weiche ich notgedrungen solche Lösungen aus, bin aber nur halb glücklich damit weil mir Anbindungen an Github und allerlei Flexibilität fehlt). Wordpress hatte ich jahrelang hinter meiner persönlichen Webseite, habe es abgeschafft. Die Pflege, Angriffsfläche und Wartung kosteten zuviel Zeit. Die Entwicklung von Templates war mir zu komplex. In Elementor hatte ich mich nie tiefer eingearbeitet, war mir zu lästig. Inzwischen läuft meine Seite statisch, Entwickelt mit Blocs. Dynamische Inhalte muss ich jetzt schrittweise nachrüsten, falls nötig.

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

### Mem0
- Vektorisiertes, zentrales Memory Layer für alle Chats und Code-Fragmente, Refactoring Entscheidungen

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
