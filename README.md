# PVist
Photovoltaik ist-Werte anzeigen für S10 PV-Anlagen der Firma E3DC.
Optional mit einer go-e Wallbox und PV-Überschussladen.

PVist ist

- eine portable Anwendung für Windows 10 & 11 und macOS, die ohne die Notwendigkeit eines dedizierten Servers auskommt.
- ein nicht-kommerzielles Freizeitprojekt, Einsatz auf eigene Gefahr

## Voraussetzungen für den Betrieb

- Windows 10, 11 oder aktuelles macOS, Intel oder Apple Silicon CPU
- der Modbus der S10 muss aktiviert sein:
  Hauptmenü -> Smart-Funktionen-> Smart Home 2x aktivieren
  Eintrag muss grün unterlegt sein, Port 502 wie voreingestellt verwenden

- die IP-Adresse oder Netzwerkname der S10 muss bekannt sein, Beispiele:
	Netzwerkname: http://S10.fritz.box oder
	IP-Adresse: http://192.168.2.1

	Zu finden im Netzwerk-Router (FritzBox etc) oder im S10 Hauptmenü -> System -> Netzwerk- > System-IP
	
- falls eine go-e Wallbox eingebunden werden soll:<br />
	- die IP-Adresse oder Netzwerkname der Wallbox muss bekannt sein.<br />
Beispiele:<br />
	Netzwerkname:<br />http://go-echarger-123456.fritz.box oder<br />
	IP-Adresse: http://192.168.2.1
	- Ggf. das API V2 der WB in der go-e Handy-App freischalten:
	“Internet” -> “Erweiterte Einstellungen” -> “Lokale HTTP API v2 erlauben”
	
	- wenn zusätzlich das PV-Überschussladen verwendet werden soll:<br />
	WB-Firmware 55.5 oder später in der go-e Handy-App unter “Internet” -> “Firmwareversion”

## Installation
Passende Datei herunter laden & in ein beliebiges Verzeichnis entpacken
- Windows 10 & 11: 	PVist-win32-x64-[versionsnummer].7z
- Mac Intel:	PVist-darwin-x64-[versionsnummer].7z
- Mac Apple Silicon:	PVist-darwin-arm64-[versionsnummer].7z

### Windows 10 & 11
PVist ist portabel, dh. es braucht keine eigentliche Installation und kann von einem beliebigen Verzeichnis sofort ausgeführt werden.

-	PVist.exe starten<br/>
	Beim ersten Start erscheint der Dialog "Windows-Sicherheitshinweis":<br/>
	Falls PVist auch im Netzwerk z.B. von Handy, Tablets odere anderen PCs verwendet werden soll:<br/>
	Haken bei "Private Netzwerke" setzen, dann "Zugriff zulassen" setzen (erfordert Admin-Rechte)

	PVist läuft lokal auch ohne Freigabe durch die Firewall.

### Mac
- PVist starten
- gegebenenfalls die Firewall unter Systemeinstellung -> netzwerk -> Firewall anpassen, wenn PVist im Netzwerk verwendet werden soll

### Alle Versionen
Beim ersten Aufruf wird automatisch der Einstellungs-Dialog angezeigt

- Feld "IP-Adresse":<br/>
IP-Adresse oder Netzwerkname der S10 
Alle anderen Felder nicht verändern, Button "Speichern" klicken.

Wenn alles geklappt hat wird jetzt eine Linien-Grafik aufgebaut. Zu den oben angezeigten, letzten Werten und Statistiken gibt es jeweils Tooltips. 

Oben rechts können Einstellungen Einstellungen vorgenommen werden.

Wird das Hauptfenster geschlossen, dann wird auch der Server beendet.

### PVist… 
- belegt keine Ressourcen, wenn es beendet ist
- installiert keine Dienste, modifiziert nicht die Registry 
- telefoniert nicht nach Hause
- braucht keinerlei externen Ressourcen, auch nicht die von E3DC oder go-e
-	wer zusätzlich eine go-e Wallbox mit aktiviertem lokalen API V2 hat, kann unter den Einstellungen deren URL eingeben.
	Beispiele:
	http://go-echarger-123456.fritz.box/api/oder
	http://192.168.x.y/api/

	Hinter dem Netzwerknamen immer “/api/” anfügen. Dann werden zusätzlich der Leistungsverlauf und die zuletzt geladene Energie der WB in Blau angezeigt. 
	Dann wird zusätzlich ein blaues Auto-Symbol angezeigt, über das weitere Einstellung vorgenommen werden können. Dort kann das PV-Überschussladen aktiviert werden.

- wenn die Funktion "CSV-Datei abspeichern" aktiviert wird, erzeugt das Programm für jeden Tag eine separate CSV-Datei, in der die angezeigten Werte abgelegt werden. Die CSV-Dateien werden auf dem PC abgelegt, auf dem PVist läuft (“Server”) unter

