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
<li> Das Bootstrap-�kosystem
<li> Quellenverzeichnis
</ol>



1. Facts
--------
Bootstrap ist ein auf HTML und CSS basierendes Framework zur Frontend Entwicklung von Webanwendungen. 
F�r die Generierung der CSS-Stylesheets nutzt Bootstrap LESS �- eine Sprache die CSS erweitert und durch einen Compiler in CSS-Code �bersetzt wird. 
Das Framework wurde auf Github ver�ffentlicht und steht unter der  Apache License 2.0 und ab Version 3.1.0 unter der MIT Lizenz zur Verf�gung. 
Der Grundgedanke hinter Bootstrap ist es das Design und die Entwicklung besser zu verkn�pfen: �pairing designers with developers�(Otto, M.: Building Twitter Bootstrap, 2012)


2. Geschichte
-------------
Bootstrap entstand aus einem internen Projekt bei Twitter. 
Ziel des Projektes war es, einen einheitlichen Standard f�r die Frontend Entwicklung zur Verf�gung zu stellen. 
Bis dato nutzten die Entwickler die Bibliotheken mit welchen Sie vertraut waren, um das Frontend der Anwendungen umzusetzen. 
Dies f�hrte zu einer starken Inkonsistenz innerhalb der Frontend Entwicklung bei Twitter.
Dadurch waren keine ausreichend schnellen Entwicklungszyklen und zufridenstellende optische Gestaltung m�glich.  
W�hrend des Entwicklungsprozesses wurden die entwickelten Gestaltungselemente genau auf ihre Usability und Umsetzung gepr�ft und optimiert. 
Der Entwicklungsprozess von Bootstrap kann in folgenden Schritten beschrieben werden: 

�ideation, debate and feature review, implementation, and lastly abstraction and documentation� (Otto, M.: Building Twitter Bootstrap, 2012)

Nach einigen Wochen wurde klar das aus Bootstrap nicht nur eine einzelnes Projekt werden sollte. 
Man blickte weiter in die Zukunft und wollte etwas umfassenderes Schaffen. 
So erkannte man, dass man aus Bootstrap eine Art lebenden Styleguide entwickeln konnte, der f�r nahezu jedes Projekt in dem Bereich geeignet war, auch au�erhalb von Twitter. 
Der erste Einsatz auf der Twitter-internen Hackweek best�tigte die N�tzlichkeit eines Tools das einen kompletten und schnell anzuwendenden Styleguid f�r die Entwickler zur Verf�gung stellt, ohne einen dedizierten Designer zu ben�tigen. 
Nach der Hackweek wurde das Projekt auch der �ffentlichkeit �ber GitHub zug�nglich gemacht. Hier�ber werden st�ndig neue Versionen ver�ffentlicht. 
Mit der Version 2 wurden optional Optimierungen f�r Mobilger�te erg�nzt. 
Die Version 3 wurde von Grund auf �berarbeitet, um anstatt lediglich mobile Styles zu erg�nzen, diese direkt im Kern des Layouts, von Anfang an, zu ber�cksichtigen. 
Kernst�ck der Unterst�tzung mobiler Ger�te stellt das responsive Design dar.  

3. Responsive Webdesign
------------------------

Die sich mit Anbahnung des Internet of Things immer weiter diversifizierende Systemlandschaft stellt eine zunehmende Herausforderung f�r die Entwickler von Webinhalten dar. 
Die Ger�te weisen stark unterschiedliche Eigenschaft ihrer Displaygr��e, -aufl�sung und Bedienbarkeit auf.  
Um eine Webanwendung f�r alle Ger�te bzw. deren User komfortabel nutzbar zu machen, muss sich das Seitendesign an die Gegebenheiten auf dem jeweiligen Ger�t anpassen. 

Dies macht aber noch keine responsive Website aus. 
Denn durch entsprechende Abfrage des User-Agents im http-Header k�nnen einfach entsprechen unterschiedlich hinterlegte Designtemplates je nach Ger�t Anwendung finden � also einfach auf eine mobile Version weitergeleitet werden. 
Das responsive Webdesign hingegen setzt nicht auf unterschiedliche Websiten um sich an die Ger�te anzupassen. 
Es wird lediglich eine Website erstellt, welche sich durch �nderung des zur Verf�gung stehenden Raumes automatisch daran anpasst.

