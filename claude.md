# Developer Profile & Homelab Base Context (claude.md)

## Über mich

- IT-Consultant mit Fokus auf Data Strategy, Analytics, DevOps, Process Mining und Low-Code Automation.
- Erfahrung als Scrum Master, Product Owner, Technical Consultant.
- Private Infrastruktur mit Schwerpunkt auf Selbst-Hosting, Automatisierung und Privacy.

## Persönliche Arbeitsweise & Präferenzen

- Bevorzuge strukturierte, dokumentierte Workflows (Markdown als Standard für Doku und Protokolle).
- Setze stark auf Automatisierung (n8n, Node-RED, Home Assistant).
- Wert lege ich auf Wiederverwendbarkeit, klare Modularisierung und offene Schnittstellen (API-first).
- Docker als Standard für Deployments, bevorzugt Compose-Setup.
- Container laufen bevorzugt auf Synology NAS oder Oracle VPS, gelegentlich auch auf dem MacBook.
- Lokale Entwicklung überwiegend auf MacBook Pro M1 Max.
- In Projekten: Fokus auf verständliche Code-Dokumentation, nachvollziehbare Architekturentscheidungen, Testing (pytest/Playwright), Linting.
- Zwei Oracle VPS sind im Einsatz: Standort Amsterdam und Zürich. Züricher Maschine ist mit Coolify, Amsterdam mit CapRover konfiguriert.
- Meine persönliche Webseite certain.cc liegt auf dem VPS Amsterdam, parallel zur persönlichen Webseite meiner Partnerin (parr.cc), die ich entwickle und verwalte
- Das Domain Management liegt komplett bei Cloudflare. Alle DNS Settings werden selbst konfiguriert.
- Wichtige Tools: VSCode, Cursor, Terminal, GitHub, Docker Desktop, Portainer, Tailscale, Miro, Witsy, zed, claude, gemini cli.

## Infrastruktur & Technologien

### Synology NAS

- Modell: DS-723+ (plus ggf. weitere Geräte)
- Speicher: Hybrid-Setup, Fokus auf SSD/NVMe, optimiert auf geringe Lautstärke und Stromverbrauch.
- Docker Engine läuft als Hauptplattform für Self-Hosting.
- Wichtige Verzeichnisse:  
    - `/volume1/docker/<applikation>/` für alle persistente Daten
- Verwaltung:  
    - Docker Compose (keine Version-Keys mehr, aktuelle Syntax),  
    - Portainer als UI für Container-Management,
    - Reverse Proxy: Synology-Proxy.
- Datensicherung: Automatisierte Backups auf Backblaze, Monitoring über Uptime Kuma.
- Netzwerkanbindung: Tailscale (inkl. ACLs für feingranulare Freigaben), gelegentlich Headscale, Cloudflare für DDNS, Wildcard-SSL via ACME.
- Internetleitung: 50 up, 50 down, DSL bei Vodafone.
- 2,5 Gbit Switch am Fritzbox Router 6660, als WLAN Router kommen eero und eero pro zum einsatz. Das NAS hat einen 10 Gbit LAN Anschluss, den ich nutze.


### Homelab/Cloud

- VPS (Oracle Cloud, Ubuntu) für ausgelagerte Dienste wie Karakeep (Bookmarking), BudiBase und weitere.
- n8n als zentrale Automatisierungsplattform (Workflows: PDF-Reparatur, API-Orchestration, Notification Services).
- Vector DBs: Qdrant (NAS), Neo4j (geplanter test), Supabase für Vektor-Projekte, remote gehostet von Supabase selbst verfügbar.
- LLM-Hosting: Ollama, Open WebUI (bisher ohne konkreten Use-Case idle), Paperless-AI, Paperless-NGX für Dokumentenmanagement. 
- RAG-Projekte in der Entwicklung (Retrieval-Augmented Generation): Lokale Embedding-Pipeline geplant, Qdrant und/oder Supabase als Storage, LlamaIndex/LangChain ggf. für Prototyping.
- Homeassistant läuft auf der eigenen Hardware Homeassistant Yellow. Integration mit Apple Home und Zigbee/Thread.
- Ein Raspberry Pi steht mir für Bastelprojekte noch zur Verfügung.
- Weitere Docker Container im Einsatz: actual (budgeting), calcom (appointments), docuseal (pdf signierung), flowise (AI Agent workflows - bisher nicht aktiv genutzt), github-runner, kestra (bisher mangels use-case nicht genutzt), mealie (rezepte), n8n (orchestrierung, APIs, MCPs), open webui (bisher kein use-case in betrieb), wallos (finance: abo management), watchtower, wud, paperless-ngx, paperless-ai, paperless-gpt, affine (bisher nicht inbenutzung)
  
