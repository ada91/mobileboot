Bootstrap Kurzvorstellung
==========

Agenda
------
<ol>
<li> Facts
<li> Geschichte
<li> Responsive Webdesign
	<ol>
		<li> Media Queries
		<li> Viewport 
		<li> Grid-System
	</ol>
<li> Entwickeln mit Bootstrap
<li> Das Bootstrap-Ökosystem
<li> Quellenverzeichnis
</ol>



1. Facts
--------
Bootstrap ist ein auf HTML und CSS basierendes Framework zur Frontend Entwicklung von Webanwendungen. 
Für die Generierung der CSS-Stylesheets nutzt Bootstrap LESS –- eine Sprache die CSS erweitert und durch einen Compiler in CSS-Code übersetzt wird. 
Das Framework wurde auf Github veröffentlicht und steht unter der  Apache License 2.0 und ab Version 3.1.0 unter der MIT Lizenz zur Verfügung. 
Der Grundgedanke hinter Bootstrap ist es das Design und die Entwicklung besser zu verknüpfen: „pairing designers with developers“(Otto, M.: Building Twitter Bootstrap, 2012)


2. Geschichte
-------------
Bootstrap entstand aus einem internen Projekt bei Twitter. 
Ziel des Projektes war es, einen einheitlichen Standard für die Frontend Entwicklung zur Verfügung zu stellen. 
Bis dato nutzten die Entwickler die Bibliotheken mit welchen Sie vertraut waren, um das Frontend der Anwendungen umzusetzen. 
Dies führte zu einer starken Inkonsistenz innerhalb der Frontend Entwicklung bei Twitter.
Dadurch waren keine ausreichend schnellen Entwicklungszyklen und zufridenstellende optische Gestaltung möglich.  
Während des Entwicklungsprozesses wurden die entwickelten Gestaltungselemente genau auf ihre Usability und Umsetzung geprüft und optimiert. 
Der Entwicklungsprozess von Bootstrap kann in folgenden Schritten beschrieben werden: 

„ideation, debate and feature review, implementation, and lastly abstraction and documentation“ (Otto, M.: Building Twitter Bootstrap, 2012)

Nach einigen Wochen wurde klar das aus Bootstrap nicht nur eine einzelnes Projekt werden sollte. 
Man blickte weiter in die Zukunft und wollte etwas umfassenderes Schaffen. 
So erkannte man, dass man aus Bootstrap eine Art lebenden Styleguide entwickeln konnte, der für nahezu jedes Projekt in dem Bereich geeignet war, auch außerhalb von Twitter. 
Der erste Einsatz auf der Twitter-internen Hackweek bestätigte die Nützlichkeit eines Tools das einen kompletten und schnell anzuwendenden Styleguid für die Entwickler zur Verfügung stellt, ohne einen dedizierten Designer zu benötigen. 
Nach der Hackweek wurde das Projekt auch der Öffentlichkeit über GitHub zugänglich gemacht. Hierüber werden ständig neue Versionen veröffentlicht. 
Mit der Version 2 wurden optional Optimierungen für Mobilgeräte ergänzt. 
Die Version 3 wurde von Grund auf überarbeitet, um anstatt lediglich mobile Styles zu ergänzen, diese direkt im Kern des Layouts, von Anfang an, zu berücksichtigen. 
Kernstück der Unterstützung mobiler Geräte stellt das responsive Design dar.  

3. Responsive Webdesign
------------------------

Die sich mit Anbahnung des Internet of Things immer weiter diversifizierende Systemlandschaft stellt eine zunehmende Herausforderung für die Entwickler von Webinhalten dar. 
Die Geräte weisen stark unterschiedliche Eigenschaft ihrer Displaygröße, -auflösung und Bedienbarkeit auf.  
Um eine Webanwendung für alle Geräte bzw. deren User komfortabel nutzbar zu machen, muss sich das Seitendesign an die Gegebenheiten auf dem jeweiligen Gerät anpassen. 

Dies macht aber noch keine responsive Website aus. 
Denn durch entsprechende Abfrage des User-Agents im http-Header können einfach entsprechen unterschiedlich hinterlegte Designtemplates je nach Gerät Anwendung finden – also einfach auf eine mobile Version weitergeleitet werden. 
Das responsive Webdesign hingegen setzt nicht auf unterschiedliche Websiten um sich an die Geräte anzupassen. 
Es wird lediglich eine Website erstellt, welche sich durch Änderung des zur Verfügung stehenden Raumes automatisch daran anpasst.

