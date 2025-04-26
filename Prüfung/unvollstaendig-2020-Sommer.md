# Abschlussprüfung Sommer 2020
>1197  
>Fachinformatiker/Fachinformatikerin  
>Systemintegration  
>Termin: Mittwoch, 29. April 2020  


Die Handlunosschritte 1 bis 5 beziehen sich auf die folqende Ausqanqssituation:

Die BaulVit AG ist eine übenegionale Baumarktkette.
Die BaulVlit AG arbeitet im WAN-Bereich mit dem Internet-Provider vNet GmbH zusammen.
Beleiligte Unternehmen und Personen:
Die BauMit AG, die vNet GmbH und Lieferanten der BauMit AG.
Auftraggeber
Die Geschäftsführung der Baul\ilit AG beauftragt die lT-Abteilung, sich aui anstehende Erweiterungen durch Gründung weiterer
Baumärkte vorzubereiten.  
Im Rahmen dieses Projektes sollen Sie vier der folgenden fünf Aufgaben erledigen:  
1. Netzwerkstruktur in der Zentrale analysieren, Einführung von lPv6 planen, Internetzugang
2. Standorte vernetzen, Firewall auswählen und einrichten, WLAN in den Baumärkten einrichten
3. Desktop und Server Virtualisierung, Verfügbarkeit der Dienste sicherste len
4. Ein Skript zum Versand von E-Mails bearbeiten
5. Befehlszeilenkommandos und GUI zur Systemverwaltung, Benutzerverwaltung

## 1. Handlunosschritt (25 Punkte)
Das Netzwerk der BauMit AG (siehe perforierte Anlage) besteht aus einer Zentrale in Frankfurt und einer Zweigniederlassung Köln.  

### a) Sie überprüfen die Funktionsfähigkeit der Kommunikation im Netzwerk.

### aa) Zunächst überprüfen Sie die lP-Konflguration des Domänencontrollers in der Zentrale mit ipconflg /all :  

Verbindungsspezifisches DNS-Suffix  : baumit.ads  
IPv4-Adresse                        : 10.0.3.200  
Subnetzmaske                        : 255.255.252.0  
Standardgateway                     : 200.0.0.2  
DNS-Server                          : 85.100.200.17  

Erläutern Sie, welcher Fehler vorliegt und wie Sie diesen Fehler beseitigen. (3 Punkte)

\______________________________________________________________________________

\______________________________________________________________________________

\______________________________________________________________________________

  
___  
### ab) Auch am Client 1 in der Zentrale überprüfen Sie die lP-Konfiguration mit ipconfig /all:

Verbindungsspezifisches DNS-Suffix  : baumit.ads  
IPv4-Adresse                        : 10.0.0.1  
Subnetzmaske                        : 255.255.252.0  
Standardgateway                     : 10.0.3.200  
DNS-Server                          : 10.0.3.254  

Erläutern Sie, welcher Fehler hier vorliegt und wie Sie diesen Fehler beseitigen. (3 Punkte)  

___ 

### Dieses Blatt kann an der Perforation aus dem Aufgabensatz herausgetrennt werden!
**Siehe Netzwerk-BauMitAG.png**

___

### ac) Zum Abschluss lhrer Kontrollen überprLifen Sie die IP-Konfiguration des Mailservers in der DMZ:    

Verbindungsspezifisches DNS-Suffix  : baumit.ads  
IPv4-Adresse                        : 192.168.99.1  
Subnetzmaske                        : 255.255.255.248  
Standardgateway                     : 192.168.99.7  
DNS-Server                          : 10.0.3.200  

Erläutern Sie, warum der Mailserver nicht mit anderen Hosts kommunizieren kann und wie Sie diesen Fehler beseitigen. (3 Punkte)

___

### b) Nach der Beseitigung der Fehler überprüfen Sie mit dem Befehl ping 192..l68.10.254 die Funktionsfähigkeit des Routings. Da der Ping fehlschlägt, lassen Sie sich die Routingtabelle des Routers in der Zentrale anzeigen:  
**Siehe RoutingTabelle-A1-b1.png**

Erläutern Sie, welcher Fehler vorliegt und wie Sie diesen Fehler beseitigen.  (4 Punkte)

___


### c) Die Administratoren haben am DNS des Domänencontrollers eine Weiterleitung auf den DNS-Server 85.100.200.17 eingerichtet.   
Eläutern Sie, warum diese Weiterleitung eingerichtet werden muss. (4 Punkte)

___


### d) Die Administratoren der BauMit AG bereiten die Umstellung des Netzwerkes auf IPv6 vor.   
Vom Provider haben sie das IPv6-Netz 2a02:ac20:e0:a000::/56 erhalten.   Das Netz soll in vier gleich groBe Subnetze unterteilt werden.  


### da) Ermitteln Sie den IPv6-Prefix frir die Subnetze. Der Rechenweg ist anzugeben.  (2 Punkte)

___ 


### db) Ermitteln sie die jeweilige Netz-ID der Subnetze und tragen Sie diese in die Tabelle ein

| Subnetz      | Netz-ID                               |
| ------------ |-------------------------------------- |
| 1   | 2a02:ac20:e0:a000::  | 
| 2   |                      | 
| 3   |                      | 
| 4   |                      | 

___


## 2. Handlungsschritt (25 Punkte)
Die BauMit AG plant, ihre Standone mit einheitlicher Infrastruktur zu vernetzen. Alle Baumärkte sollen mit identischer Netzwerk-Hardware ausgestattet werden.


### a) Jeder Standort soll mit einer Leitung frir Daten- und Telefondienste angebunden werden. Der lnternetprovider bietet lhnen hier für zwei Lösungen an: 
Eine Standleitung mittels transparenter Layer 2 Ethernet-Verbindung 
oder alternativ eine DSL Leitung.

Beschreiben Sie stichpunktartig drei Vorteile einer Standleitung gegenüber einer DSL Leitung. (6 Punkte)


___

ahhh sorry i can't do it... Wenn ich alles aptippen würde dann kann ich nicht mehr lernen sorry. 

