#####################
Upload Modul
#####################

Einstellungen
=============

Upload Dateipfad
----------------
Die vom Kunden hochgeladenen Dateien werden unter diesem Pfad abgelegt, der Pfad ist ausgehend vom ``source`` Verzeichnis
des Shops. Wir raten aus Datenschutzgründen dazu den Pfad mit eine Verzeichnisschutz zu versehen, dadurch wird er durch
Zugriff durch Dritte geschützt.

Wenn der Pfad nicht existiert wird versucht ihn anzulegen, innerhalb dieses Ordners wird ein ``ordered`` Unterordner erstellt,
in diesen Ordner werden Dateien verschoben die zu einer Bestellung gehören.

.. Attention::
   Der Pfad darf nicht mit einem Slash beginnen und muss mit einem Slash enden

Minimale Dateigröße
-------------------
Die minimale Dateigröße in Byte die eine Datei haben muss um hochgeladen zu werden

Maximale Dateigröße
-------------------
Die maximale Dateigröße in Byte die eine Datei beim Hochladen haben darf. Der Wert 0 deaktiviert diese Beschränkung.
Beachten Sie dass dieser Wert außerdem durch Ihre Hosting Umgebung beeinflusst wird
(z.B. `php upload_max_filesize <https://www.php.net/manual/de/ini.core.php#ini.upload-max-filesize>`__)

Erlaubte Dateitypen
-------------------
Gibt an welche Dateiendungen von den Kunden hochgeladen werden dürfen. Achten Sie darauf nur unbedingt notwendige Endungen
anzugeben, es könnte sonst zu Angriffen durch manipulierte Scripts oder Viren kommen. Aus Sicherheitsgründen muss
diese Einstellunge gesetzt werden. Geben Sie eine Endung pro Zeile an z.B.

.. code-block::

    .jpg
    .png
    .pdf

Cron Job
=============
Um nicht von Kunden bestellte Dateien vom Server zu entfernen raten wir Ihnen einen Cronjob einzurichten der
die unnötigen Dateien löscht. Ein Beispiel Cron könnte wie folgt aussehen

.. code-block::

    0 0 * * * find /pfad/zum/shop/source/out/pictures/uploads/ -maxdepth 1 -type f -mtime +14 -delete

Passen Sie den Pfad entsprechend Ihrem System an, bitte beachten Sie dass ein falscher Pfad zum Verlust von Daten führen kann.
Der Cron löscht automatisch um Mitternacht alle hochgeladenen Dateien die älter als 14 Tage und nicht bestellt sind.