Um dies umzusetzen m�ssen Displaygr��e und �hnliche Parameter wie beispielsweise zur Verf�gung stehende Eingabeger�te abgefragt und entsprechend darauf reagiert werden.

i. Media Queries
----------------
Um entsprechend auf die Bildschirmbreite der Ger�te reagieren zu k�nnen werden sogenannte Media Queries eingesetzt. Diese kennen Medientypen und Medienmerkmalen. 
Treffen die entsprechenden abgefragten Medientypen, Merkmale oder eine Kombination aus beiden zu, so werden entsprechend spezielle CSS-Regeln angewandt. 

Die beiden meistverwendeten und unterst�tzten <b>Medientypen</b> sind screen und print. 
Daneben existieren noch Sonderformate wie beispielsweise die f�r einen Barrierefreien Zugang, darunter: aural (f�r die maschinelle Sprachausgabe), 
braille (Tastbare wiedergabe in der Blindenschrift ), embossed (Drucker die Blindenschrift auf Papier pr�gen). 

Die wichtigsten <b>Medienmerkmale</b> sind: 

* width/height: H�he oder Breite des Anzeigebreichs bzw. der Seite (bei paginierter Ausgabe.) 
* device- width/device-height: Die Maximale Breite bzw. H�he des Ger�tedisplays.
* orientation: Es existieren die Werte portrait oder landscape.
* aspect-ratio: Seitenverh�ltnis des Darstellungsbereichs.
* device-aspect-ratio: Seitenverh�ltnis des Ger�tes.
* color: Anzahl der Farbtiefe in Bit pro Kanal (RGB).
* color-index: Beschreibt die Anzahl an Eintr�gen der darstellbaren Farben in einer Farbindextabelle auf dem Ger�t. (Falls Indextabelle vorhanden sonst 0)
* monochrome: Beschreibt die Tiefe in Bit in der Graustufen auf einem schwarz/wei� Ger�t dargestellt werden k�nnen. (Bei Farbger�ten = 0). 
* resolution: Fragt die Pixeldichte ab.  


Die Merkmale k�nnen zum Teil durch min- und max- Bedingungen erg�nzt werden. 
Medienmerkmale k�nnen untereinander sowie mit Medientypen durch den Operatur and verkn�pft werden.

Der Einsatz der Media Queries zum Aufrufen verschiedener Style-Sheets kann an unterschiedlichen Stellen geschehen:

* Einbinden unterschiedlicher Styledateien f�r unterschiedliche Medientypen: 

	```HTML
	<link rel="stylesheet" href="bildschirm-stylesheet.css" media="screen">
	<link rel="stylesheet" href="druck-stylesheet.css" media="print">  
	``` 
	(selfhtml: CSS/Media Queries, 2014)
	
* Einbinden einer allgemeinen Styledatei und �berschreiben durch Laden eine dedizierten Styledatei f�r einen speziellen Medientyp: 

	```HTML
	<link rel="stylesheet" href="stylesheet.css">
	<link rel="stylesheet" href="druck-stylesheet.css" media="print"> 
	``` 
	(selfhtml: CSS/Media Queries, 2014)
	
* Alle CSS-Regeln werden in einem Stylesheet untergebracht:

	```CSS
	/* CSS-Regeln f�r alle Ausgabeger�te */
	@media only screen and (min-width: 775px) and (max-width: 1000px) {
	/* CSS Regeln f�r die Ausgabe auf Bildschirmen welche eine Gr��e zwischen 775 und 1000 Pixeln aufweisen. */}
	```
	
Nachteile der unterschiedlichen Varianten: In Variante eins kommen vermutlich in beiden Dateien zum Teil redundante Regeln vor, zudem m�ssen beide Dateien geladen werden. 
Im zweiten Beispiel wird die Redundanzen vermieden, jedoch m�ssen auch hier beide Dateien vom Endger�t geladen werden. 

Bei Bootstrap erfolgt die Media-Abfrage in der CSS-Datei, welche sp�ter eingebunden wird. 

```CSS
	@media (min-width: @screen-sm-min) { /* CSS-Regeln f�r die Ger�te der Kategorie sm */ }
```
	
