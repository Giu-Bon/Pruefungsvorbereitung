
# Zertifikate und X.509

## Was ist ein digitales Zertifikat?

Ein **digitales Zertifikat** bestätigt kryptografisch die Identität eines Kommunikationspartners, z. B. einer Website oder einer Organisation. Es enthält den **öffentlichen Schlüssel** und Identitätsinformationen und wird von einer **Zertifizierungsstelle (Certificate Authority, CA)** signiert.

### Verwendungszwecke:

- Absicherung von HTTPS-Verbindungen (SSL/TLS)
- Digitale Signaturen (z. B. bei E-Mails oder Software)
- Authentifizierung von Benutzern oder Geräten

---

## Was ist X.509?

**X.509** ist ein Standard für den Aufbau digitaler Zertifikate. Er wird z. B. im TLS-Protokoll für HTTPS verwendet. Die aktuelle Version ist **X.509 v3**, welche Erweiterungen (Extensions) erlaubt.

---

## Aufbau eines X.509-Zertifikats

Ein X.509-Zertifikat besteht aus mehreren Feldern:

| Feld | Beschreibung |
|------|--------------|
| Version | Version des Zertifikats (meist v3) |
| Serial Number | Eindeutige Nummer zur Identifikation |
| Signature Algorithm | Algorithmus, mit dem das Zertifikat signiert wurde |
| Issuer | Herausgeber des Zertifikats (CA) |
| Validity | Gültigkeitszeitraum (Not Before / Not After) |
| Subject | Inhaber des Zertifikats (z. B. Domainname) |
| Subject Public Key Info | Öffentlicher Schlüssel des Inhabers |
| Extensions | Zusätzliche Informationen (z. B. SAN, Key Usage) |
| Signature | Digitale Signatur der CA |

---

## Wichtige Begriffe

- **CA (Certificate Authority)**: Vertrauenswürdige Stelle, die Zertifikate ausstellt.
- **Root-Zertifikat**: Selbstsigniertes Zertifikat einer CA, als Vertrauensanker im System.
- **Intermediate-Zertifikat**: Verlinkt Root-Zertifikate mit Endnutzer-Zertifikaten.
- **Chain of Trust**: Zertifikatskette von Root über Intermediate bis zum Server-Zertifikat.

---

## Zertifikatprüfung (z. B. im Browser)

1. Gültigkeit des Zertifikatszeitraums
2. Übereinstimmung von Domainname und Subject (bzw. SAN)
3. Signaturprüfung anhand der CA
4. Vertrauen in die CA (Root muss im System hinterlegt sein)

---

## Typische Zertifikatsformate

| Format | Dateiendung | Beschreibung |
|--------|-------------|---------------|
| PEM | `.crt`, `.pem` | Base64-kodiert mit Headern |
| DER | `.der`, `.cer` | Binärformat, z. B. für Windows |
| PKCS#12 | `.p12`, `.pfx` | Containerformat mit Zertifikat und privatem Schlüssel |
