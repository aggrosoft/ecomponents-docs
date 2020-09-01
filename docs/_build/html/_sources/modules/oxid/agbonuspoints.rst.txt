#####################
Bonus Punkte Modul
#####################

Installation
============
Siehe :doc:`/intro/install`

Einstellungen
=============

Bonusmodus
----------

* **Für jede Bestellung** des Eingeladenen dem Werber Bonuspunkte gutschreiben
* **Für die erste Bestellung** des Eingeladenen dem Werber Bonuspunkte gutschreiben

Gibt an ob Kunden die andere Kunden einladen nur für die erste oder für jede Bestellung Bonuspunkte erhalten.

Punkte oder Prozent des Bestellwerts pro Verkauf
------------------------------------------------
Definiert wie viele Punkte (oder Prozent) der Kunde erhält. Diese Einstellung gibt es jeweils für die Werber eines Kunden
sowie für den eigentlichen Käufer.

.. Attention::
   Die prozentuale Berechnung richtet sich am Brutto Gesamtwert der Bestellung.

Punkte prozentual oder absolut vom Bestellwert berechnen
--------------------------------------------------------
Bestimmt ob die Punkte prozentual oder absolut berechnet werden. So könnte ein Kunde entweder absolut 10 Punkte bekommen
oder 10% in Punkten - gerechnet am Bestellwert. Diese Einstellung gibt es jeweils für die Werber eines Kunden
sowie für den eigentlichen Käufer.

Cents pro Punkt
-------------------
Gibt den Umrechnungsfaktor von Cents zu Punkten an.

Feld anhand dessen das Datum bis zur Gutschrift berechnet wird
--------------------------------------------------------------
Bestimmt ob die Tage bis die Punkte gutgeschrieben werden ab dem Bestell- oder dem Versanddatum gerechnet werden.

Tage bis Punkte gutgeschrieben werden
-------------------------------------
Anzahl der Tage bis die Punkte den Kunden gutgeschrieben werden, im Normalfall 14 Tage (Widerrufsfrist) oder länger.

Dezimalstellen für Punkte erlauben
----------------------------------
Wenn aktiviert können Punkte geteilt werden, der Kunde kann dann auch z.B. 3,5 Punkte einlösen.

Punkte für das Schreiben einer Bewertung
----------------------------------------
Anzahl der Punkte die ein Kunde für das Schreiben einer Bewertung erhält.

Punkte für die erstmalige Anmeldung zum Newsletter
--------------------------------------------------
Anzahl der Punkte die ein Kunde für die Anmeldung zum Newsletter erhält.

Cron Job
=============
Damit die Punkte verrechnet werden muss regelmäßig ein Cronjob ausgeführt werden der die Punkte
berechnet. Hier ein Beispiel für einen Cronjob der die Punkte immer um Mitternacht berechnet:

.. code-block:: bash

    0 0 * * * curl "http://<SHOP_URL>/index.php?cl=agbonuspoints_cron"

Passen Sie die Shop Url entsprechend Ihrem System an, ohne diesen Aufruf werden die Punkte nicht berechnet

Alte Daten ignorieren
=====================

Folgenden SQL Befehl ausführen um bereits vorhandene Bestellungen von den Berechnungen auszuschließen:

.. code-block:: sql

    UPDATE `oxorder` SET oxpointscalculated = 1, oxtimestamp = '0000-00-00 00:00:00';

Folgenden SQL Befehl ausführen um bereits vorhandene Bewertungen von den Berechnungen auszuschließen:

.. code-block:: sql

    UPDATE `oxreviews` SET oxpointscalculated = 1;