Auf Basis von Less werden an dieser Stelle Variablen f�r die Pixelbreite der einzelnen Klassen (Auf welche nachfolgend noch eingegangen wird) eingesetzt. F�r jede Klasse existiert eine eigene Media Queries.  


ii. Viewport
------------
Um ein korrekte Darstellung der responsiven Seite auf mobilen Ger�ten sicherzustellen, sollte in der HTML Datei im <head>  
Folgendes angegeben werden: 

	<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">

Dies sorgt daf�r, dass sich die Seite beim �ffnen auch wirklich an die Breite des Ger�tebildschirms anpasst. 
Denn die mobilen Ger�te versuchen beim �ffnen die Seiten in voller Breite anzuzeigen. 
Hierzu setzen die meisten mobilen Browser ihren Viewport auf eine Breite von 980px, in welcher sie die Seite rendern. 
Daraufhin skalieren sie die Seite so, dass sie komplett auf dem Ger�t angezeigt wird. 
Dies dient dazu dem Nutzer eine �bersicht, f�r Seiten welche nicht f�r Mobilger�te optimiert sind, zu verschaffen. 
Die responsive Website soll sich allerdings an das Ger�t anpassen. Hierzu dient das Viewport Tag, welches die Breite des Inhaltes auf die vom Ger�t zur�ckgegebene Breite setzt. 
Die Ger�tebreite die vom Browser zur�ckgegeben wird, entspricht meist nicht der tats�chlichen physikalischen Pixelanzahl. 
Dies ist auch sinnvoll, denn die Pixeldichte auf mobilen Ger�ten steigt immer weiter. 
So w�rde ein aktuelles Smartphone wie das Sony Xperia Z1 mit eine Aufl�sung von 1920 � 1080 Pixeln in die Bootstrap Kategorie �Mittelgro�e Ger�te/Desktops� fallen. 
Der Entwickler einer responsive Website m�chte aber nat�rlich ein 5� Ger�t mit dem Layout f�r Smartphones ansprechen. 
Daher gibt das Ger�t einen Viewport von 360x598 zur�ck. 
Eine Sammlung welcher mobilen Enger�te welchen Viewport angeben bietet die Seite: 
http://viewportsizes.com



iii. Grid-System
----------------
Bootstrap nutzt ein Grid-System, also eine Kombination aus Zeilen und Spalten um das Seitenlayout zu erzeugen und den Inhalt zu strukturieren. 
Dies wird insbesondere auch sp�ter f�r das responsive Verhalten wichtig. 
Per Default (Die Less-Variable: @grid-columns:     12;)besteht dieses Grid bei Bootstrap aus 12 Spalten. 
Diese sind mehr als gedankliche Spalten aufzufassen. Durch <div class=�row�> <\div> wird eine Zeile erzeugt. 
Diese Zeile ist nun per Default (kann auch ge�ndert werden) in 12 Spalten aufgeteilt. 
Durch <div class=�col-md-1�>Hier steht Inhalt </div> 
wird ein Feld f�r Inhalt in der Zeile erzeugt, das genau eine Spalte breit ist.
Soll das Feld breiter sein so wird die Zahl erh�ht.  
<div class=�col-md-5�>Dieses Feld ist 5/12 breit.</div>.
M�chte man einen Abstand zwischen zwei Inhaltsfelder erzeugen so wird zus�tzlich ein Offset angegeben col-md-offset-3. Dieser erzeugt immer links des div-Elements einen Abstand �ber die entsprechend angegebene Anzahl von Zeilen. 
Siehe hierzu die Tabelle der Ger�teklassen unter: http://getbootstrap.com/css/#grid-options

Die Ger�teklass legt auch den sogenannten Breaking-Point fest, ab welcher die Spalten untereinander angeordnet werden. Dies geschieht wenn die angegebene minimale Breite der Klasse unterschritten wird. Existiert dann keine kleinere Klasse werden die Spalten untereinander �ber die gesamte Breite der Zeile angeordnet. 
Durch die Ger�teklassen k�nnen auch unterschiedliche Spaltenaufteilungen f�r unterschiedliche Ger�te (Viewportbreiten) definiert werden. 
F�r ein Beispiel mit unterschiedlichen Spalteneinteilungen f�r unterschiedliche Ger�teklassen siehe: 
http://ada91.github.io/mobileboot/#/step-15. 
Auf den fortfolgenden Seiten, im angegebenen Link, ist dargestellt wie sich das im Beispiel definierte Grid bei unterschiedlichen zur Verf�gung stehenden Breiten verh�lt. 


