#####################
Paypal Modul (legacy)
#####################

.. note::
   Diese Dokumentation ist nur die veraltete PayPal Plus / IPN Integration gültig (Aggrosoft PayPal Modul / aggrosoft/oxid-aspaypal)
   Für neue Shop Installation prüfen Sie bitte die :doc:`Dokumentation des Aggrosoft PayPal 2.0 Moduls</modules/oxid/agpaypal2>`

Installation
========================
Siehe :doc:`/intro/install`

IPN Verbindung
========================
Damit der Shop automatisch auf eingegangene PayPal Zahlungen reagieren kann ist es nötig eine sogenannte IPN Verbindung bei PayPal zu aktivieren. Loggen Sie sich hierzu auf der PayPal Website in Ihr Konto ein, anschließend klicken Sie bitte unter „Mein Konto“ auf „Mein Profil“. Im dort erscheinenden Bildschirm wählen Sie bitte auf der linken Seite „Verkäufer/Händler“. Hier dann bei „Benachrichtigungen über Sofortzahlungen“ auf „Aktualisieren“. Aktivieren Sie nun die Sofortige Zahlungsbestätigung und geben Sie folgende Benachrichtigungs URL ein:

`http://www.meinedomain.de/index.php?aspaypal_cl=aspaypal_ipn`

Nachdem Sie die IPN Verbindung eingerichtet haben sollte das Modul vollständig eingerichtet sein, bitte prüfen Sie nun ob die Zahlungsart reibungslos funktioniert.

Einrichtung von PayPal Plus
====================================
* Schalten Sie zuerst PayPal Plus in Ihrem PayPal Konto frei
* Legen Sie den REST-App unter https://developer.paypal.com/developer/applications/ an
* Gehen Sie auf erstellen REST-App und kopieren Sie die Client ID und Secret (Live Modus) in die entsprechende Eingabefelder bei den PayPal Modul Einstellungen
* Aktivieren Sie die Checkbox "PayPal Plus Aktiv"
* Aktivieren Sie die Checkbox "PayPal Plus Live Modus"
* Legen Sie den täglichen Cronjob `"/usr/bin/curl http://www.meinedomain.de/index.php?cl=aspaypal_cron"` an

Einstellungen
========================
Im Admin wird ein neuer Punkt Aggrosoft -> Paypal Modul gezeigt, unter dem alle Einstellungsmöglichkeiten zu finden sind.

E-Mail Adresse Paypal Händlerkonto
---------------------------------------------------------
Ist die E-Mail Adresse an die die Zahlungen Ihrer Kunden gesendet werden sollen. Dieses Konto wird später auch für die IPN Verbindung eingerichtet.

Live Modus
-------------------
Ist diese Option nicht gewählt wird PayPal im sogenannten „Sandbox Modus“ angesprochen. Dadurch ist es möglich die Zahlungen auszuprobieren ohne eine wirkliche Transaktion durchzuführen. Mehr Informationen hierzu erhalten Sie direkt von PayPal.

PayPal Express aktiv
--------------------------------------
Wenn Sie PayPal Express verwenden möchten müssen Sie diese Einstellung aktivieren und die nötigen API Zugangsdaten eintragen (siehe weiter unten)

API Benutzername, API Passwort, Unterschrift
---------------------------------------------------------
Um die Express API von PayPal nutzen zu können müssen Sie diese Einstellungen aus Ihrem PayPal Konto auslesen, loggen Sie sich hierzu in Ihr PayPal Konto ein. Klicken Sie auf "Mein Profil" => "Verkäufer/Händler" => "API-Zugriff" => "Aktualisieren". Wählen Sie dann "Option 2 / API-Signatur anzeigen", im folgenden Bildschirm können Sie vorhandene Zugangsdaten einsehen oder neue beantragen. Übernehmen Sie die angezeigten Einstellungen in die Moduleinstellungen.

Kommentar
-------------------
Ein frei wählbarer Kommentar der zu Paypal im dementsprechenden Feld übertragen wird.

Weiter Button Titel
--------------------------------------
legt die Beschriftung des „Weiter“ Buttons bei PayPal fest.

Hintergrund Farbe Buttons
--------------------------------------
geben Sie hier einen beliebigen Hex-Farbcode ein um die Hintergrundfarbe der Buttons bei PayPal zu beeinflussen.

Erfolgslink
--------------------------------------
falls Sie möchten dass der Kunde nicht auf der Danksagungsseite sondern auf einem anderen Link nach erfolgreicher Zahlung landet können Sie dieses Feld befüllen. Im Normalfall bleibt dieses Feld leer.

Abbruchlink
--------------------------------------
falls Sie möchten dass der Kunde nicht auf der Zahlungsarten Seite sondern auf einem anderen Link nach abgebrochener Zahlung landet können Sie dieses Feld befüllen. Im Normalfall bleibt dieses Feld leer.

„Warte“ Meldung
--------------------------------------
während der Kunde zu PayPal weitergeleitet wird erscheint eine Meldung die Sie hier eintragen können.

„Ihre Bestellung“ Meldung
--------------------------------------
gibt die Kennzeichnung für den Artikel der zu PayPal übertragen wird an. Es wird automatisch der Name Ihres Shops angehangen.

Paypal Sprache
--------------------------------------
die Sprache die bei Paypal ausgewählt sein soll. Lassen Sie dieses Feld leer um anhand der gewählten Sprache des Kunden zu wählen.

Bestellordner
--------------------------------------
In diesem Ordner werden Bestellungen automatisch übertragen nachdem die PayPal Zahlung eingegangen ist.

Shop-Logo an Paypal übergeben
--------------------------------------
Übergibt das Logo Ihres Shops automatisch an PayPal, bitte beachten Sie dass diese Option zu einer Sicherheitswarnung beim Kunden führt wenn kein SSL in Ihrem Shop aktiviert ist.

Warenkorb an Paypal übergeben
--------------------------------------
Übergibt die kompletten Inhalte des Warenkorbs an PayPal.

PayPal-Button auf der Details-Seite anzeigen
--------------------------------------------------------
Zeigt den PayPal Express Button direkt auf der Detailseite an, der Kunde kann Artikel dann direkt von dort über PayPal kaufen.

Testserver URL
--------------------------------------
ist die URL des Paypal Testservers (für Transaktion die nicht im Live Modus statt finden). Im Normalfall ist die Voreinstellung korrekt.

Liveserver URL
--------------------------------------
ist die URL des Paypal API Server (für Transaktion die im Live Modus statt finden). Im Normalfall ist die Voreinstellung korrekt.

Sandbox API-Endpoint
--------------------------------------
API-Point des Paypal API Server (für Transaktion die nicht im Live Modus statt finden). Im Normalfall ist die Voreinstellung korrekt.

Production API-Endpoint
--------------------------------------
API-Point des Paypal API Server (für Transaktion die im Live Modus statt finden). Im Normalfall ist die Voreinstellung korrekt.

API-Version
--------------------------------------
API-Version die verwendet wird. Im Normalfall ist die Voreinstellung korrekt.
