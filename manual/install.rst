.. _manual_install:

MetaModels installieren und aktualisieren
=========================================

Allgemeine Informationen zur Installation
-----------------------------------------

MetaModels besteht aus mehreren Modulen, die je nach Aufgabenstellung installiert werden müssen.

Im Contao-Manager werden über die Eingabe `metamodels/` alle zur Verfügung stehenden Pakete
von MetaModels aufgelistet. Das Basispaket `metamodels/core` muss installiert werden - darüber hinaus
können weitere Attribute und Filter je nach Aufgabenstellung hinzugefügt werden.

Neben den einzelnen Paketen gibt es `Bundles`, die verschiedene Pakete für eine vereinfachte Installation
zusammenfassen.

Für den Einstieg in MetaModels ist das Bunde `metamodels/bundle_start` zu empfehlen - hiermit
werden der Core sowie die wichtigsten Attribute und Filter installiert.

Zudem gibt es auch das Bundle `metamodels/bundle_all`, welches neben dem
`bundle_start` auch die mehrsprachigen Pakete mit installiert (Hinweis: die Pakete `translatedselect`
`translatedtags` sind hier seit MM 2.1 nicht mehr inkludiert, da diese nur für Spezialfälle einzusetzen sind).

Weitere Module wie "Registerfilter", "Umkreissuche", "Bewertung" usw. sind als separate Pakete
hinzu zu fügen - siehe :ref:`extended_index`

.. seealso:: Erfolgt die Installtion über den Contao-Manager und es sind schon Pakete installiert, die
   noch ein altes Paket vom MultiColumnWizard (MCW) enthalten, kann der Manager (bzw. der Composer)
   das nicht austauschen und gleichzeitig installieren. Als "Trick" dazu, erst alle vorhandene Erweiterungspakete
   für eine Aktualisierung markieren und anschließend das oder die MM-Pakete hinzufügen und übernehmen;
   alternativ dazu, ein `composer update` auf der Konsole -
   siehe `'Forum' <https://community.contao.org/de/showthread.php?72871-MCW-MultiColumnWizard-als-Bundle-f%C3%BCr-Contao-4-(stable)&p=502709&viewfull=1#post502709>`_.


Neben dem Contao-Manager ist die Installation der Pakete und Bundles direkt über die Konsole per
Composer möglich - z.B. mit

``php web/contao-manager.phar.php composer require metamodels/core``

bzw.

``php web/contao-manager.phar.php composer require metamodels/bundle_start``

Statt `php` ist ggf. der Pfad zum entsprechenden PHP-Binary anzugeben -
siehe :ref:`rst_cookbook_symfony_mm-2-1-tips`.

Nach der Installation ist über das Install-Tool von Contao ein **Update der Datenbank nicht zu vergessen!**

Es folgen weitere Informationen zu den einzelnen Versionen von MetaModels.


Installation von MM 2.2 für Contao 4.9
--------------------------------------

MetaModels 2.2 bringt eine volle Kompatibilität zu Contao 4.9 mit sowie verschiedene Features und
Optimierungen. Zum Beispiel ist MM 2.2 kompatibel zum `strict mode` von höheren MySQL-Versionen oder
aktueller MariaDB oder die manuelle Dateisortierung.

Die Installationsvoraussetzungen für MetaModels 2.2 sind:

* ein laufendes Contao 4.9.x (LTS) und
* PHP 7.2/7.3
* MySQL ab 5.5.5 (InnoDB), MariaDB

Höhere Versionen von Contao und/oder PHP sind möglich, werden aber nicht ofiziell supportet.

**MetaModels 2.2 ist ab sofort einsatzbereit** und kann über den Composer (Konsole) oder den
Contao-Manager installiert werden. Zugang zu dem aktuell noch geschützem Repository erhält
man über unser "eary adopter Programm" - mehr dazu unter Fundrasing auf der
`MM Webseite <https://now.metamodel.me/de/unterstuetzer/fundraising#metamodels_2-2>`_.

Weitere Features von MM 2.2 (wird laufend ergänzt):

* kompatibel zum `strict mode` von MySQL und MariaDB
* verschiedene Optimierungen für eine schnellere Anzeige von Daten
* Backend von MM "aufgeräumt" und typische Einstellungen als default gesetzt
* manuelle Dateisortierung (inkl. übersetzte Dateien)
* Slug-Generator für Alias und übersetzter Alias sowie Option zum Verhindern des "id-"-Präfix
* Frontend-Editing mit Dateiupload inkl. Drag&Drop, deaktivieren/löschen von Dateien, Thumbnails bei Bildern

Das MM-Team unterstützt mit der Arbeit/Finanzierung auch die Arbeiten am
`DC_General <https://github.com/contao-community-alliance/dc-general/>`_, der u.A. bei MM für die Anzeigen
im Backend zuständig ist und viele tolle Funktionen mitbringt.

.. seealso:: Für eine Re-Finanzierung der umfangreichen Arbeiten, bittet das MM-Team um finanzielle
   Zuwendung. Als Richtgröße sollte der Umfang des zu realisierenden Projektes genommen werden
   und etwa 10% einkalkuliert werden - aufgrund der Erfahrung der letzten Zuwendungen, sind
   das Beträge zwischen 100€ und 500€ (Netto) - eine Rechnung inkl. MwSt wird natürlich immer
   ausgestellt. `Mehr... <https://now.metamodel.me/de/unterstuetzer/spenden>`_


Installation von MM 2.1 für Contao 4.4
--------------------------------------

