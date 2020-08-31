#####################
Installation
#####################

Unsere Module werden über den `Composer Paketmanager <https://getcomposer.org/>`__ installiert,
hierzu stellen wir ein sog. Repository bereit. Ein Modul dass über composer installiert wurde lässt
sich mit minimalem Aufwand Aktualisieren und Warten.

Composer installieren
=====================
.. Attention::
   Die Art wie composer installiert werden kann unterscheidet sich je nach Hosting Umgebung, bitte wenden Sie sich bei
   Fragen direkt an Ihren Hoster.

Composer wird auf manchen Hosting Umgebungen global zur Verfügung gestellt oder kann per Paketmanager (z.B. pkg oder apt)
installiert werden. Eine Installation ist jedoch auch ohne Root Rechte möglich, folgen Sie hierzu den Schritten die
in der `Installationsanleitung von Composer <https://getcomposer.org/download/>`__.

Repository hinzufügen
=====================

Wenn Sie zum ersten mal eines unserer Module installieren muss zunächst unser Paketserver in der composer.json Datei des
Shop Projekts registriert werden. Führen Sie hierzu folgenden Befehl im Ordner aus in dem sich die composer.json des
Projekts befindet

.. code-block:: bash

    composer config repositories.aggrosoft composer https://packages.aggrosoft.de

Paket installieren
==================

Nachdem das Repository konfiguriert wurde können Sie zukünftig Module einfach über folgenden Befehl installieren

.. code-block:: bash

    composer require aggrosoft/<Paketname>

Den notwendigen Befehl bzw. Paketnamen finden Sie in den :doc:`Lizenzdetails <license>` des Moduls

Lizenz hochladen
==================

Laden Sie die :doc:`Modullizenz <license>` aus Ihrem Konto herunter und speichern Sie die Datei **unverändert** und mit der Endung .lic
im Modulordner ab - z.B. ``source/modules/agupload/license/``


Modul installieren
==================

Aktivieren Sie nun das Modul im Shop, die restliche Installation erfolgt dadurch automatisch.
Wenn Sie mit Oxid eShop arbeiten führen Sie anschließend den Befehl :guilabel:`Views aktualisieren`
im Menü ``Service => Tools`` aus.
