      _____  _     _  _____  _______ _     _ _______ _______ _______           
 <   |_____] |_____| |_____] |  |  | |     | |______ |______ |______ |        >
     |       |     | |       |  |  | |_____| ______| ______| |______ |_____    

                            { ~ ~ ~ DEUTSCH ~ ~ ~ }                            
 Vielen Dank f�r die Benutzung von phpMussel, ein PHP-basiertes Script, welches
    die Signaturen von ClamAV nutzt, um Trojaner, Viren, Malware und andere    
                      Bedrohungen in Dateien zu entdecken,                     
                 die auf Ihr System hochgeladen werden k�nnten.                
     PHPMUSSEL COPYRIGHT 2013 and beyond GNU/GPL V.2 by Caleb M (Maikuolan)    

                                     ~ ~ ~                                     


 INHALT
 1. VORWORT
 2A. INSTALLATION (SERVER)
 2B. INSTALLATION (CLI)
 3A. BENUTZUNG (SERVER)
 3B. BENUTZUNG (CLI)
 4A. BROWSER BEFEHLE
 4B. CLI (COMMAND LINE INTERFACE)
 5. IM PAKET ENTHALTENE DATEIEN
 6. EINSTELLUNGEN
 7. SIGNATURENFORMAT
 8. BEKANNTE KOMPATIBILIT�TSPROBLEME

                                     ~ ~ ~                                     


 1. VORWORT

 Besonderer Dank geht an ClamAV f�r die Inspiration und die Signaturen, die    
 dieses Script benutzt, ohne die dieses Script wahrscheinlich nicht existieren 
 w�rde oder bestenfalls einen sehr begrenzten Wert h�tte.                      
 <http://www.clamav.net/lang/en/>                                              

                                     ~ ~ ~                                     
 Dieses Skript ist freie Software; Sie k�nnen sie weitergeben und/oder         
 modifizieren unter den Bedingungen der GNU General Public License, wie von der
 Free Software Foundation ver�ffentlicht; entweder unter Version 2 der Lizenz  
 oder (nach Ihrer Wahl) jeder sp�teren Version. Dieses Skript wird in der      
 Hoffnung verteilt, dass es n�tzlich sein wird, allerdings OHNE JEGLICHE       
 GARANTIE; ohne implizite Garantien f�r VERMARKTUNG/VERKAUF/VERTRIEB oder F�R  
 EINEN BESTIMMTEN ZWECK. Lesen Sie die GNU General Public License f�r weitere  
 Details. <http://www.gnu.org/licenses/> <http://opensource.org/licenses/>     

                                     ~ ~ ~                                     
 Dieses Dokument und das zugeh�rige Paket kann kostenlos von Sourceforge
 heruntergeladen werden. <http://sourceforge.net/projects/phpmussel/>

                                     ~ ~ ~                                     


 2A. INSTALLATION (SERVER)

 Zuf�nftig wird dieser Prozess mit einem Installationsmanager vereinfacht, bis
 dahin folgen Sie den Anweisungen, um phpMussel auf den *meisten Systemen und
 CMS zu installieren:

 1) Entpacken Sie das heruntergeladene Archiv auf Ihren lokalen PC. Erstellen
    Sie ein Verzeichnis, wohin Sie den Inhalt dieses Paketes auf Ihrem Host
    oder CMS installieren m�chten. Ein Verzeichnis wie /public_html/phpmussel/
    o.�. gen�gt, solange es Ihren Sicherheitsbed�rfnissen oder pers�nlichen
    Pr�ferenzen entspricht.

 2) �ffnen Sie die "phpmussel.php", suchen Sie die Zeile beginnend mit
    "$vault=" und ersetzen Sie den String zwischen den Anf�hrungszeichen mit
    dem exakten Pfad des "vault"-Verzeichnisses von phpMussel. Ein solches
    Verzeichnis werden Sie sicherlich im heruntergeladenen Archiv bemerkt haben
    (sollten Sie das Script recodieren wollen, so m�ssen Sie die Datei und
    Verzeichnisstruktur aus dem originalen Archiv beibehalten). Das
    "vault"-Verzeichnis sollte eine Ebene unterhalb des Verzeichnisses liegen,
    in dem sich die Datei "phpmussel.php" befindet. Speichern und schlie�en Sie
    die Datei.

 3) (Optional; Empfohlen f�r erfahrene Anwender, nicht empfohlen f�r Anwender
    ohne entsprechende Kenntnisse): �ffnen Sie die Datei "phpmussel.ini" im
    "vault"-Verzeichnis) - Diese Datei beinhaltet alle funktionalen Optionen
    f�r phpMussel. �ber jeder Option beschreibt ein kurzer Kommentar die
    Aufgabe dieser Option. Ver�ndern Sie die Werte nach Ihren Bed�rfnissen.
    Speichern und schlie�en Sie die Datei.

 4) Laden Sie den kompletten Inhalt (phpMussel und die Dateien) in das
    Verzeichnis hoch, f�r das Sie sich in Schritt 1 entschieden haben. Die
    Dateien readme.XX.txt oder change_log.txt m�ssen nicht mit hochgeladen
    werden.

 5) �ndern Sie die Zugriffsberechtigungen des "vault"-Verzeichnisses auf "777".
    Die Berechtigungen des �bergeordneten Verzeichnises, in welchem sich der
    Inhalt befindet (das Verzeichnis, wof�r Sie sich entschieden haben), k�nnen
    so belassen werden, �berpr�fen Sie jedoch die Berechtigungen, wenn in der
    Vergangenheit Zugriffsprobleme aufgetreten sind (Voreinstellung "755"
    o.�.).

 6) Binden Sie phpMussel in Ihr System oder CMS ein. Es gibt viele verschiedene
    M�glichkeiten, ein Script wie phpMussel einzubinden, am einfachsten ist es,
    das Script am Anfang einer Haupt-Datei (eine Datei, die immer geladen wird,
    wenn jemand irgend eine beliebige Seite Ihres Webauftritts aufruft) Ihres
    Systems oder CMS mit Hilfe des require- oder include-commands einzubinden.
    �blicherweise wird eine solche Datei in Verzeichnissen wie "/includes",
    "/assets" or "/functions" gespeichert und wird h�ufig "init.php",
    "common_functions.php", "functions.php" o.�. genannt. Sie m�ssen
    herausfinden, welche Datei dies f�r Ihre Bed�rfnisse ist. F�gen Sie in
    dieser Datei folgenden Code diret am Anfang ein:

    <?php require("/user_name/public_html/phpmussel/phpmussel.php"); ?>

    Ersetzen Sie den String zwischen den Anf�hrungszeichen mit dem lokalen Pfad
    der Datei "phpmussel.php", nicht mit der HTTP-Adresse (�hnlich dem Pfad f�r
    das "vault"-Verzeichnis). Speichern und schlie�en Sie die Datei, laden Sie
    sie ggf. erneut hoch.

 7) Der Installationsvorgang wurde nun fertiggestellt. Sie sollten nun das
    Programm auf ordnungsgem��e Funktion testen. Sie sollten nun die im Paket
    enthaltenen Testdateien "_testfiles" auf Ihre Webseite �ber die
    gew�hnlichen browserbasierten Methoden hochladen. Funktioniert das Programm
    ordnungsgem��, erscheint eine Meldung von phpMussel, dass der Upload
    erfolgreich blockiert wurde. Erscheint keine Meldung, funktioniert das
    Programm nicht korrekt. Nutzen Sie andere erweiterte Funktionen oder
    weitere m�gliche Arten von Scannern dieses Programms, so sollten Sie diese
    ebenfalls testen, um die ordnungsgem��e Funktion sicherzustellen.

                                     ~ ~ ~                                     


 2B. INSTALLATION (CLI)

 Zuf�nftig wird dieser Prozess mit einem Installationsmanager vereinfacht, bis
 dahin folgen Sie den Anweisungen, um phpMussel im CLI-Modus zu installieren
 (beachten Sie an dieser Stelle, CLI-Support ist nur auf Windows-Systemen
 m�glich, Linux und andere Systeme werden in zuk�nftigen Versionen
 unterst�tzt):

 1) Entpacken Sie das heruntergeladene Archiv auf Ihren lokalen PC in ein
    Verzeichnis, das Ihren Sicherheitsbed�rfnissen oder pers�nlichen
    Pr�ferenzen entspricht.

 2) phpMussel ben�tigt eine intallierte PHP-Umgebung, um ausgef�hrt werden zu
    k�nnen. Sofern PHP bei Ihnen nicht installiert ist, installieren Sie es
    bitte nach den Anweisungen des PHP-Installers.

 3) �ffnen Sie die "phpmussel.php", suchen Sie die Zeile beginnend mit
    "$vault=" und ersetzen SIe den String zwischen den Anf�hrungszeichen mit
    dem exakten Pfad des "vault"-Verzeichnisses von phpMussel. Ein solches
    Verzeichnis werden Sie sicherlich im heruntergeladenen Archiv bemerkt haben
    (sollten Sie das Script recodieren wollen, so m�ssen Sie die Datei- und
    Verzeichnisstruktur aus dem originalen Archiv beibehalten). Das
    "vault"-Verzeichnis sollte eine Ebene unterhalb des Verzeichnisses liegen,
    in dem sich die Datei "phpmussel.php" befindet. Speichern und schlie�en Sie
    die Datei.

 4) (Optional; Empfohlen f�r erfahrene Anwender, nicht empfohlen f�r Anwender
    ohne entsprechende Kenntnisse): �ffnen Sie die Datei "phpmussel.ini" im
    "vault"-Verzeichnis) - Diese Datei beinhaltet alle funktionalen Optionen
    f�r phpMussel. �ber jeder Option beschreibt ein kurzer Kommentar die
    Aufgabe dieser Option. Ver�ndern Sie die Werte nach Ihren Bed�rfnissen.
    Speichern und schlie�en Sie die Datei.

 5) (Optional) Sie k�nnen den Start von phpMussel vereinfachen, indem Sie
    mittels einer Stapelverarbeitungsdatei PHP und phpMussel automatisch laden.
    �ffnen Sie einen einfachen Texteditor wie Notepad oder Notepad++, tragen
    den vollst�ndigen Pfad zu Ihrer "php.exe" im Verzeichnis Ihrer
    PHP-Installation ein, gefolgt von einem Leerzeichen und dem vollst�ndigen
    Pfad zur "phpmussel.php" im Verzeichnis Ihrer phpMussel-Installation,
    speichern diese Datei mit einer ".bat"-Dateierweiterung an einem Ort, wo
    Sie sie leicht finden k�nnen und f�hren Sie sie zuk�nfig nur noch mit einem
    Doppelclick aus.

 6) Der Installationsvorgang wurde nun fertiggestellt. Sie sollten nun das
    Programm auf ordnungsgem��e Funktion testen. Um den Test durchzuf�hren,
    f�hren Sie bitte phpMussel aus, und scannen Sie das Verzeichnis
    "_testfiles" aus dem Archiv von phpMussel.

                                     ~ ~ ~                                     


 3A. BENUTZUNG (SERVER)

 phpMussel ist daf�r vorgesehen, fast vollst�ndig autonom zu funktionieren,
 ohne dass Sie etwas tun m�ssen: Sobald es installiert ist, f�hrt es die
 T�tigkeiten allein aus.

 Das Scannen von Dateiuploads ist automatisiert und standardm��ig
 eingeschaltet, Sie m�ssen nichts weiter unternehmen.

 Sie sind jedoch auch in der Lage, phpMussel anzuweisen, nach Dateien, Ordnern
 oder Archiven zu scannen, die Sie implizit angeben. Um dies auszuf�hren,
 stellen Sie sicher, dass diese Konfiguration in der phpmussel.ini festgelegt
 ist (Cleanup mu� deaktiviert sein).

 Erstellen Sie eine mit phpMussel eingebundene PHP-Datei mit folgender
 Funktion:

 phpMussel($what_to_scan,$output_type,$output_flatness);

 - $what_to_scan ist entweder ein String oder ein Array, welches auf eine
   Datei, ein Verzeichnis oder ein Array von Dateien und/oder Verzeichnissen
   zeigt.

 - $output_type ist eine Ganzzahl (Integer), gibt das Format an, wie das
   Ergebnis zur�ckgegeben werden soll. Ein Wert von 0 weist die Funktion an,
   das Ergebnis als Ganzzahl zur�ckzugeben (Integer; ein R�ckgabewert von -2
   zeigt an, dass besch�digte Dateien gefunden wurden und der Scan nicht
   abgeschlossen wurde, -1 zeigt an, dass fehlende Erweiterungen oder Addons
   von PHP ben�tigt werden, um den Scan durchzuf�hren und der Scan deshalb
   nicht abgeschlossen wurde, 0 zeigt an, dass das Ziel nicht existiert und
   somit nichts �berpr�ft werden konnte, 1 zeigt an, dass das Ziel erfolgreich
   gepr�ft wurde und keine Probleme erkannt wurden, 2 zeigt an, dass das Ziel
   erfolgreich gepr�ft wurde, jedoch Probleme gefunden wurden). Ein Wert von 1
   weist die Funktion an, die Ergebnisse als lesbaren Text auszugeben. Ein Wert
   von 2 weist die Funktion an, beides auszugeben, einen lesbaren Text und
   einen Export in eine globale Variable. Diese Variable ist optional,
   Standardeinstellung ist 0.

 - $output_flatness ist eine Ganzzahl (Integer), weist die Funktion an, das
   Ergebnis als Array oder String auszugeben. Enth�lt das Ziel mehrere Elemente
   (wie z.B. Verzeichnisse oder Arrays), wird das Ergebnis als Array
   zur�ckgegeben (Standardeinstellung 0). Ein Wert von 1 weist die Funktion an,
   das Ergebnis als verketteten String zuruckzugeben. Diese Variable ist
   optional, Standardeinstellung ist 0.

 Beispiel:

   $results=phpMussel("/user_name/public_html/my_file.html",1,1);
   echo $results;

   Gibt so etwas wie dies (als eine String):
    Wed, 18 Sep 2013 02:49:46 +0000 Gestartet.
    > �berpr�fung '/user_name/public_html/my_file.html':
    -> Keine Probleme gefunden.
    Wed, 18 Sep 2013 02:49:47 +0000 Fertig.

 Eine vollst�ndige Liste der Signaturen, die phpMussel nutzt und wie diese
 verarbeitet werden, finden Sie im Abschnitt SIGNATURENFORMAT.

 Sollten irgendwelche Fehlalarme auftreten, Sie etwas entdecken, was Ihrer
 Meinung nach blockiert werden sollte oder etwas mit den Signaturen nicht
 funtionieren, so informieren Sie mich, damit ich die erforderlichen �nderungen
 durchf�hren kann.

 Um die Signaturen, die in phpMussel enthalten sind, zu deaktivieren, lesen Sie
 bitte die Hinweise zum Greylisting im Abschnitt BROWSER BEFEHLE.

 Zus�tzlich zum �berpr�fen von hochgeladenen Dateien und dem optionalen
 �berpr�fen von Dateien und Verzeichnissen mittels der oben genannten Funktion,
 ist in phpMussel eine Funktion enthalten, Textk�rper (body) von E-Mails zu
 �berpr�fen. Diese Funktion verh�lt sich �hnlich wie die normalen
 Scan-Funktionen von phpMussel, ist allerdings auf die E-Mail-Signaturen von
 ClamAV fokussiert. Diese Signaturen sind nicht in den normalen Funktionen von
 phpMussel eingebunden, da es h�chst unwahrscheinlich ist, eine E-Mail auf
 einer Webseite, in der phpMussel eingebunden ist, innerhalb eines Dateiuploads
 �berpr�fen zu m�ssen. Diese Signaturen in die phpMussel-Funktionen einzubinden
 w�re redundant. Diese separate Funktion ist n�tzlich f�r CMS, die mit dem
 E-Mail-System zusammenarbeiten oder Systeme, die E-Mails mittels PHP
 analysieren. Diese Funktion wird in der "phpmussel.ini" konfiguriert. Um diese
 Funktion zu nutzen (Sie ben�tigen Ihre eigene Implementierung), f�gen Sie in
 eine PHP-Datei, in welcher phpMussel eingebunden ist, folgenden Code hinzu:

 phpMussel_mail($body);

 $body ist der Textk�rper (Body) der E-Mail, die Sie �berpr�fen m�chten
 (zus�tzlich k�nnen Sie versuchen, neue Forenbeitr�ge oder eingehende
 Nachrichten aus einem Formular zu scannen). Tritt ein Fehler auf, wird ein
 Wert von -1 zur�ckgegeben. Wurde der Scan beendet und keine Auff�lligkeiten
 festgestellt, gibt die Funktion den Wert 0 zur�ck. Sollte etwas festgestellt
 werden, gibt die Funktion einen String mit einer Nachricht, was gefunden
 wurde, zur�ck.

 Sollten Sie die Quelltexte betrachten, werden Sie die Funktionen phpMusselD()
 und phpMusselR() auffinden. Diese Funktionen sind Subroutinen der phpMussel()
 und sollten nicht au�erhalb der �bergeordneten Funktion aufgerufen werden
 (nicht wegen der Nebeneffekte, sie h�tten allein ausgef�hrt einfach nur keinen
 Zweck und w�rden nicht korrekt ausgef�hrt werden). Es gibt noch viele weitere
 Funktionen und Steuerm�glichkeiten in phpMussel f�r Ihren Einsatzzweck. F�r
 andere Funktionen und Steuerm�glichkeiten, die hier nicht aufgelistet sind,
 lesen Sie bitte den Abschnitt BROWSER BEFEHLE.

                                     ~ ~ ~                                     


 3B. BENUTZUNG (CLI)

 Bitte lesen Sie den Abschnitt INSTALLATION (CLI).

 Bedenken Sie, dass zuk�nftige Versionen von phpMussel andere Systeme
 unterst�tzen werden, zur Zeit jedoch phpMussel im CLI-Modus nur f�r
 Windows-Systeme optimiert wurde (Sie k�nnen nat�rlich versuchen, phpMussel auf
 anderen Systemen zu installieren, jedoch wird nicht garantiert, dass es wie
 vorgesehen funktioniert). Beachten Sie au�erdem, dass phpMussel keine
 vollst�ndige Antiviren-Software ersetzt, nicht den aktiven Speicher �berwacht
 oder Viren spontan erkennt! Es erkennt nur Viren in den Dateien, die Sie
 explizit zum Scannen angegeben haben.

                                     ~ ~ ~                                     


 4A. BROWSER BEFEHLE

 Ist phpMussel auf Ihren System installiert und funktioniert ordnungsgem��,
 sind Sie in de Lage, einige Verwaltungsfunktionen und Befehle an phpMussel
 �ber Ihren Browser zu �bergeben, sofern Sie die Variablen script_password und
 logs_password in Ihrer Konfigurationsdatei gesetzt haben. Diese Passw�rter
 m�ssen zum Aktivieren dieser Kontrollen gesetzt werden, um eine gr��t m�gliche
 Sicherheit zu erlangen, die browserbasierten Kontrollen zu sch�tzen und um
 daf�r zu sorgen, dass diese browserbasierten Kontrollen vollst�ndig
 deaktiviert werden k�nnen, wenn sie nicht von Ihnen, dem Webmaster oder den
 Administratoren ben�tigt werden. Zum Aktivieren dieser Kontrollm�glichkeiten
 wird ein Passwort vergeben, zum Deaktivieren wird kein Passwort vergeben.
 Alternativ k�nnen Sie diese Kontrollen aktivieren und zu einem sp�teren
 Zeitpunkt mit einem Befehl deaktivieren (z.B. wenn Sie Aktionen durchf�hren
 m�ssen und bef�rchten, dass Ihr Passwort ausgelesen werden kann, so k�nnen
 Sie die Kontrollen schnell deaktivieren ohne die Konfigurationsdatei zu
 bearbeiten).

 Gr�nde, warum Sie diese Kontrollen aktivieren sollten:
 - Bietet die M�glichkeit, Signaturen schnell in eine Greylist aufzunehmen,
   wenn Sie Dateien auf Ihr System hochladen und Fehlalarme erzeugt werden und
   Sie nicht die Zeit haben, die Greylist manuell zu bearbeiten.
 - Bietet die M�glichkeit, anderen Personen die Kontrollen �ber phpMussel zu
   geben, ohne ihnen Zugang �ber FTP zu gew�hren.
 - Bietet die M�glichkeit, kontrollierten Zugang zu Ihren Log-Dateien zu
   gew�hren.
 - Bietet einen einfachen Weg, phpMussel zu aktualisieren.
 - Bietet die M�glichkeit, phpMussel zu �berwachen, wenn kein FTP-Zugang oder
   andere Zugangsmethoden verf�gbar sind.

 Gr�nde, warum Sie diese Kontrollen nicht aktivieren sollten:
 - Bietet einen Vektor f�r Angreifer, ob Sie phpMussel nutzen oder nicht (je
   nach Perspektive k�nnte dies ein Grund f�r oder gegen die Nutzung der
   Browserbefehle sein), indem blind Befehle an Ihren Server gesendet werden
   (Probing). Einerseits k�nnte dies den Angreifer entmutigen, sobald er
   feststellt, dass die Angriffsmethoden aufgrund der Ergebnisse von phpMussel
   nutzlos sind. Andererseits k�nnte ein unvorhergesehener oder bislang
   unbekannter Exploit f�r phpMussel oder f�r zuk�nftige Versionen einen
   Angriffsverkor bieten, ein positives Ergebnis einer blinden Anfrage k�nnte
   den Angreifer ermutigen, Ihr System zu attackieren.
 - Sollte Ihr Passwort kompromittiert worden sein, bietet es dem Angreifer die
   M�glichkeit, Signaturen zu umgehen, die normalerweise den Angriff verhindert
   h�tten, oder phpMussel vollst�ndig zu deaktivieren.

 Die Entscheidung m�ssen Sie selbst treffen. Standardm��ig sind diese
 Kontrollen deaktiviert, dennoch erkl�rt dieser Abschnitt, wie Sie die
 Kontrollen aktivieren und nutzen.

 Liste der verf�gbaren Browser Befehle:

 scan_log
   Ben�tigtes Passwort: logs_password
   Weitere Bedingungen: scan_log muss gesetzt sein.
   Ben�tigte Parameter: (keine)
   Optionale Parameter: (keine)
   Beispiel: ?logspword=[logs_password]&phpmussel=scan_log
   ~
   Zweck: Gibt den Inhalt der Datei scan_log aus.
   ~
 scan_kills
   Ben�tigtes Passwort: logs_password
   Weitere Bedingungen: scan_kills muss gesetzt sein.
   Ben�tigte Parameter: (keine)
   Optionale Parameter: (keine)
   Beispiel: ?logspword=[logs_password]&phpmussel=scan_kills
   ~
   Zweck: Gibt den Inhalt der Datei scan_kills aus.
   ~
 controls_lockout
   Ben�tigtes Passwort: logs_password ODER script_password
   Weitere Bedingungen: (keine)
   Ben�tigte Parameter: (keine)
   Optionale Parameter: (keine)
   Beispiel 1: ?logspword=[logs_password]&phpmussel=controls_lockout
   Beispiel 2: ?pword=[script_password]&phpmussel=controls_lockout
   ~
   Zweck: Deaktiviert ("lock out") alle browser-basierten Kontrollen. Diese
          Funktion sollte benutzt werden, wenn Sie bef�rchten, dass Ihr
          Passwort kompromittiert wurde (dies ist m�glich, wenn Sie die
          Kontrollen von einem Computer aus benutzen, der nicht abgesichert
          oder dem nicht vertraut werden kann). controls_lockout erstellt die
          Datei controls.lck im Verzeichnis "vault", wonach phpMussel zuerst
          sucht, befor es Aktionen ausf�hrt. Wurden die Kontrollen deaktiviert,
          m�ssen Sie die Datei controls.lck file manuell mittels FTP o.�.
          l�schen. Kann mit jedem Passwort aufgerufen werden.
   ~
 disable
   Ben�tigtes Passwort: script_password
   Weitere Bedingungen: (keine)
   Ben�tigte Parameter: (keine)
   Optionale Parameter: (keine)
   Beispiel: ?pword=[script_password]&phpmussel=disable
   ~
   Zweck: Deaktiviert phpMussel. Wird benutzt, wenn Sie Aktualisierungen
          d�rchf�hren, �nderungen an Ihrem System vornehmen oder Software oder
          Module installieren und m�glicherweise Fehlalarme ausgel�st werden
          k�nnten. Sie k�nnen diese Funktion nutzen, wenn Sie Probleme mit
          phpMussel entdecken und es nicht von Ihrem System entfernen m�chten.
          Um phpMussel wieder zu aktivieren, nutzen Sie "enable".
   ~
 enable
   Ben�tigtes Passwort: script_password
   Weitere Bedingungen: (keine)
   Ben�tigte Parameter: (keine)
   Optionale Parameter: (keine)
   Beispiel: ?pword=[script_password]&phpmussel=enable
   ~
   Zweck: Aktiviert phpMussel. Wird benutzt, wenn Sie phpMussel mittels
          "disable" deaktiviert haben und es wieder aktivieren m�chten.
   ~
 update
   Ben�tigtes Passwort: script_password
   Weitere Bedingungen: update.dat und update.inc m�ssen vorhanden sein.
   Ben�tigte Parameter: (keine)
   Optionale Parameter: forcedupdate
   Beispiele: ?pword=[script_password]&phpmussel=update&musselvar=forcedupdate
   ~
   Zweck: Sucht nach Aktualisierungen f�r phpMussel und Signaturen. War die
          Suche erfolgreich und Aktualisierungen sind verf�gbar, so werden
          diese heruntergeladen und installiert. Wenn zu schnell oder zu oft
          nach Aktualisierungen gesucht wird, wird die Suche abgebrochen.
          Schl�gt die Suche fehl, wird der Vorgang abgebrochen. Wird der
          optionale Parameter "forcedupdate" Verwendet, wird der Timestamp des
          letzten Aktualisierungen ignoriert und die Suche fortgesetzt, selbst
          wenn zu oft oder zu schnell gesucht wurde, jedoch wird der Vorgang
          abgebrochen, wenn die Suche fehlschl�gt. Die Ergebnisse des gesamten
          Vorgangs werden ausgegeben. Es wird empfohlen, den optionalen
          Parameter "forcedupdate" zu nutzen, wenn die Aktualisierungen manuell
          ausgef�hrt wird, benutzen Sie diesen Parameter jedoch nicht in einem
          automatisierten Prozess wie cron o.�."forcedupdate". Es wird
          empfohlen, mindestens einmal monatlich nach Aktualisierungen zu
          suchen, um sicherzustellen, dass die Signaturen und Ihre Kopie von
          phpMussel auf dem neuesten Stand sind. Eine h�ufigere Suche nach
          Aktualisierungen ist fruchtlos, da die entsprechenden Pakete meist
          monatlich eingestellt werden.
   ~
 greylist
   Ben�tigtes Passwort: script_password
   Weitere Bedingungen: (keine)
   Ben�tigte Parameter: [Name der Signatur f�r die Greylist]
   Optionale Parameter: (keine)
   Beispiel: ?pword=[script_password]&phpmussel=greylist&musselvar=[Signature]
   ~
   Zweck: F�gt eine Signatur zur Greylist hinzu.
   ~
 greylist_clear
   Ben�tigtes Passwort: script_password
   Weitere Bedingungen: (keine)
   Ben�tigte Parameter: (keine)
   Optionale Parameter: (keine)
   Beispiel: ?pword=[script_password]&phpmussel=greylist_clear
   ~
   Zweck: L�scht die gesamte Greylist.
   ~
 greylist_show
   Ben�tigtes Passwort: script_password
   Weitere Bedingungen: (keine)
   Ben�tigte Parameter: (keine)
   Optionale Parameter: (keine)
   Beispiel: ?pword=[script_password]&phpmussel=greylist_show
   ~
   Zweck: Gibt den Inhalt der Greylist aus.
   ~

                                     ~ ~ ~                                     


 4B. CLI (COMMAND LINE INTERFACE)

 phpMussel kann als interactiver Scanner im CLI-Modus in einer
 Windows-Systemumgebung genutzt werden.

 Bitte lesen Sie den Abschnitt INSTALLATION (CLI).

 F�r eine Liste der verf�gbaren CLI-Befehle, an der
 CLI-Eingabeaufforderung, schreiben "c", und dr�cken Sie die Enter.

                                     ~ ~ ~                                     


 5. IM PAKET ENTHALTENE DATEIEN

 Die folgende Liste beinhaltet alle Dateien, die im heruntergeladenen Archiv
 des Scripts enthalten sind und Dateien, die durch die Benutzung des Scripts
 eventuell erstellt werden, incl. einer kurzen Beschreibung.

 /phpmussel.php (Script, enthalten)
    phpMussel Loader file. L�dt das script, Updater, etc.
    Diese Datei wird in Ihr CMS eingebunden (notwendig)!
    ~
 /web.config (Sonstiges, enthalten)
    Eine ASP.NET-Konfigurationsdatei (in diesem Fall zum Schutz des
    Verzeichnisses "/vault" vor einem nicht authorisierten Zugriff, sofern das
    Script auf einem auf der ASP.NET-Technologie basierenden Server installiert
    wurde).
    ~
 /_docs/ (Verzeichnis)
    Dokumentation-Verzeichnis (beinhaltet verschiedene Dateien).
    ~
 /_docs/change_log.txt (Dokumentation, enthalten)
    Eine Auflistung der �nderungen des Scripts der verschiedenen Versionen
    (f�r die korrekte Funktion des Scripts nicht notwendig).
    ~
 /_docs/readme.XX.txt (Dokumentation, enthalten)
    Die README-Dateien (z.B. die Datei, die Sie gerade lesen).
    ~
 /_testfiles/ (Verzeichnis)
    Verzeichnis f�r Testdateien (beinhaltet verschiedene Dateien). Alle
    enthaltenen Dateien dienen zur �berpr�fung, ob phpMussel auf Ihrem System
    ordnungsgem�� installiert wurde. Sie m�ssen dieses Verzeichnis oder die
    Dateien nicht hochladen, sofern Sie keinen solchen Test durchf�hren
    m�chten.
    ~
 /_testfiles/exe_standard_testfile.exe (Testdatei, enthalten)
    Testdatei zur �berpr�fung der PE-Signaturen.
    ~
 /_testfiles/general_standard_testfile.txt (Testdatei, enthalten)
    Testdatei zur �berpr�fung der allgemeinen Signaturen.
    ~
 /_testfiles/graphics_standard_testfile.gif (Testdatei, enthalten)
    Testdatei zur �berpr�fung der Graphik-Signaturen.
    ~
 /_testfiles/md5_testfile.txt (Testdatei, enthalten)
    Testdatei zur �berpr�fung der MD5-Signaturen.
    ~
 /_testfiles/metadata_testfile.txt.gz (Testdatei, enthalten)
    Testdatei zur �berpr�fung der Metadata-Signaturen und zur �berpr�fung der
    GZ-Archivunterst�tzung Ihres Systems.
    ~
 /_testfiles/metadata_testfile.txt.zip (Testdatei, enthalten)
    Testdatei zur �berpr�fung der Metadata-Signaturen und zur �berpr�fung der
    ZIP-Archivunterst�tzung Ihres Systems.
    ~
 /_testfiles/pe_sectional_testfile.exe (Testdatei, enthalten)
    Testdatei zur �berpr�fung der PE-Sectional-Signaturen.
    ~
 /vault/ (Verzeichnis)
    Vault-Verzeichnis (beinhaltet verschiedene Dateien).
    ~
 /vault/.htaccess (Sonstiges, enthalten)
    Ein hypertext access file (in diesem Fall zum Schutz von sensiblen Dateien
    des Scripts vor einem nicht authorisierten Zugriff).
    ~
 /vault/elf_clamav_regex.cvd (Signaturen, enthalten)
 /vault/elf_clamav_regex.map (Signaturen, enthalten)
 /vault/elf_clamav_standard.cvd (Signaturen, enthalten)
 /vault/elf_clamav_standard.map (Signaturen, enthalten)
 /vault/elf_custom_regex.cvd (Signaturen, enthalten)
 /vault/elf_custom_standard.cvd (Signaturen, enthalten)
 /vault/elf_mussel_regex.cvd (Signaturen, enthalten)
 /vault/elf_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der ELF-Signaturen.
    Ben�tigt, wenn die Option "ELF signatures" in der phpmussel.ini aktiviert
    ist. Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist
    (Dateien werden bei einem Update neu erstellt).
    ~
 /vault/exe_clamav_regex.cvd (Signaturen, enthalten)
 /vault/exe_clamav_regex.map (Signaturen, enthalten)
 /vault/exe_clamav_standard.cvd (Signaturen, enthalten)
 /vault/exe_clamav_standard.map (Signaturen, enthalten)
 /vault/exe_custom_regex.cvd (Signaturen, enthalten)
 /vault/exe_custom_standard.cvd (Signaturen, enthalten)
 /vault/exe_mussel_regex.cvd (Signaturen, enthalten)
 /vault/exe_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der Portable Executable file (EXE)-Signaturen.
    Ben�tigt, wenn die Option "EXE signatures" in der phpmussel.ini aktiviert
    ist. Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist
    (Dateien werden bei einem Update neu erstellt).
    ~
 /vault/filenames_clamav.cvd (Signaturen, enthalten)
 /vault/filenames_custom.cvd (Signaturen, enthalten)
 /vault/filenames_mussel.cvd (Signaturen, enthalten)
    Dateien der filename-Signaturen.
    Ben�tigt, wenn die Option "filename signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist (Dateien werden bei einem Update neu erstellt).
    ~
 /vault/general_clamav_regex.cvd (Signaturen, enthalten)
 /vault/general_clamav_regex.map (Signaturen, enthalten)
 /vault/general_clamav_standard.cvd (Signaturen, enthalten)
 /vault/general_clamav_standard.map (Signaturen, enthalten)
 /vault/general_custom_regex.cvd (Signaturen, enthalten)
 /vault/general_custom_standard.cvd (Signaturen, enthalten)
 /vault/general_mussel_regex.cvd (Signaturen, enthalten)
 /vault/general_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der allgemeinen Signaturen.
    Ben�tigt, wenn die Option "general signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist (Dateien werden bei einem Update neu erstellt).
    ~
 /vault/graphics_clamav_regex.cvd (Signaturen, enthalten)
 /vault/graphics_clamav_regex.map (Signaturen, enthalten)
 /vault/graphics_clamav_standard.cvd (Signaturen, enthalten)
 /vault/graphics_clamav_standard.map (Signaturen, enthalten)
 /vault/graphics_custom_regex.cvd (Signaturen, enthalten)
 /vault/graphics_custom_standard.cvd (Signaturen, enthalten)
 /vault/graphics_mussel_regex.cvd (Signaturen, enthalten)
 /vault/graphics_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der Signaturen f�r Grafikdateien.
    Ben�tigt, wenn die Option "graphics signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist (Dateien werden bei einem Update neu erstellt).
    ~
 /vault/greylist.csv (Signaturen, enthalten / wird erstellt)
    CSV der Signaturen in der Greylist, die phpMussel ignorieren soll
    (Datei wird nach dem L�schen automatisch neu erstellt).
    ~
 /vault/hex_general_commands.csv (Signaturen, enthalten)
    Hex-encodierte CSV mit allgemeinen command detections. Ben�tigt, wenn die
    Option "general command detection" in der phpmussel.ini aktiviert ist. Die
    Datei kann entfernt werden, wenn die Option deaktiviert ist (Datei wird bei
    einem Update neu erstellt).
    ~
 /vault/lang.inc (Script, enthalten)
    Sprachpaket f�r phpMussel; Erforderlich f�r unterst�tzung mehrerer
    Sprachen.
    ~
 /vault/macho_clamav_regex.cvd (Signaturen, enthalten)
 /vault/macho_clamav_regex.map (Signaturen, enthalten)
 /vault/macho_clamav_standard.cvd (Signaturen, enthalten)
 /vault/macho_clamav_standard.map (Signaturen, enthalten)
 /vault/macho_custom_regex.cvd (Signaturen, enthalten)
 /vault/macho_custom_standard.cvd (Signaturen, enthalten)
 /vault/macho_mussel_regex.cvd (Signaturen, enthalten)
 /vault/macho_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der Mach-O-Signaturen.
    Ben�tigt, wenn die Option "Mach-O signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist (Dateien werden bei einem Update neu erstellt).
    ~
 /vault/mail_clamav_regex.cvd (Signaturen, enthalten)
 /vault/mail_clamav_regex.map (Signaturen, enthalten)
 /vault/mail_clamav_standard.cvd (Signaturen, enthalten)
 /vault/mail_clamav_standard.map (Signaturen, enthalten)
 /vault/mail_custom_regex.cvd (Signaturen, enthalten)
 /vault/mail_custom_standard.cvd (Signaturen, enthalten)
 /vault/mail_mussel_regex.cvd (Signaturen, enthalten)
 /vault/mail_mussel_standard.cvd (Signaturen, enthalten)
    Signaturdateien f�r die Funktion phpMussel_mail().
    Dateien werden auf jeden Fall von der Funktion phpMussel_mail() ben�tigt.
    Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist
    (Dateien werden bei einem Update neu erstellt).
    ~
 /vault/md5_clamav.cvd (Signaturen, enthalten)
 /vault/md5_custom.cvd (Signaturen, enthalten)
 /vault/md5_mussel.cvd (Signaturen, enthalten)
    Dateien der MD5-signaturen.
    Ben�tigt, wenn die Option "MD5" in der phpmussel.ini aktiviert ist. Die
    Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist (Dateien
    werden bei einem Update neu erstellt).
    ~
 /vault/metadata_clamav.cvd (Signaturen, enthalten)
 /vault/metadata_custom.cvd (Signaturen, enthalten)
 /vault/metadata_mussel.cvd (Signaturen, enthalten)
    Dateien f�r die Signaturen der Archiv-Metadaten.
    Ben�tigt, wenn die Option "archive metadata signatures" in der
    phpmussel.ini aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die
    Option deaktiviert ist (Dateien werden bei einem Update neu erstellt).
    ~
 /vault/pe_clamav.cvd (Signaturen, enthalten)
 /vault/pe_custom.cvd (Signaturen, enthalten)
 /vault/pe_mussel.cvd (Signaturen, enthalten)
    Dateien der PE-Sectional-Signaturen.
    Ben�tigt, wenn die Option "PE Sectional signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist (Dateien werden bei einem Update neu erstellt).
    ~
 /vault/phpmussel.inc (Script, enthalten)
    phpMussel Core Script (absolut notwendig)!
    ~
 /vault/phpmussel.ini (Sonstiges, enthalten)
    phpMussel Konfigurationsdatei; beinhaltet alle
    Konfigurationsm�glichkeiten von phpMussel (absolut notwendig)!
    ~
 /vault/scan_log.txt *(Logfile, wird erstellt)
    Eine Aufzeichnung aller von phpMussel gescanten Objekte.
    ~
 /vault/scan_kills.txt *(Logfile, wird erstellt)
    Eine Aufzeichnung aller von phpMussel blockierten Dateiuploads.
    ~
 /vault/template.html (Sonstiges, enthalten)
    phpMussel Template file; Template f�r die HTML-Ausgabe mit der Nachricht,
    dass der Dateiupload von phpMussel blockiert wurde (Nachricht, die dem
    Nutzer angezeigt wird).
    ~
 /vault/update.dat (Sonstiges, enthalten)
    Datei beinhaltet Versionsinformationen des Scripts und der Signaturen.
    Diese Datei ist notwendig, wenn Sie phpMussel automatisch oder mittels
    Browser aktualisieren wollen.
    ~
 /vault/update.inc (Script, enthalten)
    phpMussel Update Script; Wird nur f�r die automatische Aktualisierung und
    Aktualisierung mittels Browser ben�tigt.
    ~

 * Der Dateiname kann je nach Konfiguratuion in der phpmussel.ini variieren.

 = BETRIFFT DIE SIGNATURDATEIEN =
    CVD ist ein Akronym f�r "ClamAV Virus Definitions", in Bezug auf die
    Namensgebung der Signaturen von ClamAV und zur Nutzung durch phpMussel;
    Dateien mit der Endung "CVD" enthalten Signaturen.
    ~
    Dateien mit der Endung "MAP" stellen eine Liste dar, welche Signaturen
    phpMussel f�r einzelne Scans nutzen soll und welche nicht; Nicht alle
    Signaturen werden unbedingt f�r jeden einzelnen Scan ben�tigt, phpMussel
    nutzt diese Listen, um den Scanprozess zu beschleunigen (der sonst recht
    langsam und ressourcenaufw�ndig w�re).
    ~
    Signaturdateien mit der Kennzeichnung "_regex" enthalten Signaturen, welche
    regul�re Ausdrucke verwenden (regex).
    ~
    Signaturdateien mit der Kennzeichnung "_standard" enthalten Signaturen,
    welche nicht jede Form der Musterpr�fung nutzen.
    ~
    Signaturdateien, die weder mit "_regex" oder "_standard" gekennzeichnet
    sind, sind entweder das eine oder das andere, aber nicht beides (Bitte
    lesen Sie den Abschnitt SIGNATURENFORMAT).
    ~
    Signaturdateien mit der Kennzeichnung "_clamav" enthalten Signaturen direkt
    aus der Datenbank von ClamAV (GNU/GPL).
    ~
    Signaturdateien mit der Kennzeichnung "_custom" enthalten in der
    Voreinstellung keinerlei Signaturen; In diese Dateien k�nnen Sie Ihre
    eigenen Signaturen eintragen.
    ~
    Signaturdateien mit der Kennzeichnung "_mussel" enthalten Signaturen,
    welche nicht von ClamAV stammen.
    ~

                                     ~ ~ ~                                     


 6. EINSTELLUNGEN

 Nachfolgend finden Sie eine Liste der Variablen in der Konfigurationsdatei
 "phpmussel.ini" mit einer kurzen Beschreibung ihrer Funktionen.

 "general" (Category)
 - General configuration for phpMussel.
    "script_password"
    - As a conveniance, phpMussel will allow certain functions (including the
      ability to update phpMussel on-the-fly) to be manually triggered via
      POST, GET and QUERY. However, as a security precaution, to do this,
      phpMussel will expect a password to be included with the command, as to
      ensure that it is you, and not someone else, attempting to manually
      trigger these functions. Set script_password to whatever password you
      would like to use. If no password is set, manual triggering will be
      disabled by default. Use something you will remember but which is hard
      for others to guess.
      * Has no influence in CLI mode.
    "logs_password"
    - The same as script_password, but for viewing the contents of scan_log
      and scan_kills. Having separate passwords can be useful if you want to
      give someone else access to one set of functions but not the other.
      * Has no influence in CLI mode.
    "cleanup"
    - Unset script variables and cache after execution. If you aren't using
      the script beyond the initial scanning of uploads, should set to yes, to
      minimize memory usage. If you are using the script for purposes beyond
      the initial scanning of uploads, should set to no, to avoid unnecessarily
      reloading duplicate data into memory. In general practise, it should
      probably be set to yes, but, if you do this, you won't be able to use the
      script for anything other than scanning file uploads.
      * Has no influence in CLI mode.
    "scan_log"
    - Filename of file to log all scanning results to. Specify a filename, or
      leave blank to disable.
    "scan_kills"
    - Filename of file to log all records of blocked or killed uploads to.
      Specify a filename, or leave blank to disable.
    "ipaddr"
    - Where to find IP address of connecting request? (Useful for services
      such as Cloudflare and the likes) Default = REMOTE_ADDR
      WARNING: Don't change this unless you know what you're doing!
    "forbid_on_block"
    - Should phpMussel send 403 headers with the file upload blocked message,
      or stick with the usual 200 OK? 0 = No (200) [Default], 1 Yes (403).
    "delete_on_sight"
    - Switching on this option will instruct the script to attempt to
      immediately delete any file it finds during its scans that matches any
      detection criteria, whether via signatures or otherwise. Files determined
      to be "clean" will not be touched. In the case of archives, the entire
      archive will be deleted (regardless of if the offending file is only one
      of several files contained within the archive). For the case of file
      upload scanning, usually, it isn't necessary to turn this option on,
      because usually, php will automatically purge the contents of its cache
      when execution has finished, meaning that it'll usually delete any files
      uploaded through it to the server unless they've moved, copied or deleted
      already. The option is added here as an extra measure of security for the
      extra paranoid and for those whose copies of php may not always behave in
      the manner intended.
      0 - After scanning, leave the file alone [Default],
      1 - After scanning, if not clean, delete immediately.
    "lang"
    - Specify the default language for phpMussel.
 "signatures" (Category)
 - Configuration for signatures.
   %%%_clamav = ClamAV signatures (both mains and daily).
   %%%_custom = Your custom signatures (if you've written any).
   %%%_mussel = phpMussel signatures included in your current signatures set
                which aren't from ClamAV.
   - Check against MD5 signatures when scanning?
     0 = No, 1 = Yes [Default].
     "md5_clamav"
     "md5_custom"
     "md5_mussel"
   - Check against general signatures when scanning?
     0 = No, 1 = Yes [Default].
     "general_clamav"
     "general_custom"
     "general_mussel"
   - Check PE (portable executable) files (EXE, DLL, etc) against PE Sectional
     signatures when scanning?
     0 = No, 1 = Yes [Default].
     "pe_clamav"
     "pe_custom"
     "pe_mussel"
   - Check PE (portable executable) files (EXE, DLL, etc) against PE signatures
     when scanning?
     0 = No, 1 = Yes [Default].
     "exe_clamav"
     "exe_custom"
     "exe_mussel"
   - Check ELF files against ELF signatures when scanning?
     0 = No, 1 = Yes [Default].
     "elf_clamav"
     "elf_custom"
     "elf_mussel"
   - Check Mach-O files (OSX, etc) against Mach-O signatures when scanning?
     0 = No, 1 = Yes [Default].
     "macho_clamav"
     "macho_custom"
     "macho_mussel"
   - Check graphics files against graphics based signatures when scanning?
     0 = No, 1 = Yes [Default].
     "graphics_clamav"
     "graphics_custom"
     "graphics_mussel"
   - Check archive contents against archive metadata signatures when scanning?
     0 = No, 1 = Yes [Default].
     "metadata_clamav"
     "metadata_custom"
     "metadata_mussel"
   - Check filenames against filename based signatures when scanning?
     0 = No, 1 = Yes [Default].
     "filenames_clamav"
     "filenames_custom"
     "filenames_mussel"
   - Allow scanning with phpMussel_mail()?
     0 = No, 1 = Yes [Default].
     "mail_clamav"
     "mail_custom"
     "mail_mussel"
   - Signature matching length limiting options. Only change these if you
     know what you're doing. SD = Standard signatures. RX = PCRE (Perl
     Compatible Regular Expressions, or "Regex") signatures. FN = Filename
     signatures. If you notice php crashing when phpMussel attempts to scan,
     try lowering the "max" values below. If possible and convenient, let me
     know when this happens and the results of whatever you try.
     "fn_siglen_min"
     "fn_siglen_max"
     "rx_siglen_min"
     "rx_siglen_max"
     "sd_siglen_min"
     "sd_siglen_max"
   - Should phpMussel report when signatures files are missing or corrupted?
     If fail_silently is disabled, missing and corrupted files will be reported
     on scanning, and if fail_silently is enabled, missing and corrupted files
     will be ignored, with scanning reported for those files that there are no
     problems. This should generally be left alone unless you're experiencing
     crashes or similar problems.
     0 = Disabled [Default], 1 = Enabled.
     "fail_silently"
 "files" (Category)
 - General configuration for handling of files.
   "max_uploads"
   - Maximum allowable number of files to scan during files upload scan before
     aborting the scan and informing the user they are uploading too much at
     once! Provides protection against a theoretical attack whereby an attacker
     attempts to DDoS your system or CMS by overloading phpMussel to slow down
     the php process to a grinding halt. Recommended: 10. You may wish to raise
     or lower this number depending on the speed of your hardware. Note that
     this number does not account for or include the contents of archives.
   "filesize_limit"
   - Filesize limit in KB. 65536 = 64MB [Default], 0 = No limit (always
     greylisted), any (positive) numeric value accepted. This can be useful
     when your php configuration limits the amount of memory a process can hold
     or if your php configuration limits filesize of uploads.
   "filesize_response"
   - What to do with files that exceed the filesize limit (if one exists).
     0 - Whitelist, 1 - Blacklist [Default].
   "filetype_whitelist" and "filetype_blacklist"
   - If your system only allows specific types of files to be uploaded, or if
     your system explicitly denies certain types of files, specifying those
     filetypes in whitelists and blacklists can increase the speed at which
     scanning is performed by allowing the script to skip over certain
     filetypes. Format is CSV (comma separated values). If you want to scan
     everything, rather than whitelist or blacklist, leave the variable(/s)
     blank (doing so will disable whitelist/blacklist).
   "check_archives"
   - Attempt to check the contents of archives?
     0 - No (do not check), 1 - Yes (check) [Default].
     * Currently, only checking of ZIP and GZ files is supported (checking of
       TAR, RAR, CAB, 7z and etcetera not currently supported).
     * This is not foolproof! While I highly recommend keeping this turned on,
       I can't guarantee it'll always find everything.
     * Also be aware that archive checking currently is not recursive for ZIPs
      (although I intend to correct this at some point, and GZ is recursive).
   "filesize_archives"
   - Carry over filesize blacklisting/whitelisting to the contents of archives?
     0 - No (just greylist everything), 1 - Yes [Default].
   "filetype_archives"
   - Carry over filetype blacklisting/whitelisting to the contents of archives?
     0 - No (just greylist everything) [Default], 1 - Yes.
   "max_recursion"
   - Maximum recursion depth limit for archives. Default = 10.
 "attack_specific" (Category)
 - Configuration for specific attack detections (not based on CVDs).
   * Chameleon attack detection: 0 = Off, 1 = On.
   "chameleon_from_php"
   - Search for php header in files that are neither php files nor recognised
     archives.
   "chameleon_from_exe"
   - Search for executable headers in files that are neither executables nor
     recognised archives and for executables whose headers are incorrect.
   "chameleon_to_archive"
   - Search for archives whose headers are incorrect (Supported: ZIP, RAR,
     GZ).
   "chameleon_to_doc"
   - Search for office documents whose headers are incorrect (Supported: DOC,
     DOT, PPS, PPT, XLA, XLS, WIZ).
   "chameleon_to_img"
   - Search for images whose headers are incorrect (Supported: BMP, DIB, PNG,
     GIF, JPEG, JPG, XCF, PSD, PDD).
   "chameleon_to_pdf"
   - Search for PDF files whose headers are incorrect.
   "archive_file_extensions" and "archive_file_extensions_wc"
   - Recognised archive file extensions (format is CSV; should only add or
     remove when problems occur; unnecessarily removing may cause
     false-positives to appear for archive files, whereas unnecessarily adding
     will essentially whitelist what you are adding from attack specific
     detection; modify with caution; also note that this has no effect on what
     archives can and can't be analysed at content-level). The list, as is at
     default, lists those formats used most commonly across the majority of
     systems and CMS, but intentionally isn't necessarily comprehensive.
   "general_commands"
   - Search content of files for general commands such as eval(), exec() and
     include()? 0 - No (do not check) [Default], 1 - Yes (check).
     Turn this option off if you intend to upload any of the following to your
     system or CMS via your browser: php, JavaScript, HTML, python, perl files
     and etcetera. Turn this option on if you do not have any additional
     protections on your system and do not intend to upload such files. If you
     use additional security in conjunction with phpMussel such as ZB Block,
     there is no need to turn this option on, because most of what phpMussel
     will look for (in the context of this option) are duplications of
     protections that are already provided.
   "block_control_characters"
   - Block any files containing any control characters (other than newlines)?
     ([\x00-\x08\x0b\x0c\x0e\x1f\x7f]) If you are -only- uploading plain-text,
     then you can turn this option on to provide some additional protection to
     your system. However, if you upload anything other than plain-text,
     turning this on may result in false positives.
     0 - Don't block [Default], 1 - Block.
   "corrupted_exe"
   - Corrupted files and parse errors. 0 = Ignore, 1 = Block [Default].
     Detect and block potentially corrupted PE (portable executable) files?
     Often (but not always), when certain aspects of a PE file are corrupted or
     can't be parsed correctly, it can be indicative of a viral infection. The
     processes used by most anti-virus programs to detect viruses in PE files
     require parsing those files in certain ways, which, if the programmer of a
     virus is aware of, will specifically try to prevent, in order to allow
     their virus to remain undetected.
 "compatibility" (Category)
 - Compatibility directives for phpMussel.
    "ignore_upload_errors"
    - This directive should generally be switched OFF unless it is required for
      correct functionality of phpMussel on your specific system. Normally,
      when switched OFF, when phpMussel detects the presence of elements in the
      $_FILES array(), it will attempt to initiate a scan of the files that
      those elements represent, and, if those elements are blank or empty,
      phpMussel will return an error message. This is proper behaviour for
      phpMussel. However, for some CMS, empty elements in $_FILES can occur as
      a result of the natural behaviour of those CMS, or errors may be reported
      when there aren't any, in which case, the normal behaviour for phpMussel
      will be interfering with the normal behaviour of those CMS. If such a
      situation occurs for you, turning this option ON will instruct phpMussel
      to not attempt to initiate scans for such empty elements, ignore them
      when found and to not return any related error messages, thus allowing
      continuation of the page request. 0 - OFF, 1 - ON.


                                     ~ ~ ~                                     


 7. SIGNATURENFORMAT

 = MD5 SIGNATURES =
   All MD5 signatures follow the format:
    HASH:FILESIZE:NAME
   Where HASH is the MD5 hash of an entire file, FILESIZE is the total size
   of that file and NAME is the name to cite for that signature.

 = FILENAME SIGNATURES =
   All filename signatures follow the format:
    NAME:FNRX
   Where NAME is the name to cite for that signature and FNRX is the regex
   pattern to match filenames (unencoded) against.

 = ARCHIVE METADATA SIGNATURES =
   All archive metadata signatures follow the format:
    NAME:FILESIZE:CRC32
   Where NAME is the name to cite for that signature, FILESIZE is the total
   size (uncompressed) of a file contained within the archive and CRC32 is
   the crc32 checksum of that contained file.

 = EVERYTHING ELSE =
   All other signatures follow the format:
    NAME:HEX:FROM:TO
   Where NAME is the name to cite for that signature and HEX is a
   hexidecimal-encoded segment of the file intended to be matched by
   the given signature. FROM and TO are optional parameters, indicting from
   which and to which positions in the source data to check against (not
   supported by the mail function).

 = REGEX =
   Any form of regex understood and correctly processed by php should also be
   correctly understood and processed by phpMussel and its signatures.
   However, I'd suggest taking extreme caution when writing new regex based
   signatures, because, if you're not entirely sure what you're doing, there
   can be highly irregular and/or unexpected results. Take a look at the
   phpMussel source-code if you're not entirely sure about the context in
   which regex statements are parsed. Also, remember that all patterns (with
   exception to filename, archive metadata and MD5 patterns) must be
   hexidecimally encoded (foregoing pattern syntax, of course)!

 = WHERE TO PUT CUSTOM SIGNATURES? =
   Only put custom signatures in those files intended for custom signatures.
   Those files should contain "_custom" in their filenames.
   You should also avoid editing the default signature files, unless you know
   exactly what you're doing, because, aside from being good practise in
   general and aside from helping you distinguish between your own signatures
   and the default signatures included with phpMussel, it is good to stick to
   editing only the files intended for editing, because tampering with the
   default signature files can cause them to stop working correctly, due to the
   "maps" files: The maps files tell phpMussel where in the signature files to
   look for signatures required by phpMussel as per when required, and these
   maps can become out-of-sync with their associated signature files if those
   signature files are tampered with. You can put pretty much whatever you want
   into your custom signatures, so long as you follow the correct syntax.
   However, be careful to test new signatures for false-positives beforehand
   if you intend to share them or use them in a live environment.

 = SIGNATURE BREAKDOWN =
   The following is a breakdown of the types of signatures used by phpMussel:
   - "MD5 Signatures" (md5_*). Checked against the MD5 hash of the contents
      and the filesize of every non-whitelisted file targeted for scanning.
   - "General Signatures" (general_*). Checked against the contents of every
     non-whitelisted file targeted for scanning.
   - "General Commands" (hex_general_commands.csv). Checked against the
     contents of every non-whitelisted file targeted for scanning.
   - "Portable Executable Sectional Signatures" (pe_*). Checked against the
     contents of every non-whitelisted targeted for scanning and matched to the
     PE format.
   - "Portable Executable Signatures" (exe_*). Checked against the contents of
     every non-whitelisted targeted for scanning and matched to the PE format.
   - "ELF Signatures" (elf_*). Checked against the contents of every
     non-whitelisted file targeted for scanning and matched to the ELF format.
   - "Graphics Signatures" (graphics_*). Checked against the contents of every
     non-whitelisted file targeted for scanning and matched to a known
     graphical file format.
   - "Mach-O Signatures" (macho_*). Checked against the contents of every
     non-whitelisted file targeted for scanning and matched to the Mach-O
     format.
   - "ZIP MetaData Signatures" (metadata_*). Checked against the CRC32
     hash and filesize of the initial file contained inside of any
     non-whitelisted archive targeted for scanning.
   - "Email Signatures" (mail_*). Checked against the $body variable parsed
     to the phpMussel_mail() function, which is intended to be the body of
     email messages or similar entities (potentially forum posts and etcetera).
   (Note that any of these signatures may be easily disabled via
    phpmussel.ini).


                                     ~ ~ ~                                     


 8. BEKANNTE KOMPATIBILIT�TSPROBLEME

 PHP and PCRE
 - phpMussel requires PHP and PCRE to execute and function correctly. Without
   php, or without the PCRE extension of PHP, phpMussel will not execute or
   function correctly. Should make sure your system has both PHP and PCRE
   installed and available prior to downloading and installing phpMussel.

 ANTI-VIRUS SOFTWARE COMPATIBILITY

 For the most part, phpMussel should be fairly compatible with most other
 virus scanning software. However, conflictions have been reported by a number
 of users in the past. This information below is from VirusTotal.com, and it
 describes a number of false-positives reported by various anti-virus programs
 against phpMussel. Although this information isn't an absolute guarantee of
 whether or not you will encounter compatibility problems between phpMussel
 and your anti-virus software, if your anti-virus software is noted as
 flagging against phpMussel, you should either consider disabling it prior to
 working with phpMussel or should consider alternative options to either your
 anti-virus software or phpMussel.

 This information was last updated 4th August 2014 and is current for ALL
 versions of phpMussel, from initial release v0.1 through to latest release
 v0.4a at the time of writing this.

 Ad-Aware                Keine Probleme bekannt
 Agnitum                 Keine Probleme bekannt
 AhnLab-V3               Keine Probleme bekannt
 AntiVir                 Keine Probleme bekannt
 Antiy-AVL               Keine Probleme bekannt
 Avast                !  Berichten "JS:ScriptSH-inf [Trj]" (alle au�er v0.3d)
 AVG                     Keine Probleme bekannt
 Baidu-International     Keine Probleme bekannt
 BitDefender             Keine Probleme bekannt
 Bkav                 !  Berichten "VEX408f.Webshell" (v0.3 bis v0.3c)
 ByteHero                Keine Probleme bekannt
 CAT-QuickHeal           Keine Probleme bekannt
 ClamAV                  Keine Probleme bekannt
 CMC                     Keine Probleme bekannt
 Commtouch            !  Berichten "W32/GenBl.857A3D28!Olympus" (v0.3e einzig)
 Comodo                  Keine Probleme bekannt
 DrWeb                   Keine Probleme bekannt
 Emsisoft                Keine Probleme bekannt
 ESET-NOD32              Keine Probleme bekannt
 F-Prot                  Keine Probleme bekannt
 F-Secure                Keine Probleme bekannt
 Fortinet                Keine Probleme bekannt
 GData                !  Berichten "Archive.Trojan.Agent.E7C7J7" (v0.3e einzig)
 Ikarus               !  Berichten "Trojan.JS.Agent" (v0.3g bis v0.4a)
 Jiangmin                Keine Probleme bekannt
 K7AntiVirus             Keine Probleme bekannt
 K7GW                    Keine Probleme bekannt
 Kaspersky               Keine Probleme bekannt
 Kingsoft                Keine Probleme bekannt
 Malwarebytes            Keine Probleme bekannt
 McAfee                  Keine Probleme bekannt
 McAfee-GW-Edition       Keine Probleme bekannt
 Microsoft               Keine Probleme bekannt
 MicroWorld-eScan        Keine Probleme bekannt
 NANO-Antivirus          Keine Probleme bekannt
 Norman               !  Berichten "Kryptik.BQS" (alle au�er v0.3d und v0.3e)
 nProtect                Keine Probleme bekannt
 Panda                   Keine Probleme bekannt
 Qihoo-360               Keine Probleme bekannt
 Rising                  Keine Probleme bekannt
 Sophos                  Keine Probleme bekannt
 SUPERAntiSpyware        Keine Probleme bekannt
 Symantec             !  Berichten "WS.Reputation.1" (v0.3e bis v0.3g)
 TheHacker               Keine Probleme bekannt
 TotalDefense            Keine Probleme bekannt
 TrendMicro              Keine Probleme bekannt
 TrendMicro-HouseCall !  Berichten "TROJ_GEN.F47V1219" (v0.3d und fr�her)
                      !  Berichten "TROJ_GEN.F47V0312" (v0.3e einzig)
 VBA32                   Keine Probleme bekannt
 VIPRE                   Keine Probleme bekannt
 ViRobot                 Keine Probleme bekannt


                                     ~ ~ ~                                     


Zuletzt Aktualisiert: 4 August 2014
EOF