Um dies umzusetzen müssen Displaygröße und ähnliche Parameter wie beispielsweise zur Verfügung stehende Eingabegeräte abgefragt und entsprechend darauf reagiert werden.

i. Media Queries
----------------
Um entsprechend auf die Bildschirmbreite der Geräte reagieren zu können werden sogenannte Media Queries eingesetzt. Diese kennen Medientypen und Medienmerkmalen. 
Treffen die entsprechenden abgefragten Medientypen, Merkmale oder eine Kombination aus beiden zu, so werden entsprechend spezielle CSS-Regeln angewandt. 

Die beiden meistverwendeten und unterstützten <b>Medientypen</b> sind screen und print. 
Daneben existieren noch Sonderformate wie beispielsweise die für einen Barrierefreien Zugang, darunter: aural (für die maschinelle Sprachausgabe), 
braille (Tastbare wiedergabe in der Blindenschrift ), embossed (Drucker die Blindenschrift auf Papier prägen). 

Die wichtigsten <b>Medienmerkmale</b> sind: 

* width/height: Höhe oder Breite des Anzeigebreichs bzw. der Seite (bei paginierter Ausgabe.) 
* device- width/device-height: Die Maximale Breite bzw. Höhe des Gerätedisplays.
* orientation: Es existieren die Werte portrait oder landscape.
* aspect-ratio: Seitenverhältnis des Darstellungsbereichs.
* device-aspect-ratio: Seitenverhältnis des Gerätes.
* color: Anzahl der Farbtiefe in Bit pro Kanal (RGB).
* color-index: Beschreibt die Anzahl an Einträgen der darstellbaren Farben in einer Farbindextabelle auf dem Gerät. (Falls Indextabelle vorhanden sonst 0)
* monochrome: Beschreibt die Tiefe in Bit in der Graustufen auf einem schwarz/weiß Gerät dargestellt werden können. (Bei Farbgeräten = 0). 
* resolution: Fragt die Pixeldichte ab.  


Die Merkmale können zum Teil durch min- und max- Bedingungen ergänzt werden. 
Medienmerkmale können untereinander sowie mit Medientypen durch den Operatur and verknüpft werden.

Der Einsatz der Media Queries zum Aufrufen verschiedener Style-Sheets kann an unterschiedlichen Stellen geschehen:

* Einbinden unterschiedlicher Styledateien für unterschiedliche Medientypen: 

	```HTML
	<link rel="stylesheet" href="bildschirm-stylesheet.css" media="screen">
	<link rel="stylesheet" href="druck-stylesheet.css" media="print">  
	``` 
	(selfhtml: CSS/Media Queries, 2014)
	
* Einbinden einer allgemeinen Styledatei und Überschreiben durch Laden eine dedizierten Styledatei für einen speziellen Medientyp: 

	```HTML
	<link rel="stylesheet" href="stylesheet.css">
	<link rel="stylesheet" href="druck-stylesheet.css" media="print"> 
	``` 
	(selfhtml: CSS/Media Queries, 2014)
	
* Alle CSS-Regeln werden in einem Stylesheet untergebracht:

	```CSS
	/* CSS-Regeln für alle Ausgabegeräte */
	@media only screen and (min-width: 775px) and (max-width: 1000px) {
	/* CSS Regeln für die Ausgabe auf Bildschirmen welche eine Größe zwischen 775 und 1000 Pixeln aufweisen. */}
	```
	
Nachteile der unterschiedlichen Varianten: In Variante eins kommen vermutlich in beiden Dateien zum Teil redundante Regeln vor, zudem müssen beide Dateien geladen werden. 
Im zweiten Beispiel wird die Redundanzen vermieden, jedoch müssen auch hier beide Dateien vom Endgerät geladen werden. 

Bei Bootstrap erfolgt die Media-Abfrage in der CSS-Datei, welche später eingebunden wird. 

```CSS
	@media (min-width: @screen-sm-min) { /* CSS-Regeln für die Geräte der Kategorie sm */ }
```
	
Auf Basis von Less werden an dieser Stelle Variablen für die Pixelbreite der einzelnen Klassen (Auf welche nachfolgend noch eingegangen wird) eingesetzt. Für jede Klasse existiert eine eigene Media Queries.  


ii. Viewport
------------
Um ein korrekte Darstellung der responsiven Seite auf mobilen Geräten sicherzustellen, sollte in der HTML Datei im <head>  
Folgendes angegeben werden: 

	<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">

