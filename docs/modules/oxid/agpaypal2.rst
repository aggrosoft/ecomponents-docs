#####################
Paypal Modul 2.0
#####################

.. note::
   Diese Dokumentation ist nur für die neue PayPal Commerce Integration gültig (Aggrosoft PayPal 2.0 / aggrosoft/oxid-agpaypal)
   Für ältere Shop Installation und vorhandene Installationen prüfen Sie bitte die :doc:`Dokumentation des Vorgänger Moduls</modules/oxid/agpaypal>`

Installation
========================
Siehe :doc:`/intro/install`

REST App anlegen
====================================
* Legen Sie eine REST-App unter https://developer.paypal.com/developer/applications/ an
* Klicken Sie auf "Live" - klicken Sie auf "Create App" um eine neue App anzulegen. Den Namen der Applikation können Sie frei wählen. Kopieren Sie die Client ID und Client Secret in die entsprechende Eingabefelder der Modul Einstellungen.

Einstellungen
========================
Die Moduleinstellungen werden wie gewohnt unter "Einstellungen" => "Module" => "Aggrosoft PayPal 2.0" => "Einstell." eingetragen.

Zugangsdaten
~~~~~~~~~~~~~~~

PayPal Händler E-Mail Adresse
---------------------------------------------------------
Die E-Mail Addresse des PayPal Business Konto für die Zahlungen entgegen genommen werden sollen.

Rest Client ID / Rest Client Secret
---------------------------------------
Zugangsdaten die im Schritt "REST App anlegen" erzeugt wurden.

Webhook Id
--------------------------------------
Sofern die Rest App Zugänge korrekt eingetragen wurden erzeugt das Modul automatisch den benötigten Webhook und trägt die ID ein.
Ändern Sie diese ID nur wenn es hierfür einen technischen Grund gibt.

Einstellungen
~~~~~~~~~~~~~~~

PayPal Sandbox nutzen
--------------------------------------
Verbindet das Modul mit der PayPal Sandbox Umgebung, nutzen Sie diese Einstellung zusammen mit einer Sandbox App um
das Modul zu testen.

.. note::
   Wir raten dazu das Modul zunächst in einer Testumgebung mit Sandbox Zugangsdaten zu testen.

Bestellungen die nicht authorisiert werden konnten automatisch stornieren
--------------------------------------------------------------------------
Storniert Bestellungen bei denen die Authorisierung zurückgenommen wurde automatisch, dies kann der Fall sein
bei Kreditkarten Betrug oder nachgelagerten Ablehnungen im Rechnungskauf.

Log Level
--------------------------------------------------------------------------
Bestimmt wie viele Informationen zur Kommunikation mit PayPal in der Datei logs/agpaypal.log abgelegt werden.
Sie können zwischen Fehlern, allen Anfragen und keinem Logging wählen - im Live Betrieb sollte das Level maximal
auf "Fehler" stehen. Beachten Sie bitte dass die Log Datei nicht automatisch gelöscht oder bereinigt wird.

Zahlungsarten definieren
========================
Das Modul generiert während der Installation keine Zahlungsarten, diese müssen von Ihnen angelegt werden.
Legen Sie für jede gewünschte Zahlungsart (PayPal, Kreditkarte, Rechnung, IDEAL, EPS etc.) eine separate Zahlungsart an.
(Siehe `Oxid eShop Handbuch<https://docs.oxid-esales.com/eshop/de/6.2/einrichtung/zahlungsarten/zahlungsarten.html>`_

Legen Sie bei den Zahlungsarten im vom Modul erzeugten Feld *PayPal Zahlungsmethode* die gewünschte PayPal Zahlungsart.

.. note::
   Um die PayPal Express Funktionen zu nutzen (Kauf direkt aus Detailseite/Warenkorb) **muss** eine Zahlungsart existieren
   bei der das Feld *PayPal Zahlungsmethode* mit dem Wert *PayPal* belegt ist.

.. warning::
   Achten Sie darauf die Zahlungsart mit den entsprechend von PayPal erlaubten Ländern zu verknüpfen - EPS ist zum Beispiel
   nur für Kunden aus Österreich verfügbar. Sollten Sie die Zahlungsart einem deutschen Kunden anbieten führt dies zu einer
   Fehlermeldung.

   Bestimmte Zahlungsarten müssen separat für Ihren PayPal Account freigeschalten werden (Kreditkarte, Rechnung) - wenden
   Sie sich bei Fragen hierzu an den PayPal Händler Support.