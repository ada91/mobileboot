Bootstrap Kurzvorstellung
==========

Agenda
------
<ol>
<li> Facts
<li> Geschichte
<li>Responsive Webdesign
	<ol>
		<li> Media Queries
		<li> Viewport 
		<li> Grid-System
	</ol>
<li> Komponenten
<li> Oekosystem
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
Um entsprechend auf die Bildschirmbreite der Ger�te reagieren zu k�nnen werden sogenannte Media Queries eingesetzt.   Diese kennen Medientypen und Medienmerkmalen. Treffen die entsprechenden abgefragten Medientypen, Merkmale oder eine Kombination aus beiden zu, so werden entsprechend spezielle CSS-Regeln angewandt. Die beiden meistverwendeten und unterst�tzten Medientypen sind screen und print. Daneben existieren noch Sonderformate wie beispielsweise die f�r einen Barrierefreien Zugang, darunter: aural (f�r die maschinelle Sprachausgabe), braille (Tastbare wiedergabe in der Blindenschrift ), embossed (Drucker die Blindenschrift auf Papier pr�gen). 

Der Einsatz der Media Queries zum Aufrufen verschiedener Style-Sheets kann an unterschiedlichen Stellen geschehen:

* Einbinden unterschiedlicher Styledateien f�r unterschiedliche Medientypen: 
	"<link rel="stylesheet" href="bildschirm-stylesheet.css" media="screen">
	<link rel="stylesheet" href="druck-stylesheet.css" media="print">"(selfhtml: CSS/Media Queries, 2014)
* Einbinden einer allgemeinen Styledatei und �berschreiben durch Laden eine dedizierten Styledatei f�r einen speziellen Medientyp. 
	"<link rel="stylesheet" href="stylesheet.css">
	<link rel="stylesheet" href="druck-stylesheet.css" media="print">"(selfhtml: CSS/Media Queries, 2014)
* Alle CSS-Regeln werden in einem Stylesheet untergebracht.
	"/* CSS-Regeln f�r alle Ausgabeger�te */
	@media print {
	/* zus�tzliche CSS-Regeln f�r Drucker */"(selfhtml: CSS/Media Queries, 2014)

Nachteile der unterschiedlichen Varianten: In Variante eins kommen vermutlich in beiden Dateien zum Teil redundante Regeln vor, zudem m�ssen beide Dateien geladen werden. 
Im zweiten Beispiel wird die Redundanzen vermieden, jedoch m�ssen auch hier beide Dateien vom Endger�t geladen werden. 

ii. Viewport
------------

iii. Grid-System
----------------

6. Quellenverzeichnis
---------------------
Jendryschik, Michael [2010]: Allen recht, in: iX (2010) heise.de/-1058764 (15.05.2014)

Otto, Mark [2012]: Building Twitter Bootstrap, 2012, alistapart.com/article/building-twitter-bootstrap (16.05.2013)

selfhtml [2014]: CSS/Media Queries, 2014, http://wiki.selfhtml.org/wiki/CSS/Media_Queries (04.02.2014, 15.05.2014)

w3schools [NAN]: CSS How To�, NAN, www.w3schools.com/css/css_howto.asp

bootstrap [2014]: CSS : Global CSS settings, fundamental HTML elements styled and enhanced with extensible classes, and an advanced grid system., 2014, http://holdirbootstrap.de/css/ (18.05.2014)