4. Entwickeln mit Bootstrap
---------------------------
In diesem Abschnitt wird erl�utert, wie man mit dem Bootstrap-Framework entwickeln kann. 

Dazu m�ssen zun�chst die erforderlichen Dateien heruntergeladen werden. Folgender [Link][download] f�hrt dabei zu der entsprechenden Website:

  [download]: http://getbootstrap.com/getting-started/#download  "Download von Bootstrap"
  
Hierbei kann zwischen verschiedenen Versionen der Dateien ausgew�hlt werden:
<ol>
<li> CSS, JavaScript und Schrifttypen in bereits kompilierter und komprimierter Version</li>
<li> Less, JavaSript und Schrifttypen als Quelldateien</li>
<li> Von Less nach Sass portiertiertes Framework</li>
</ol>
Version zwei verlangt dabei dass ein Less-Compiler eingerichtet ist, liefert jedoch auch die Bootstrap-Dokumentation mit.
Version drei eignet sich f�r das Einbinden von Bootstrap in Rails, Compass oder Sass-only Projekte. 
Nachfolgend wird Version eins verwendet.

Die entsprechenden Dateien m�ssen im Anschluss im Header des HTML-Dokumentes �ber das Script- bzw. das Link-Tag eingebunden werden.

Alternativ zum Download der Bootstrap-Dateien kann das Content Delivery Network (CDN) [MaxCDN][max] verwendet werden.
[max]:http://www.bootstrapcdn.com/

Dazu m�ssen statt den Verweisen auf die heruntergeladenen Dateien die entsprechenden Links von MaxCDN angegeben werden.

	<!-- Aktuellstes kompiliertes und minimiertes CSS -->
	<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
	
	<!-- Optional: Thema -->
	<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap-theme.min.css">
	
	<!-- Aktuellstes kompiliertes und minimiertes JavaScript -->
	<script src="//netdna.bootstrapcdn.com/bootstrap/3.1.1/js/bootstrap.min.js"></script>

Eine weitere M�glichkeit zur "Installation" von Bootstrap ist die Verwendung des Packet-Managers [Bower][bow].
[bow]:https://github.com/bower/bower

	$ bower install bootstrap

Au�erdem muss das Framework [JQuery][jq] in das Projekt eingebunden werden. Hierzu k�nnen die entsprechenden Dateien wiederum entweder heruntergeladen oder �ber ein CDN eingebunden werden.
[jq]:http://jquery.com/

Nachdem alle notwendigen Dateien heruntergeladen sind, kann die Programmierung einer Website mit Bootstrap vorgenommen werden. Das Grundger�st sieht dabei wie folgt aus:

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
	
	    <!-- jQuery (notwendig f�r die Bootstrap JavaScript-Plugins) -->
	    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>
	    <!-- Einbinden aller Bootstrap-Plugins -->
	    <script src="js/bootstrap.min.js"></script>
	  </body>
	</html>

Nachdem das Grundger�st innerhalb der HTML-Seite erstellt ist, k�nnen nun die durch Bootstrap bereitgestellten Elemente und JavaScript-Plugins innerhalb des oben vorgestellten responsiven Designs verwendet werden.
Weitere Informationen finden sich auf http://getbootstrap.com.

5. Das Bootstrap-�kosystem
--------------------------
Neben dem eigentlichen Bootstrap-Framework haben sich viele Projekte entwickelt, die f�r die Entwicklung genutzt werden k�nnen, um einfacher Websites mit Bootstrap zu erstellen.
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

w3schools [NAN]: CSS How To�, NAN, www.w3schools.com/css/css_howto.asp

bootstrap [2014]: CSS : Global CSS settings, fundamental HTML elements styled and enhanced with extensible classes, and an advanced grid system., 2014, http://holdirbootstrap.de/css/ (18.05.2014)



