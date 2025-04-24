# Unterschiede zwischen SAN und NAS

## Was ist ein SAN?

Ein **Storage Area Network (SAN)** ist ein dediziertes Hochgeschwindigkeits-Netzwerk, das Server und Speichergeräte miteinander verbindet. Es arbeitet unabhängig vom lokalen Netzwerk (LAN) und ermöglicht den Speicherzugriff auf Blockebene. Dadurch eignet sich ein SAN besonders für Anwendungen, die schnellen Datenzugriff mit geringer Latenz benötigen.

### Merkmale von SAN:

- Zugriff auf Blockebene
- Verwendet Fibre Channel oder iSCSI
- Unabhängig vom LAN
- Hohe Leistung und geringe Latenz

---

## Was ist ein NAS?

Ein **Network Attached Storage (NAS)** ist ein Dateiserver, der mit dem LAN verbunden ist und über **standardisierte Netzwerkprotokolle** wie **NFS** oder **SMB** arbeitet. Es ermöglicht den Datenzugriff **auf Dateiebene** und ist besonders für die gemeinsame Dateinutzung im Netzwerk geeignet.

### Merkmale von NAS:

- Zugriff auf Dateiebene
- Verwendet Ethernet/IP
- In das lokale Netzwerk integriert
- Einfach zu verwalten und kostengünstiger

---

## Vergleich: SAN vs. NAS

| Merkmal | SAN | NAS |
| --- | --- | --- |
| Zugriffsebene | Blockebene | Dateiebene |
| Verbindungstyp | Fibre Channel, iSCSI | Ethernet (LAN) |
| Performance | Sehr hoch | Mäßig bis hoch |
| Komplexität | Hoch | Gering |
| Typische Protokolle | FC, iSCSI | NFS, SMB/CIFS |
| Einsatzgebiet | Hochleistungs-Apps, Datenbanken | Dateifreigabe, zentrale Speicherlösung |

---

## Anwendungsfälle für SAN

SAN-Systeme werden häufig eingesetzt für:

- Hochleistungs-Computing
- Geschäftskritische Datenbanken
- Schnelle und zuverlässige Backups

---

## Anwendungsfälle für NAS

NAS-Systeme eignen sich besonders für:

- Zentrale Dateispeicherung und -freigabe
- Big Data: Speicherung großer unstrukturierter Dateien
- Active Archives: Langfristige Dateiarchivierung mit Zugriffsmöglichkeiten