### Networking & Security

- Netzwerkstruktur:  
    - Fritzbox als Hardware-Firewall,
    - interne Firewall auf NAS (GeoIP-Blocking, Portfilter),
    - Tailscale ACLs und Zugangsbeschränkungen,
    - Reverse Proxies auf Domainbasis, TLS per ACME.
- Remote Access: Nur über Tailscale oder VPN (kein direkter Expose von Apps). Das NAS als auch beide VPS und alle mobilen Geräte sind über Tailscale nodes erschlossen und im MEsh verfügbar. Die VPS sind für Traffic über Port 443 und 80 erreichbar, das NAS nicht. Die SSH Ports sind überall dicht. SSH wird nur über die Tailscale-eigene Lösung betrieben.
- Monitoring: Uptime Kuma, Dozzle für Log-Überwachung, Watchtower für Container-Updates.

## Dokumentation & Entscheidungsfindung

- Projekte, Setup-Anleitungen, Changelogs und Entscheidungslogs liegen als Markdown auf dem NAS (z.B. `/volume1/docs/`) aber leider auch verteilt auf einer atlassian confluence instanz (nicht mehr gepflegt) und ganz viel lokal in meiner produktivitäts App craft.do auf dem macbook bzw. synchronisiert mit der craft Cloud.
- Jedes Projekt hat ein eigenes Subverzeichnis mit README und decision-log.
- Technische Notizen zu NAS-Konfiguration, Reverse Proxy, Zertifikaten, Container-Architektur, etc. finden sich in `/volume1/docs/homelab/` oder leider verteilt in craft notes. Deshalb wird dringend ein RAG projekt benötigt.
- Ich versuche das PARA System für globale context Standardisierung über mehrere Apps zu nutzen. Einheitlich benannte "Areas" erleichtern mir die Orientierung.

## Arbeitsstil & Standards

- Neue Projekte starten mit einer ausführlichen Projektbeschreibung als `claude.md` im Root-Verzeichnis.
- Alle Konfigurationen, Shell-Skripte und Docker Compose Files sind verständlich kommentiert.
- Einheitliche Volumestruktur für alle Container (`/volume1/docker/<app>`).
- Keine unnötige Komplexität – bevorzugt lokale-first-Lösungen, SaaS nur wenn unumgänglich. Kosteneffizienz steht im Vordergrund.
- Bevorzugt Open Source Tools und Self-Hosting, Datenhaltung möglichst auf dem NAS oder Hybrid auf eigenem VPS innerhalb der EU.

## Bekannte Schwachpunkte & TODOs

- Die Reverse-Proxy-Konfiguration auf Synology ist stark eingeschränkt – drum lagere ich manche Applikationen auf meinen VPS aus.
- Qdrant UI ist verbesserungswürdig, deshalb Wechsel auf Supabase. Die lokale Inbetriebnahme des Supabase Stacks war zu aufwendig, langfristige Stabilität steht im Vordergrund und ist enorm wichtig.
- Dokumentation zu Automations- und Notification-Workflows wird laufend aktualisiert.
- Bisher keinerlei Erfahrung mit RAG Technologie. Stringenter Aufbau meines Know-how gewünscht, mit dem Ziel, einen eigenen Knowledge Graphen zu betreiben. Falls zu komplex, greife ich auf eine Hybride Lösung zurück und binde ein externes RAG an, sofern nicht zu teuer. Die Pragmatik und Nutzbarkeit des Systems steht im Vordergrund.
- Die Entwicklung eigener Pipelines, AI Agents als persönliche Helfer und Assistenten ist mein Ziel.
- Anytype möchte ich als primäres PKM Tool im Alltag einsetzen und intelligent in meinen Techstack einbinden. Die Verwaltung meines Wissens derzeit in Craft notes ist trotz aller Struktur sehr chaotisch. Die Informatione müssen viel besser verknüpft sein.

---

## [Optional] Häufig genutzte Projekte & Pfade

- Paperless-NGX: `/volume1/docker/paperlessngx/`
- Open WebUI: `/volume1/docker/openwebui/`
- Home Assistant: `/volume1/docker/homeassistant/`
- n8n: `/volume1/docker/n8n/`
- Qdrant: `/volume1/docker/qdrant/`
- Anytype Self-Hosting: `/volume1/docker/anytype/`

---

**Hinweis für Claude:**  
Wenn Fragen zu Infrastruktur, Netzwerk, Container, Automation oder Datenstruktur auftreten, beziehe dich auf diesen Grundkontext. Bei Detailfragen zu Projekten bitte gezielt die Projekt-spezifische `claude.md` abfragen oder weitere Details anfordern.