Dies sorgt dafür, dass sich die Seite beim Öffnen auch wirklich an die Breite des Gerätebildschirms anpasst. 
Denn die mobilen Geräte versuchen beim Öffnen die Seiten in voller Breite anzuzeigen. 
Hierzu setzen die meisten mobilen Browser ihren Viewport auf eine Breite von 980px, in welcher sie die Seite rendern. 
Daraufhin skalieren sie die Seite so, dass sie komplett auf dem Gerät angezeigt wird. 
Dies dient dazu dem Nutzer eine Übersicht, für Seiten welche nicht für Mobilgeräte optimiert sind, zu verschaffen. 
Die responsive Website soll sich allerdings an das Gerät anpassen. Hierzu dient das Viewport Tag, welches die Breite des Inhaltes auf die vom Gerät zurückgegebene Breite setzt. 
Die Gerätebreite die vom Browser zurückgegeben wird, entspricht meist nicht der tatsächlichen physikalischen Pixelanzahl. 
Dies ist auch sinnvoll, denn die Pixeldichte auf mobilen Geräten steigt immer weiter. 
So würde ein aktuelles Smartphone wie das Sony Xperia Z1 mit eine Auflösung von 1920 × 1080 Pixeln in die Bootstrap Kategorie „Mittelgroße Geräte/Desktops“ fallen. 
Der Entwickler einer responsive Website möchte aber natürlich ein 5“ Gerät mit dem Layout für Smartphones ansprechen. 
Daher gibt das Gerät einen Viewport von 360x598 zurück. 
Eine Sammlung welcher mobilen Engeräte welchen Viewport angeben bietet die Seite: 
http://viewportsizes.com



iii. Grid-System
----------------
Bootstrap nutzt ein Grid-System, also eine Kombination aus Zeilen und Spalten um das Seitenlayout zu erzeugen und den Inhalt zu strukturieren. 
Dies wird insbesondere auch später für das responsive Verhalten wichtig. 
Per Default (Die Less-Variable: @grid-columns:     12;)besteht dieses Grid bei Bootstrap aus 12 Spalten. 
Diese sind mehr als gedankliche Spalten aufzufassen. Durch <div class=“row“> <\div> wird eine Zeile erzeugt. 
Diese Zeile ist nun per Default (kann auch geändert werden) in 12 Spalten aufgeteilt. 
Durch <div class=“col-md-1“>Hier steht Inhalt </div> 
wird ein Feld für Inhalt in der Zeile erzeugt, das genau eine Spalte breit ist.
Soll das Feld breiter sein so wird die Zahl erhöht.  
<div class=“col-md-5“>Dieses Feld ist 5/12 breit.</div>.
Möchte man einen Abstand zwischen zwei Inhaltsfelder erzeugen so wird zusätzlich ein Offset angegeben col-md-offset-3. Dieser erzeugt immer links des div-Elements einen Abstand über die entsprechend angegebene Anzahl von Zeilen. 
Siehe hierzu die Tabelle der Geräteklassen unter: http://getbootstrap.com/css/#grid-options

Die Geräteklass legt auch den sogenannten Breaking-Point fest, ab welcher die Spalten untereinander angeordnet werden. Dies geschieht wenn die angegebene minimale Breite der Klasse unterschritten wird. Existiert dann keine kleinere Klasse werden die Spalten untereinander über die gesamte Breite der Zeile angeordnet. 
Durch die Geräteklassen können auch unterschiedliche Spaltenaufteilungen für unterschiedliche Geräte (Viewportbreiten) definiert werden. 
Für ein Beispiel mit unterschiedlichen Spalteneinteilungen für unterschiedliche Geräteklassen siehe: 
http://ada91.github.io/mobileboot/#/step-15. 
Auf den fortfolgenden Seiten, im angegebenen Link, ist dargestellt wie sich das im Beispiel definierte Grid bei unterschiedlichen zur Verfügung stehenden Breiten verhält. 


4. Entwickeln mit Bootstrap
---------------------------
In diesem Abschnitt wird erläutert, wie man mit dem Bootstrap-Framework entwickeln kann. 

Dazu müssen zunächst die erforderlichen Dateien heruntergeladen werden. Folgender [Link][download] führt dabei zu der entsprechenden Website:

  [download]: http://getbootstrap.com/getting-started/#download  "Download von Bootstrap"
  
Hierbei kann zwischen verschiedenen Versionen der Dateien ausgewählt werden:
<ol>
<li> CSS, JavaScript und Schrifttypen in bereits kompilierter und komprimierter Version</li>
<li> Less, JavaSript und Schrifttypen als Quelldateien</li>
<li> Von Less nach Sass portiertiertes Framework</li>
</ol>
Version zwei verlangt dabei dass ein Less-Compiler eingerichtet ist, liefert jedoch auch die Bootstrap-Dokumentation mit.
Version drei eignet sich für das Einbinden von Bootstrap in Rails, Compass oder Sass-only Projekte. 
Nachfolgend wird Version eins verwendet.