-	Windows
	Windows-Verzeichnis für temporäre Dateien, das den symbolischen Namen "%temp%" hat (im Dateiexplorer eingegeben)
-	Mac
	Dokumentenordner

Die Dateien können z.B. mit Excel, Calc, oder Numbers weiter verarbeitet werden.

Wenn die aktuelle Datei gesperrt wird (z.B. durch eine Tabellenkalkulation), kann PVist keine weiteren Daten hinzufügen.

Diese Dateien werden von PVist nicht gelöscht.

Enjoy!
## Anmerkungen: 
Das Programm erzeugt ein Symbol im Infobereich (Windows) oder oben (Mac). Klick = Fenster anzeigen/verstecken, das Programm läuft dann im Hintergrund weiter. Rechtsklick auf Icon zeigt ein Menü an.
### Tasten
- Leertaste	Pause/Weiter
- e	Einstellungen
- l	Log einblenden 
- <Strg>-r	Bildschirm erneuern
- F11	Vollbild

### PVist kann 1:1 auch aus dem LAN / WLAN / Internet (per VPN) via

	https://[pcname bzw IP-Adr]:26180 

mit jedem Browser aufgerufen werden. Der dann folgende, einmalige Sicherheitshinweis bzgl. eines selbst ausgestellten Zertifikats kann getrost ignoriert werden, da der Web-Server selbst betrieben wird.
Zeitliche Auflösung
Die zeitliche Auflösung der Grafik kann per Menü rechts oben zwischen einer und 60 Sekunden gewählt werden, sie gilt für alle Betrachter der Grafik. Die Kurven werden nicht geglättet.
### Zoom / Cursor
Interessante Zeitfenster aus der Grafik können mit der linken Maustaste markiert werden. Der gestrichelte vertikale Cursor zeigt den genauen Zeitpunkt und dessen Werte an. 

Zoom beenden: Button rechts oben klicken.
### Statistik
Wenn während einer Pause (Leertaste) ein Bereich markiert wird, wird links eine Statistik eingeblendet, die z.B. in Excel per Cut&Paste weiter verwendet werden kann.

Auf diese Weise kann man z.B. den realen COP einer Wärmepumpe während der Warmwasserbereitung abschätzen, da man dann hinreichend genau ermitteln kann, wie viel Wasser mit welchem Energieeinsatz um welche Temperatur erwärmt wurde. 
### Überschussladen mit einer go-e Wallbox
Damit PVist die aktuellen Leistungswerte regelmäßig an die WB überträgt, muss in den PVist Einstellungen das Häkchen "Laden mit PV-Überschuss" gesetzt werden. 

Dann werden alle 5 Sekunden die aktuellen Werte an die WB übertragen, was diese zur Anpassung der Ladeleistung veranlasst. Die Wallbox muss zuverlässig im Netzwerk erreichbar sein.

Voraussetzung dafür ist, dass in den ECO-Einstellung der Handy-App die Überschussladung aktiviert ist. Alle anderen Parameter (Leistungslimit, wann Phasenumschaltung etc.) werden ebenfalls in der Handy-App eingestellt.

Wenn alles richtig konfiguriert ist, muss nur noch das Auto eingesteckt werden, die Ladung mit der Überschussleistung der PV startet dann nach kurzer Zeit automatisch. 

Schwindet die PV-Leistung oder ist das Auto geladen, wird die Ladeleistung reduziert oder die Ladung beendet. Die eigentliche Ladeleistung wird durch die WB oder das Auto selbst bestimmt, PVist liefert nur die aktuellen Daten dafür an die WB.

Es kann einige Sekunden dauern, bis die WB ihre Leistung an eine veränderte PV-Leistung anpasst, z.B. bei Wolken. 

Bei einem Wechsel der Anzahl der Phasen kann es zu einigen Sekunden Unterbrechung des Ladevorganges kommen.

Die Ladung des Autos wird höher als das Laden des S10-Akkus priorisiert.
### Sicherheit
PVist ist für den Inhouse-Gebrauch mit wohlwollenden Anwendern gedacht und bringt keine bekannten Sicherheitsprobleme mit sich. Es betreibt einen eigenen, rudimentären Webserver. 

Theoretisch können seine Dienste auch direkt ins Internet gestellt werden, wovon aber abzuraten ist. Dann könnte jeder beliebige Internet-Teilnehmer die Konfiguration verändern.

Es spricht aber nichts dagegen, es auch von unterwegs aus über ein VPN zu verwenden. 

Hinweise auf etwaige Schwachstellen nimmt der Autor gerne an.


## De-Installation (???)
### Windows
- das PVist-Installationsverzeichnis mitsamt allen Unterverzeichnissen löschen
- das Verzeichnis %appdata%/PVist mitsamt allen Unterverzeichnissen löschen
- ggf. angelegte Firewall-Regeln löschen (Systemsteuerung -> “Apps über die Windows-Firewall kommunizieren lassen”)
### Mac
- App löschen
- ggf. Firewall zurücksetzen
