#####################
Varianten Filter
#####################

Installation
============
Siehe :doc:`/intro/install`

Bitte beachten Sie dass für den Varianten Filter eine funktionierende Elasticsearch Installation notwendig ist,
folgen Sie hierzu bitte den Anweisungen in der Elasticsearch Dokumentation.

Einstellungen
=============

Filter im Frontend Aktiv
------------------------
Zeigt den Filter im Shop Frontend an, lassen Sie diese Option deaktiviert bis Sie das Daten Mapping abgeschlossen haben.

Maximale Variantentiefe
-----------------------
Wird nicht mehr verwendet, bitte nicht ausfüllen. Option wird in einem folgenden Update entfernt.

Artikel aus Unterkategorien anzeigen
------------------------------------
Berücksichtigt beim Filtern auch alle Unterkategorien der aktuell gewählten Kategorie.

Hersteller Filter anzeigen
---------------------------
Zeigt den Hersteller Filter im Shop Frontend an.

Preis Filter anzeigen
---------------------------
Zeigt den Preis Filter im Shop Frontend an.

Elasticsearch Hosts
-------------------
Liste von IP Adressen Ihrer Elasticsearch Hosts, wenn leer wird http://localhost:9200 verwendet.

Daten Mapping
=====================
Um doppelte Werte und unnötige Filter zu verhindern müssen die vorhandenen Varianten und Attribute vorbereitet werden.

Gruppen
--------
Gruppen bezeichnen die einzelnen filterbaren Gruppen von Optionen, wie z.B. Farbe, Größe etc.
Die Liste der Gruppen wird aus allen vorhandenen Variantennamen und Attributen gebildet. Damit eine Variante oder ein
Attribut im Frontend sichtbar wird muss ein Mapping vorgenommen werden.

Tragen Sie für alle filterbaren Gruppen einen Wert in das Feld Anzeigewert ein. Wenn Sie für verschiedene Werte den
gleichen Anzeigewert eintragen werden die Werte zusammengefasst.

Wenn Sie ein Attribut oder eine Variante die bildliche Darstellung beeinflusst aktivieren Sie die Option :guilabel:`Bildrelevant`

Beispiel:

+---------+-------------+--------------+
|   Wert  | Anzeigewert | Bildrelevant |
+---------+-------------+--------------+
|  Farbe  |    Farbe    |    |check|   |
+---------+-------------+--------------+
| Färbung |    Farbe    |    |check|   |
+---------+-------------+--------------+
|  Größe  |    Größe    |   |remove|   |
+---------+-------------+--------------+
|  Ausmaß |    Größe    |   |remove|   |
+---------+-------------+--------------+

Wenn die Werte wie oben in der Tabelle angezeigt konfiguriert werden hat der Benutzer im Shop die Möglichkeit nach
:guilabel:`Farbe` und :guilabel:`Größe` zu filtern. Die Werte des Attributs :guilabel:`Färbung` werden mit in :guilabel:`Farbe` angezeigt,
die Werte des Attributs :guilabel:`Ausmaß` in :guilabel:`Größe`

Optionen
--------
Optionen bezeichnen die auswählbaren Werte innerhalb der Gruppen, wie z.B. Rot, Grün, Blau, S, M, L etc.
Die Liste der Optionen wird aus allen vorhandenen Variantentiteln und Attributwerten gebildet.
Damit eine Wert im Frontend sichtbar wird muss ein Mapping vorgenommen werden.

Sie haben die Möglichkeit mehrere Werte für eine Option zu wählen,
so könnte Rot/Weiß im Shop jeweils im Wert Rot oder Weiß erscheinen.

Die Vorschlagsliste enthält alle bisher gesetzten Anzeigewerte, jeder individuelle Anzeigewert erzeugt eine Auswahl
innerhalb der zugehörigen Gruppe.

Anzeige
-------
Die einzelnen Optionswerte können wenn gewünscht als Bild oder Farbwert dargestellt werden, außerdem können Sie jedem
Wert eine individuelle Sortierung vorgeben. Die Werte werden nach der Sortierung aufsteigend im Filter angezeigt.

Index aktualisieren
=====================
Nachdem Sie ein Mapping geändert muss der Index des Filters neu aufgebaut werden. Die entsprechende Funktion hierzu
befindet sich unter Home => Index neu erstellen.