.. _rst_features:

Funktionsübersicht
==================

Flexible Datenmodelle
---------------------

MetaModels ermöglichen es Datenmodelle komfortabel und (nahezu)
ohne Beschränkungen im Backend von Contao zu definieren.

In den Datenmodellen stehen verschiedene vom Datentypen für die Datenfelder
(Attribute) zur Verfügung: sei es Reintext, Bilder, Zahlen oder gar Tags
- alles ist möglich. Sollte eine Beschränkung erreicht werden in dem der
gewünschter Datentyp nicht verfügbar ist, kann dieser mit minimalem Aufwand
implementieret werden.

Das flexible Rechtesystem welches für MetaModels entwickelt wurde, gestattet
es, unterschiedliche Backendansichten für Redakteur- und Administrator-Benutzergruppen
zu definieren. Die Eingabemasken verwenden weiterhin das aus Contao bekannte
'Look und Feel'.

Das Backend kann weiterhin dahingehend angepasst werden, dass nur bestimmte
Gruppen Zugriff auf einzelne Eingabefelder erhalten und obendrein kann auch
deren Reihenfolge individuell pro Benutzergruppe angepasst werden. Dies stellt
den ersten Schritt in Richtung perfekter Arbeitsabläufe dar.

Mehrsprachigkeit
----------------

MetaModels wurden von Anfang an mit dem Anspruch der Mehrsprachigkeit entwickelt.
Daher können Attribute die Übersetzung der von ihnen gespeicherten Daten in
mehrere Sprachen unterstützen. Man muss im Backend lediglich mittels des
Sprachenwählers in die gewünschte Sprache wechseln und kann sofort den Datensatz
in der gewählten Sprache bearbeiten.

Das Beste hierbei ist, das Attribute die nicht übersetzbar sind, auch nicht
übersetzt werden. Dies ermöglicht es beispielsweise lediglich die Namen und
Beschreibungstexte von Produkten übersetzbar zu machen, die EAN und Massangaben
jedoch nicht. Diese Arbeitsweise verringert enorm die Redundanz der einzugebenden
Daten.

Filter
------

MetaModels verwenden ein vollkommen neuartiges und einzigartiges Filterkonzept.
Der Administrator der Webseite kann die Filterinteraktionen vollkommen frei an
seine Bedürfnisse anpassen. Dies gelingt durch die Konfiguration und Kombination
von Filtereinstellungen und deren Parametern.

MetaModels legt keine Beschränkungen hinsichtlich der Kombination von
Filtern auf und beherrscht auch äußerst komplexe Filterszenarien. Dank der offenen
Struktur der API, können eigene Filter mit geringem Aufwand programmiert werden.

MetaModels wird mit sechs verschiedenen Filtereinstellungen ausgeliefert,
welche verwendet werden können um Frontent-Filter-Eingabefelder wie beispielsweise
Auswahlboxen, Bereichsfilter, Freitext-Suche usw. zu erzeugen. Kombiniert man
dieses Filter mit Filtereinstellungen, welche keine Eingabefelder erzeugen können,
mittels UND/ODER Bedingungen ermöglichen es Individuelle SQL Abfragen und andere
vordefinierte Filtereinstellungen äusserst komplexe, interaktive Filter zu definieren
jedoch ohne dass man auf die hochperformante Auswertung der Filterung verzichten muss.

Es versteht sich von selbst, dass Filtereinstellungen die Frontent-Filter-Eingabefelder
bereit stellen ähnlich einfach zu implementieren sind, wie diejenigen die dies nicht
tun, was die Lernkurve für Anpassungen an die eigenen Anforderungen flach hält.

Dynamische Ansichten
--------------------

Mittels der Ausgabeeinstellungen wurde in MetaModels das "partial"-Template Konzept von
Contao in einer erweiterten Form umgesetzt. Der Anwender kann jeglichen Aspekt
der Ansichten auf Attributsebene und Datensatzebene anpassen.

Etliche allgemeine Einstellungen können in der Backend-Konfiguration festgelegt
werden. Diese können jedoch auch überschrieben, feingranual angepasst oder gar gänzlich
ignoriert werden, indem man ein eigenes Template auf Attributsebene oder Datensatzebene festlegt.
Diese Ausgabeeinstellungen bieten den flexibelsten Weg 'Daten-Views' zu definieren.

Der Designer kann für jeden Zweck eine komplett andere Ansicht definieren, sei es eine
simple Listenausgabe, einen Anreisser für die Startseite oder eine Detailansicht eines
Datensatzes, und ebenso wann und wo sie eingesetzt werden soll.

Die Ausgabe eines RSS-Feeds und andere Syndications-Formen sind in Planung und werden
das Konzept der Ausgabeeinstellungen erweitern.

Export/Import
-------------

Demnächst...

Front-End-Editing
-----------------

Demnächst...

Schnittstelle zu Online-Shop-Modul 'Isotope'
--------------------------------------------

Demnächst...