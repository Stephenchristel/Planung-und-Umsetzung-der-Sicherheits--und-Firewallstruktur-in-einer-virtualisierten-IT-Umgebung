# Planung-und-Umsetzung-der-Sicherheits--und-Firewallstruktur-in-einer-virtualisierten-IT-Umgebung
Die IT-Sicherheit zählt zu den kritischsten Herausforderungen moderner Unternehmen. Statistiken zeigen, dass ein Großteil aller Betriebe bereits von Cyberangriffen betroffen war. Vor diesem Hintergrund ist dieses Projekt von zentraler Bedeutung: Es demonstriert praxisnah, wie Sicherheitsarchitekturen in modernen IT-Infrastrukturen konzipiert .

## Schritt 1: Bereitstellung der pfSense-Firewall und Netzwerksegmentierung
Nach der erfolgreichen Installation und Inbetriebnahme der pfSense-Firewall habe ich die einzelnen Netzwerke strikt voneinander isoliert. Diese Segmentierung ist eine essenzielle Sicherheitsmaßnahme: Sie dient der Schadensbegrenzung bei potenziellen Cyberangriffen, reduziert die Angriffsfläche der Systeme minimiert und ermöglicht eine deutlich bessere Übersicht sowie Kontrolle über den gesamten Netzwerkverkehr.
<img width="1061" height="810" alt="Screenshot 2026-06-26 214124" src="https://github.com/user-attachments/assets/5ca4943f-1f33-466d-9f0f-c2f6caaf37b2" />
<img width="1414" height="738" alt="Screenshot 2026-06-27 160145" src="https://github.com/user-attachments/assets/f7a78983-4331-4bd5-87e9-10add3d629bf" />

## Schritt 2: Schnittstellen-Zuweisung und IP-Adresskonfiguration
In diesem Schritt erfolgt die korrekte Zuordnung der virtuellen Netzwerkkarten (Interfaces) innerhalb von pfSense sowie die Anpassung der IP-Adressbereiche. Diese Konfiguration stellt sicher, dass alle Endgeräte im Netzwerk ihre Anfragen (Requests) korrekt an das zuständige Standard-Gateway adressieren können. Zudem wird der Firewall signalisiert, welche physische bzw. virtuelle Schnittstelle welchem Netzwerksegment zugeordnet ist. Eine saubere Strukturierung an dieser Stelle bildet das Fundament für ein effizientes Netzwerkdesign und erleichtert spätere administrative Aufgaben wie das Troubleshooting oder die Abwehr von Cyberangriffen.
<img width="1139" height="629" alt="Screenshot 2026-06-27 163723" src="https://github.com/user-attachments/assets/04f02a28-0d84-423a-9021-4d8081842acd" />
<img width="1158" height="693" alt="Screenshot 2026-06-27 164203" src="https://github.com/user-attachments/assets/77f4d582-241b-4f27-adfa-483b9c9f54c6" />

## Schritt 3: Konfiguration des Firewall-Regelwerks (Firewall Rules)
Da die pfSense-Firewall im Auslieferungszustand jeglichen Datenverkehr blockiert (Default-Deny-Prinzip), ist die Konfiguration dedizierter Firewall-Regeln erforderlich. Um diese Regeln zu erstellen, erfolgt der Zugriff auf die grafische Web-Oberfläche (WebGUI) der pfSense. Aus Sicherheitsgründen wird dieser administrative Zugriff isoliert über den Linux-Client durchgeführt. Dieser Schritt ist von zentraler Bedeutung: Das Regelwerk definiert nicht nur die erlaubten Kommunikationswege zwischen dem internen Netzwerk und externen Netzen (wie dem Internet), sondern ermöglicht durch die Protokollierung unerlaubter Zugriffe auch eine schnelle Reaktion auf unbefugte Angriffsversuche.
<img width="1262" height="740" alt="Screenshot 2026-06-27 183913" src="https://github.com/user-attachments/assets/f08699f3-2fab-4458-80bc-517097fab593" />
<img width="1256" height="750" alt="Screenshot 2026-06-27 194340" src="https://github.com/user-attachments/assets/b6045013-a776-4069-86d5-56ccefd6e49f" />

## Schritt 4: Netzwerkintegration des Windows Servers und Installation des Active Directory (AD DS)
In diesem Schritt wurde der Windows Server in das Netzwerk integriert und mit einer statischen (festen) IP-Adresse konfiguriert. Diese statische IP-Vergabe ist zwingend erforderlich, um eine dauerhafte Erreichbarkeit des Servers zu gewährleisten und spätere Konflikte bei der Verwaltung der IP-Adressbereiche im Server-Segment zu verhindern. Anschließend erfolgte die Installation der Active Directory Domänendienste (AD DS). Das Active Directory bildet das Herzstück der Infrastruktur und fungiert als zentrale Administrations- und Authentifizierungsinstanz (Domänencontroller), die alle Benutzer, Gruppen und Computer im gesamten Netzwerk maßgeblich steuert und strukturiert.
<img width="997" height="610" alt="Screenshot 2026-06-27 200856" src="https://github.com/user-attachments/assets/9350ef9e-93db-4611-914c-6c5449a3957f" />
<img width="1023" height="767" alt="Screenshot 2026-06-27 201950" src="https://github.com/user-attachments/assets/45499832-9c2e-4c76-a3b5-a362606aee6c" />

## 