Die Installationsvoraussetzungen für MetaModels 2.1 sind:

* ein laufendes Contao 4.4.x (LTS) und
* PHP 7.1/7.2
* MySQL ab 5.5.5 (InnoDB), MariaDB (ohne `strict mode`)

Höhere Versionen von Contao und/oder PHP sind möglich, werden aber nicht ofiziell supportet.


Hinweise und Anleitungen für ältere Contao- und MM-Versionen
------------------------------------------------------------

* :ref:`cookbook_move_mm2.0_to_2.1`
* :ref:`cookbook_install_mm2.0-and-older`


Umstellung von `metamodels/bundle_*` auf separate Module
--------------------------------------------------------

Bei einer Umstellung z.B. von 2.0 auf eine neuere version oder Neuinstalltion ist es eine gute Gelegenheit, nur noch
die Attribute und Filter zu installieren, die für das Projekt notwendig sind. War zuvor z.B. `metamodels/bundle_all`
oder `metamodels/bundle_all` im Einsatz, kann man mit den folgenden SQL-Befehlen die wirklich verwendeten Attribute
und Filter abfragen:

.. code-block:: sql
   :linenos:
   
   -- Attribute
   SELECT type FROM `tl_metamodel_attribute` GROUP BY type ORDER BY type
   
   -- Filter
   SELECT type FROM `tl_metamodel_filtersetting` GROUP BY type ORDER BY type

Die daraus sich ergebende Liste kann dann über den Contao Manager oder die Konsole installiert werden und nicht genutzte
Module bleiben außen vor.


Test von speziellen Paketen
---------------------------

Neben den aktuell verfügbaren und freigegebenen Pakete von MetaModels, gibt es teilweise
Pakete mit Bugfixes oder neuen Funktionen, die getestet werden können/müssen - das
könnte z.B. für den MetaModels-core das ein Paket ``hotfix/2.1.25`` sein. Zu sehen sind die Pakete u.a.
auf Github im entsprechenden Repository (z.B. MetaModels/core) im Reiter
`'branches' <https://github.com/MetaModels/core/branches>`_. Die dort angegebene Bezeichnung wie
``hotfix/2.1.25`` muss um den Präfix ``dev-`` ergänzt werden, sowie um ein ``as 2.1.25`` am Ende.

Möchte man ein solches Paket testen, muss es explizit im Contao-Manger mit 

``dev-hotfix/2.1.25 as 2.1.25``

oder in der composer.json

``"metamodels/core": "dev-hotfix/2.1.25 as 2.1.25"``

mit seiner Version angegeben werden.

Anschließend über den Contao-Manager oder auf der Konsole ein Update machen.

Da MetaModels eng mit dem DC_General (DCG) verzahnt ist, muss zum Testen häufig auch hier
auf eine neuere Version geupdatet werden. Das Vorgehen ist das gleiche wie bei MetaModels
inklusive der Anpassung des JSON-Eintrages mit "as 2.1.x".

Die Composer-JSON sollte für die Implementierung der Pakete für Core und DCG in etwa die
folgenden Einträge im Knoten "require" aufweisen (Zeile 8 und 10):

.. code-block:: json
   :linenos:
   
   {
       "name": "local/website",
       "description": "A local website project",
       "type": "project",
       "license": "proprietary",
       "require": {
           "contao-community-alliance/composer-client": "~0.12",
           "contao-community-alliance/dc-general": "dev-hotfix/2.1.42 as 2.1.42",
           "metamodels/bundle_all": "^2.1",
           "metamodels/core": "dev-hotfix/2.1.25 as 2.1.25",
           ...
       },
       ...
   }

Um auf den ursprünglichen Stand zurück zu gelangen, die Pakete wieder auf ihren ursprünglichen Aufruf
z.B. "^2.1" zurücksetzen und ein Update inkl. Datenbank machen..

Wichtig ist nach einem Test die Rückmeldung zum Entwickler bzw. an das MetaModels-Team über
`Github <https://github.com/MetaModels>`_.

Zwei weitere Möglichkeiten sind die Installation eines Forks oder eines Pull-Requests (PR).
Hier muss für die Installation die composer.json angepasst werden.

Bei einem Fork (ggf. in den Einstellungen der Paketverwaltung den eigenen Github oAuth Token
eintragen) z.B.

.. code-block:: json
   :linenos:
   
   {
       "name": "local/website",
       "description": "A local website project",
       "type": "project",
       "license": "proprietary",
       "require": {
           "contao-community-alliance/composer-client": "~0.12",
           "contao-community-alliance/dc-general": "^2.1",
           "metamodels/bundle_all": "^2.1",
           "byteworks/metamodelsattribute_multi": ">=1.0.5.0,<1.1-dev",
           ...
       },
       ...
       "repositories": [
           ...
           {
               "type": "vcs",
               "url": "https://github.com/byteworks-ch/contao-metamodelsattribute_multi.git"
           }
       ],
       ...
   }

oder für einen PR mit dem Hash des Commits - diesen findet man unter Github bei dem PR beim
Reiter "Commits".

.. code-block:: json
   :linenos:
   
   {
       "name": "local/website",
       "description": "A local website project",
       "type": "project",
       "license": "proprietary",
       "require": {
           "contao-community-alliance/composer-client": "~0.12",
           "contao-community-alliance/dc-general": "^2.1",
           "metamodels/bundle_all": "^2.1",
           "metamodels/attribute_alias": "dev-master#a97ec461ae1254fa616811c3ce234515238fb3c7",
           ...


.. |br| raw:: html

   <br />
