# 🚀 UNISM – Unified Server Management

UNISM ist ein Agent-basiertes Server-Management- und Monitoring-System, mit dem du eigene Server zentral verwalten, überwachen und sicher steuern kannst.

## 🎯 Fokus des MVPs

Das MVP konzentriert sich auf ein schlankes, aber sauberes technisches Fundament:

- Management-Backend (Spring Boot) mit erster Web-UI
- Sicher angebundener Agent auf einem Zielserver
- Basis-Ansicht der registrierten Server in der Oberfläche

Ziel: Einen Agent auf einem Server installieren, eine gesicherte Verbindung aufbauen und den Server im Dashboard sichtbar machen.

## 🔑 Kernfeatures (MVP)

- **Agent-Registry**: Registrierung von Servern/Agents mit Status (online/offline, letzte Aktivität).
- **Sichere Kommunikation**: gRPC mit mTLS zwischen Backend und Agent (eigene kleine CA geplant).
- **Server-Übersicht**: Einfache Web-UI mit Liste aller bekannten Agents/Server und Basis-Infos.

Spätere Ausbaustufen (nach dem MVP geplant):

- Task-/Command-Ausführung (z.B. Services neu starten, Updates anstoßen)
- Erweiterte Monitoring-Metriken (CPU/RAM/Disk, ggf. Integration in Prometheus/Grafana)
- Rollen- und Rechtemodell (RBAC) für mehrere Nutzer

## 🛠 Tech Stack

- **Backend**: Java, Spring Boot, gRPC
- **Agent**: Python (leichtgewichtiger Dienst auf dem Zielserver)
- **Kommunikation**: Protocol Buffers / gRPC, mTLS
- **Datenbank**: PostgreSQL (für Agents, Tasks, Audit-Logs – geplant)
- **Web-UI**: Spring Boot + Thymeleaf (MVP), später ggf. SPA/PWA

## ⚡ Quick Start (MVP – Work in Progress)

> Achtung: Das Projekt befindet sich im frühen Aufbau. Die folgenden Schritte werden erweitert, sobald die ersten Komponenten stehen.

### Backend lokal starten

```bash
git clone https://github.com/Aridex339/UNISM.git
cd UNISM/sm-backend

# Build & Run (Beispiel)
./mvnw spring-boot:run
```
Standardmäßig ist das Backend dann unter http://localhost:8080 erreichbar (Port kann sich später noch ändern).

### Agent auf einem Testserver starten

```bash
git clone https://github.com/Aridex339/UNISM.git
cd UNISM/sm-agent

# Python-Umgebung und Abhängigkeiten installieren (Platzhalter)
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Agent (noch Dummy) starten
python agent_main.py
```

Sobald die erste gRPC-Verbindung implementiert ist, sollte der Agent im Backend unter „Agents“ sichtbar werden.

### 🗺 Roadmap
- [x] Repository-Grundstruktur & Issue Templates

- [ ] README & Contributing Guidelines finalisieren

- [ ] Shared .proto-Definition für Backend/Agent

- [ ] gRPC-Backend mit mTLS (Skeleton)

- [ ] Minimaler Python-Agent (Registration + Heartbeat)

- [ ] Einfache Web-UI für Agent-Liste

- [ ] Erste Beta-Tests auf Heim-Testservern

### 🤝Rules

Details findest du in der CONTRIBUTING.md.