Die entsprechenden Dateien müssen im Anschluss im Header des HTML-Dokumentes über das Script- bzw. das Link-Tag eingebunden werden.

Alternativ zum Download der Bootstrap-Dateien kann das Content Delivery Network (CDN) [MaxCDN][max] verwendet werden.
[max]:http://www.bootstrapcdn.com/

Dazu müssen statt den Verweisen auf die heruntergeladenen Dateien die entsprechenden Links von MaxCDN angegeben werden.

	<!-- Aktuellstes kompiliertes und minimiertes CSS -->
	<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
	
	<!-- Optional: Thema -->
	<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap-theme.min.css">
	
	<!-- Aktuellstes kompiliertes und minimiertes JavaScript -->
	<script src="//netdna.bootstrapcdn.com/bootstrap/3.1.1/js/bootstrap.min.js"></script>

Eine weitere Möglichkeit zur "Installation" von Bootstrap ist die Verwendung des Packet-Managers [Bower][bow].
[bow]:https://github.com/bower/bower

	$ bower install bootstrap

Außerdem muss das Framework [JQuery][jq] in das Projekt eingebunden werden. Hierzu können die entsprechenden Dateien wiederum entweder heruntergeladen oder über ein CDN eingebunden werden.
[jq]:http://jquery.com/

Nachdem alle notwendigen Dateien heruntergeladen sind, kann die Programmierung einer Website mit Bootstrap vorgenommen werden. Das Grundgerüst sieht dabei wie folgt aus:

	<!DOCTYPE html>
	<html lang="en">
	  <head>
	    <meta charset="utf-8">
	    <meta http-equiv="X-UA-Compatible" content="IE=edge">
	    <meta name="viewport" content="width=device-width, initial-scale=1">
	    <title>Bootstrap</title>
	
	    <!-- Bootstrap CSS: Hier den richtigen Pfad bzw. eine CDN-Referenz angeben -->
	    <link href="css/bootstrap.min.css" rel="stylesheet">
	
	  </head>
	  <body>
	    <h1>Hello, world!</h1>
	
	    <!-- jQuery (notwendig für die Bootstrap JavaScript-Plugins) -->
	    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>
	    <!-- Einbinden aller Bootstrap-Plugins -->
	    <script src="js/bootstrap.min.js"></script>
	  </body>
	</html>

Nachdem das Grundgerüst innerhalb der HTML-Seite erstellt ist, können nun die durch Bootstrap bereitgestellten Elemente und JavaScript-Plugins innerhalb des oben vorgestellten responsiven Designs verwendet werden.
Weitere Informationen finden sich auf http://getbootstrap.com.

5. Das Bootstrap-Ökosystem
--------------------------
Neben dem eigentlichen Bootstrap-Framework haben sich viele Projekte entwickelt, die für die Entwicklung genutzt werden können, um einfacher Websites mit Bootstrap zu erstellen.
Nachfolgend sind einige Beispiele aufgelistet:

Bootstrap Interface Builder
<ul>
<li>LayoutIt!(http://www.layoutit.com/)
<li>Jetstrap(https://jetstrap.com/)
<li>rapidmoon(http://www.rapidmoon.com/)
</ul>

Bootstrap Themes und Templates
<ul>
<li>{Wrap}bootstrap(https://wrapbootstrap.com/)
<li>Bootstrap Zero(http://bootstrapzero.com/)
<li>Start Bootstrap(http://startbootstrap.com/)
<li>Bootswatch(http://bootswatch.com/)
<li>Bootstrap Stage(http://www.bootstrapstage.com/)
</ul>
 
6. Quellenverzeichnis
---------------------
Jendryschik, Michael [2010]: Allen recht, in: iX (2010) http://heise.de/-1058764 (15.05.2014)

Otto, Mark [2012]: Building Twitter Bootstrap, 2012, http://alistapart.com/article/building-twitter-bootstrap (16.05.2013)

selfhtml [2014]: CSS/Media Queries, 2014, http://wiki.selfhtml.org/wiki/CSS/Media_Queries (04.02.2014, 15.05.2014)

w3schools [NAN]: CSS How To…, NAN, www.w3schools.com/css/css_howto.asp

bootstrap [2014]: CSS : Global CSS settings, fundamental HTML elements styled and enhanced with extensible classes, and an advanced grid system., 2014, http://holdirbootstrap.de/css/ (18.05.2014)



