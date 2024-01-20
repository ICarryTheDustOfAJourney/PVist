# PVist
 	Photovoltaik ist-Werte anzeigen für S10 PV-Anlagen der Firma E3DC
	Optional mit einer go-e Wallbox und PV-Überschussladen

	Eine portable Anwendung, die ohne die Notwendigkeit eines dedizierten Servers auskommt. 
	Es ist ein nicht-kommerzielles Freizeitprojekt, der Einsatz erfolgt auf eigene Gefahr.

## Voraussetzungen für den Betrieb

- Windows 10, 11 oder macOS, Intel oder Apple Silicon CPU
- der Modbus der S10 muss aktiviert sein:
  Hauptmenü -> Smart-Funktionen-> Smart Home 2x aktivieren
  Eintrag muss grün unterlegt sein, Port 502 wie voreingestellt verwenden

- die IP-Adresse oder Netzwerkname der S10 muss bekannt sein, Beispiele:
	Netzwerkname: http://S10.fritz.box
		oder
	IP-Adresse: http://192.168.2.1


Zu finden im Netzwerk-Router (FritzBox etc) oder im S10 Hauptmenü -> System -> Netzwerk- > System-IP


Falls eine go-e Wallbox eingebunden werden soll:

die IP-Adresse oder Netzwerkname der Wallbox muss bekannt sein. Beispiele:
	Netzwerkname: http://go-echarger-123456.fritz.box
		oder
	IP-Adresse: http://192.168.2.1

Ggf. das API V2 der WB in der go-e Handy-App freischalten:
“Internet” -> “Erweiterte Einstellungen” -> “Lokale HTTP API v2 erlauben”

Wenn zusätzlich das PV-Überschussladen verwendet werden soll:
ggf. WB-Firmware 55.5 oder später in der go-e Handy-App unter 
“Internet” -> “Firmwareversion” installieren

