      _____  _     _  _____  _______ _     _ _______ _______ _______
 <   |_____] |_____| |_____] |  |  | |     | |______ |______ |______ |        >
     |       |     | |       |  |  | |_____| ______| ______| |______ |_____

                            { ~ ~ ~ DEUTSCH ~ ~ ~ }
 INHALT
 1. VORWORT
 2A. INSTALLATION (SERVER)
 2B. INSTALLATION (CLI - BEFEHLSZEILENMODUS)
 3A. BENUTZUNG (SERVER)
 3B. BENUTZUNG (CLI - BEFEHLSZEILENMODUS)
 4A. BROWSER BEFEHLE
 4B. CLI (BEFEHLSZEILENMODUS)
 5. IM PAKET ENTHALTENE DATEIEN
 6. EINSTELLUNGEN
 7. SIGNATURENFORMAT
 8. BEKANNTE KOMPATIBILIT�TSPROBLEME

                                     ~ ~ ~


 1. VORWORT

 Vielen Dank f�r die Benutzung von phpMussel, einem auf PHP basiertem Script,
 um Trojaner, Viren, Malware und andere Bedrohungen in Dateien zu entdecken,
 die auf Ihr System hochgeladen werden k�nnten, welches die Signaturen von
 ClamAV und andere nutzt.

 PHPMUSSEL COPYRIGHT 2013 and beyond GNU/GPL V.2 by Caleb M (Maikuolan).

 Dieses Skript ist freie Software; Sie k�nnen Sie weitergeben und/oder
 modifizieren unter den Bedingungen der GNU General Public License, wie von der
 Free Software Foundation ver�ffentlicht; entweder unter Version 2 der Lizenz
 oder (nach Ihrer Wahl) jeder sp�teren Version. Dieses Skript wird in der
 Hoffnung verteilt, dass es n�tzlich sein wird, allerdings OHNE JEGLICHE
 GARANTIE; ohne implizite Garantien f�r VERMARKTUNG/VERKAUF/VERTRIEB oder F�R
 EINEN BESTIMMTEN ZWECK. Lesen Sie die GNU General Public License f�r weitere
 Details <http://www.gnu.org/licenses/> <http://opensource.org/licenses/>.

 Besonderer Dank geht an ClamAV f�r die Inspiration und die Signaturen, die
 dieses Script benutzt, ohne die dieses Script wahrscheinlich nicht existieren
 w�rde oder bestenfalls einen sehr begrenzten Wert h�tte
 <http://www.clamav.net/>.

 Besonderer Dank auf Sourceforge f�r die hosten der Projektdateien, gefunden
 auf <http://sourceforge.net/projects/phpmussel/>, auf Spambot Security f�r
 die phpMussel Diskussionforen gehostet auf
 <http://www.spambotsecurity.com/forum/viewforum.php?f=55>, und an den
 Lieferanten von die zus�tzliche Anzahl der durch  Signaturen verwendet
 phpMussel: SecuriteInfo.com <http://www.securiteinfo.com/>, PhishTank
 <http://www.phishtank.com/>, NLNetLabs <http://nlnetlabs.nl/> und anderen,
 und Besonderer Dank geht an alle diejenigen die Projekt unterst�tzen werden,
 an andere Personen nicht erw�hnt, und an Sie, f�r die Verwendung des Script.

 Dieses Dokument und das zugeh�rige Paket kann kostenlos von Sourceforge
 heruntergeladen werden <http://sourceforge.net/projects/phpmussel/>.

                                     ~ ~ ~


 2A.INSTALLATION (SERVER)

 Zuf�nftig wird dieser Prozess mit einem Installationsmanager vereinfacht, bis
 dahin folgen Sie den Anweisungen, um phpMussel auf den *meisten Systemen und
 CMS zu installieren:

 1) Entpacken Sie das heruntergeladene Archiv auf Ihren lokalen PC. Erstellen
    Sie ein Verzeichnis, wohin Sie den Inhalt dieses Paketes auf Ihrem Host
    oder CMS installieren m�chten. Ein Verzeichnis wie
    /public_html/phpmussel/ o.�. gen�gt, solange es Ihren
    Sicherheitsbed�rfnissen oder pers�nlichen Pr�ferenzen entspricht.

 2) �ffnen Sie die "phpmussel.php", suchen Sie die Zeile beginnend mit
    "$vault=" und ersetzen Sie den String zwischen den Anf�hrungszeichen mit
    dem exakten Pfad des "vault"-Verzeichnisses von phpMussel. Ein solches
    Verzeichnis werden Sie sicherlich im heruntergeladenen Archiv bemerkt haben
    (sollten Sie das Script recodieren wollen, so m�ssen Sie die Datei- und
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
    wenn irgend eine beliebige Seite Ihres Webauftritts aufgerufen wird) Ihres
    Systems oder CMS mit Hilfe des require- oder include-Befehls einzubinden.
    �blicherweise wird eine solche Datei in Verzeichnissen wie "/includes",
    "/assets" or "/functions" gespeichert und wird h�ufig "init.php",
    "common_functions.php", "functions.php" o.�. genannt. Sie m�ssen
    herausfinden, welche Datei dies f�r Ihre Bed�rfnisse ist. F�gen Sie in
    dieser Datei folgenden Code diret am Anfang ein:

    <?php require("/user_name/public_html/phpmussel/phpmussel.php"); ?>

    Ersetzen Sie den String zwischen den Anf�hrungszeichen mit dem lokalen Pfad
    der Datei "phpmussel.php", nicht mit der HTTP-Adresse (�hnlich dem Pfad f�r
    das "vault"-Verzeichnis). Speichern und schlie�en Sie die Datei, laden Sie
    Sie ggf. erneut hoch.

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


 2B. INSTALLATION (CLI - BEFEHLSZEILENMODUS)

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
    "$vault=" und ersetzen Sie den String zwischen den Anf�hrungszeichen mit
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
    Sie Sie leicht finden k�nnen und f�hren Sie Sie zuk�nfig nur noch mit einem
    Doppelclick aus.

 6) Der Installationsvorgang wurde nun fertiggestellt. Sie sollten nun das
    Programm auf ordnungsgem��e Funktion testen. Um den Test durchzuf�hren,
    f�hren Sie bitte phpMussel aus und versuchen, das Verzeichnis "_testfiles"
    in diesem Installationspaket zu sannen.

                                     ~ ~ ~


 3A. BENUTZUNG (SERVER)

 phpMussel ist daf�r vorgesehen, fast vollst�ndig autonom zu funktionieren,
 ohne dass Sie etwas tun m�ssen: Sobald es installiert ist, f�hrt es die
 T�tigkeiten allein aus.

 Das Scannen von Dateiuploads ist automatisiert und standardm��ig
 eingeschaltet, Sie m�ssen nichts weiter unternehmen.

 Sie sind jedoch auch in der Lage, phpMussel anzuweisen, nach Dateien,
 Ordnern oder Archiven zu scannen, die Sie implizit angeben. Um dies
 auszuf�hren, stellen Sie sicher, dass diese Konfiguration in der phpmussel.ini
 festgelegt ist (Cleanup mu� deaktiviert sein). Erstellen Sie eine mit
 phpMussel eingebundene PHP-Datei mit folgender Funktion:

 phpMussel($what_to_scan,$output_type,$output_flatness);

 - $what_to_scan ist entweder ein String oder ein Array, welches auf eine
   Datei, ein Verzeichnis oder ein Array von Dateien und/oder Verzeichnissen
   zeigt.

 - $output_type ist eine Ganzzahl (Integer), gibt das Format an, wie das
   Ergebnis zur�ckgegeben werden soll. Ein Wert von 0 weist die Funktion an,
   das Ergebnis als Ganzzahl zur�ckzugeben (Integer) (ein R�ckgabewert von -2
   zeigt an, dass besch�digte Dateien gefunden wurden und der Scan nicht
   abgeschlossen wurde, -1 zeigt an, dass fehlende Erweiterungen oder Addons
   von PHP ben�tigt werden, um den Scan durchzuf�hren und der Scan deshalb
   nicht abgeschlossen wurde, 0 zeigt an, dass das Ziel nicht existiert und
   somit nichts �berpr�ft werden konnte, 1 zeigt an, dass das Ziel erfolgreich
   gepr�ft wurde und keine Probleme erkannt wurden, 2 zeigt an, dass das Ziel
   erfolgreich gepr�ft wurde, jedoch Probleme gefunden wurden).
   Ein Wert von 1 weist die Funktion an, die Ergebnisse als lesbaren Text
   auszugeben.
   Ein Wert von 2 weist die Funktion an, beides auszugeben, einen lesbaren Text
   und einen Export in eine globale Variable.
   Diese Variable ist optional, Standardeinstellung ist 0.

 - $output_flatness ist eine Ganzzahl (Integer), weist die Funktion an, das
   Ergebnis als Array oder String auszugeben. Enth�lt das Ziel mehrere Elemente
   (wie z.B. Verzeichnisse oder Arrays), wird das Ergebnis als Array
   zur�ckgegeben (Standardeinstellung 0). Ein Wert von 1 weist die Funktion an,
   das Ergebnis als verketteten String zuruckzugeben.
   Diese Variable ist optional, Standardeinstellung ist 0.

 Beispiel:

   $results=phpMussel("/user_name/public_html/my_file.html",1,1);
   echo $results;

   Gibt so etwas wie dies (als eine String):
    Wed, 16 Sep 2013 02:49:46 +0000 Gestartet.
    > �berpr�fung '/user_name/public_html/my_file.html':
    -> Keine Probleme gefunden.
    Wed, 16 Sep 2013 02:49:47 +0000 Fertig.

 Eine vollst�ndige Liste der Signaturen, die phpMussel nutzt und wie diese
 verarbeitet werden, finden Sie im Abschnitt SIGNATURENFORMAT.

 Sollten irgendwelche Fehlalarme auftreten, Sie etwas entdecken, was Ihrer
 Meinung nach blockiert werden sollte oder etwas mit den Signaturen nicht
 funtionieren, so informieren Sie den Autor, damit die erforderlichen
 �nderungen durchgef�hrt werden k�nnen.

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
 festgestellt, gibt die Funktion den Wert 0 zur�ck.
 Sollte etwas festgestellt werden, gibt die Funktion einen String mit einer
 Nachricht, was gefunden wurde, zur�ck.

 Sollten Sie die Quelltexte betrachten, werden Sie die Funktionen phpMusselD()
 und phpMusselR() auffinden. Diese Funktionen sind Subroutinen der phpMussel()
 und sollten nicht au�erhalb der �bergeordneten Funktion aufgerufen werden
 (nicht wegen der Nebeneffekte, Sie h�tten allein ausgef�hrt einfach nur keinen
 Zweck und w�rden nicht korrekt ausgef�hrt werden).

 Es gibt noch viele weitere Funktionen und Steuerm�glichkeiten in phpMussel f�r
 Ihren Einsatzzweck. F�r andere Funktionen und Steuerm�glichkeiten, die hier
 nicht aufgelistet sind, lesen Sie bitte den Abschnitt BROWSER BEFEHLE.

                                     ~ ~ ~


 3B. BENUTZUNG (CLI - BEFEHLSZEILENMODUS)

 Bitte lesen Sie den Abschnitt INSTALLATION (CLI - BEFEHLSZEILENMODUS).

 Bedenken Sie, dass zuk�nftige Versionen von phpMussel andere Systeme
 unterst�tzen werden, zur Zeit jedoch phpMussel im CLI-Modus nur f�r
 Windows-Systeme optimiert wurde (Sie k�nnen nat�rlich versuchen, phpMussel
 auf anderen Systemen zu installieren, jedoch wird nicht garantiert, dass es
 wie vorgesehen funktioniert).

 Beachten Sie au�erdem, dass phpMussel keine vollst�ndige Antiviren-Software
 ersetzt, nicht den aktiven Speicher �berwacht oder Viren spontan erkennt! Es
 erkennt nur Viren in den Dateien, die Sie explizit zum Scannen angegeben
 haben.

                                     ~ ~ ~


 4A. BROWSER BEFEHLE

 Ist phpMussel auf Ihren System installiert und funktioniert ordnungsgem��,
 sind Sie in de Lage, einige Verwaltungsfunktionen und Befehle an phpMussel
 �ber Ihren Browser zu �bergeben, sofern Sie die Variablen script_password und
 logs_password in Ihrer Konfigurationsdatei gesetzt haben. Diese Passw�rter
 m�ssen zum Aktivieren dieser Kontrollen gesetzt werden, um eine gr��t m�gliche
 Sicherheit zu erlangen, die browserbasierten Kontrollen zu sch�tzen und um
 daf�r zu sorgen, dass diese browserbasierten Kontrollen vollst�ndig
 deaktiviert werden k�nnen, wenn Sie nicht von Ihnen, dem Webmaster oder den
 Administratoren ben�tigt werden. Zum Aktivieren dieser Kontrollm�glichkeiten
 wird ein Passwort vergeben, zum Deaktivieren wird kein Passwort vergeben.
 Alternativ k�nnen Sie diese Kontrollen aktivieren und zu einem sp�teren
 Zeitpunkt mit einem Befehl deaktivieren (z.B. wenn Sie Aktionen durchf�hren
 m�ssen und bef�rchten, dass Ihr Passwort ausgelesen werden kann, so k�nnen Sie
 die Kontrollen schnell deaktivieren ohne die Konfigurationsdatei zu
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
   Zweck: Deaktiviert ("locks out") alle browser-basierten Kontrollen.
          Diese Funktion sollte benutzt werden, wenn Sie bef�rchten, dass Ihr
          Passwort kompromittiert wurde (dies ist m�glich, wenn Sie die
          Kontrollen von einem Computer aus benutzen, der nicht abgesichert
          oder dem nicht vertraut werden kann). controls_lockout erstellt die
          Datei controls.lck im Verzeichnis "vault", wonach phpMussel zuerst
          sucht, befor es Aktionen ausf�hrt. Wurden die Kontrollen deaktiviert,
          m�ssen Sie die Datei controls.lck manuell mittels FTP o.�. l�schen.
          Kann mit jedem Passwort aufgerufen werden.
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
   Optionale Parameter: (keine)
   Beispiele: ?pword=[script_password]&phpmussel=update
   ~
   Zweck: Sucht nach Aktualisierungen f�r phpMussel und Signaturen.
          War die Suche erfolgreich und Aktualisierungen sind verf�gbar, so
          werden diese heruntergeladen und installiert. Schl�gt die Suche fehl,
          wird der Vorgang abgebrochen. Die Ergebnisse des gesamten Vorgangs
          werden ausgegeben. Es wird empfohlen, mindestens einmal monatlich
          nach Aktualisierungen zu suchen, um sicherzustellen, dass die
          Signaturen und Ihre Kopie von phpMussel auf dem neuesten Stand sind.
          Eine h�ufigere Suche nach Aktualisierungen ist fruchtlos, da die
          entsprechenden Pakete meist monatlich eingestellt werden.
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


 4B. CLI (BEFEHLSZEILENMODUS)

 phpMussel kann als interactiver Scanner im CLI-Modus in einer
 Windows-Systemumgebung genutzt werden. Bitte lesen Sie den Abschnitt
 INSTALLATION (CLI - BEFEHLSZEILENMODUS).

 Um eine Liste der verf�gbaren CLI-Befehle zu erhalten, geben Sie in der
 Befehlszeile 'c' ein und best�tigen mit Enter.

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
    Verzeichnis f�r die Dokumentationen (beinhaltet verschiedene Dateien).
    ~
 /_docs/change_log.txt (Dokumentation, enthalten)
    Eine Auflistung der �nderungen des Scripts der verschiedenen Versionen (f�r
    die korrekte Funktion des Scripts nicht notwendig).
    ~
 /_docs/readme.DE.txt (Dokumentation, enthalten); DEUTSCH
 /_docs/readme.EN.txt (Dokumentation, enthalten); ENGLISH
 /_docs/readme.ES.txt (Dokumentation, enthalten); ESPA�OL
 /_docs/readme.FR.txt (Dokumentation, enthalten); FRAN�AIS
 /_docs/readme.ID.txt (Dokumentation, enthalten); BAHASA INDONESIA
 /_docs/readme.IT.txt (Dokumentation, enthalten); ITALIANO
 /_docs/readme.NL.txt (Dokumentation, enthalten); NEDERLANDSE
 /_docs/readme.PT.txt (Dokumentation, enthalten); PORTUGU�S
    Die README-Dateien (z.B. die Datei, die Sie gerade lesen).
    ~
 /_docs/signatures_tally.txt (Dokumentation, enthalten)
    Verschiebung-Tally von Signaturen enthalten (f�r die korrekte Funktion des
    Scripts nicht notwendig).
    ~
 /_testfiles/ (Verzeichnis)
    Verzeichnis f�r Testdateien (beinhaltet verschiedene Dateien).
    Alle enthaltenen Dateien dienen zur �berpr�fung, ob phpMussel auf Ihrem
    System ordnungsgem�� installiert wurde. Sie m�ssen dieses Verzeichnis oder
    die Dateien nicht hochladen, sofern Sie keinen solchen Test durchf�hren
    m�chten.
    ~
 /_testfiles/ascii_standard_testfile.txt (Testdatei, enthalten)
    Testdatei zur �berpr�fung der normierten ASCII-Signaturerkennung.
    ~
 /_testfiles/coex_testfile.rtf (Testdatei, enthalten)
    Testdatei zur �berpr�fung der Komplex-Erweitert-Signaturerkennung.
    ~
 /_testfiles/exe_standard_testfile.exe (Testdatei, enthalten)
    Testdatei zur �berpr�fung der PE-Signaturerkennung.
    ~
 /_testfiles/general_standard_testfile.txt (Testdatei, enthalten)
    Testdatei zur �berpr�fung der Erkennung der allgemeinen Signaturen.
    ~
 /_testfiles/graphics_standard_testfile.gif (Testdatei, enthalten)
    Testdatei zur �berpr�fung der Grafik-Signaturerkennung.
    ~
 /_testfiles/html_standard_testfile.txt (Testdatei, enthalten)
    Testdatei zur �berpr�fung der normierten HTML-Signaturerkennung.
    ~
 /_testfiles/md5_testfile.txt (Testdatei, enthalten)
    Testdatei zur �berpr�fung der MD5-Signaturerkennung.
    ~
 /_testfiles/metadata_testfile.txt.gz (Testdatei, enthalten)
    Testdatei zur �berpr�fung der Metadata-Signaturerkennung und zur
    �berpr�fung der GZ-Archivunterst�tzung Ihres Systems.
    ~
 /_testfiles/metadata_testfile.zip (Testdatei, enthalten)
    Testdatei zur �berpr�fung der Metadata-Signaturerkennung und zur
    �berpr�fung der ZIP-Archivunterst�tzung Ihres Systems.
    ~
 /_testfiles/ole_testfile.ole (Testdatei, enthalten)
    Testdatei zur �berpr�fung der OLE-Signaturerkennung.
    ~
 /_testfiles/pdf_standard_testfile.pdf (Testdatei, enthalten)
    Testdatei zur �berpr�fung der PDF-Signaturerkennung.
    ~
 /_testfiles/pe_sectional_testfile.exe (Testdatei, enthalten)
    Testdatei zur �berpr�fung der PE-Sectional-Signaturerkennung.
    ~
 /_testfiles/xdp_standard_testfile.xdp (Testdatei, enthalten)
    Testdatei zur �berpr�fung der XML/XDP-St�cke-Signaturen.
    ~
 /vault/ (Verzeichnis)
    Vault-Verzeichnis (beinhaltet verschiedene Dateien).
    ~
 /vault/quarantine/ (Verzeichnis)
    Quarant�ne-Verzeichnis (enth�lt Dateien in Quarant�ne).
    ~
 /vault/quarantine/.htaccess (Sonstiges, enthalten)
    Ein hypertext access file (in diesem Fall zum Schutz von sensiblen Dateien
    des Scripts vor einem nicht authorisierten Zugriff).
    ~
 /vault/.htaccess (Sonstiges, enthalten)
    Ein hypertext access file (in diesem Fall zum Schutz von sensiblen Dateien
    des Scripts vor einem nicht authorisierten Zugriff).
    ~
 /vault/ascii_clamav_regex.cvd (Signaturen, enthalten)
 /vault/ascii_clamav_regex.map (Signaturen, enthalten)
 /vault/ascii_clamav_standard.cvd (Signaturen, enthalten)
 /vault/ascii_clamav_standard.map (Signaturen, enthalten)
 /vault/ascii_custom_regex.cvd (Signaturen, enthalten)
 /vault/ascii_custom_standard.cvd (Signaturen, enthalten)
 /vault/ascii_mussel_regex.cvd (Signaturen, enthalten)
 /vault/ascii_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der normierten ASCII-Signaturen.
    Ben�tigt, wenn die Option "ASCII Signatures" in der phpmussel.ini aktiviert
    ist. Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist.
    ~
 /vault/coex_clamav.cvd (Signaturen, enthalten)
 /vault/coex_custom.cvd (Signaturen, enthalten)
 /vault/coex_mussel.cvd (Signaturen, enthalten)
    Dateien der Komplex-Erweitert-Signaturen.
    Ben�tigt, wenn die Option "Complex Extended" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist.
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
    Ben�tigt, wenn die Option "ELF Signatures" in der phpmussel.ini aktiviert
    ist. Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist.
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
    Ben�tigt, wenn die Option "EXE Signatures" in der phpmussel.ini aktiviert
    ist. Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist.
    ~
 /vault/filenames_clamav.cvd (Signaturen, enthalten)
 /vault/filenames_custom.cvd (Signaturen, enthalten)
 /vault/filenames_mussel.cvd (Signaturen, enthalten)
    Dateien der Dateinamen-Signaturen.
    Ben�tigt, wenn die Option "Filename Signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist.
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
    Ben�tigt, wenn die Option "General Signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist.
    ~
 /vault/graphics_clamav_regex.cvd (Signaturen, enthalten)
 /vault/graphics_clamav_regex.map (Signaturen, enthalten)
 /vault/graphics_clamav_standard.cvd (Signaturen, enthalten)
 /vault/graphics_clamav_standard.map (Signaturen, enthalten)
 /vault/graphics_custom_regex.cvd (Signaturen, enthalten)
 /vault/graphics_custom_standard.cvd (Signaturen, enthalten)
 /vault/graphics_mussel_regex.cvd (Signaturen, enthalten)
 /vault/graphics_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der Signaturen f�r Bilddateien.
    Ben�tigt, wenn die Option "Graphics Signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist.
    ~
 /vault/greylist.csv (Signaturen, enthalten/wird erstellt)
    CSV der Signaturen in der Greylist, die phpMussel ignorieren soll (Datei
    wird nach dem L�schen automatisch neu erstellt).
    ~
 /vault/hex_general_commands.csv (Signaturen, enthalten)
    Hex-codierte CSV mit allgemeinen Befehlserkennung.
    Ben�tigt, wenn die Option "General Command Detection" in der phpmussel.ini
    aktiviert ist. Die Datei kann entfernt werden, wenn die Option deaktiviert
    ist.
    ~
 /vault/html_clamav_regex.cvd (Signaturen, enthalten)
 /vault/html_clamav_regex.map (Signaturen, enthalten)
 /vault/html_clamav_standard.cvd (Signaturen, enthalten)
 /vault/html_clamav_standard.map (Signaturen, enthalten)
 /vault/html_custom_regex.cvd (Signaturen, enthalten)
 /vault/html_custom_standard.cvd (Signaturen, enthalten)
 /vault/html_mussel_regex.cvd (Signaturen, enthalten)
 /vault/html_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der normierten HTML-Signaturen.
    Ben�tigt, wenn die Option "HTML Signatures" in der phpmussel.ini aktiviert
    ist. Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist.
    ~
 /vault/lang.inc (Script, enthalten)
    Sprachpaket f�r phpMussel; Erforderlich f�r Unterst�tzung mehrerer
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
    Ben�tigt, wenn die Option "Mach-O Signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist.
    ~
 /vault/mail_clamav_regex.cvd (Signaturen, enthalten)
 /vault/mail_clamav_regex.map (Signaturen, enthalten)
 /vault/mail_clamav_standard.cvd (Signaturen, enthalten)
 /vault/mail_clamav_standard.map (Signaturen, enthalten)
 /vault/mail_custom_regex.cvd (Signaturen, enthalten)
 /vault/mail_custom_standard.cvd (Signaturen, enthalten)
 /vault/mail_mussel_regex.cvd (Signaturen, enthalten)
 /vault/mail_mussel_standard.cvd (Signaturen, enthalten)
 /vault/mail_mussel_standard.map (Signaturen, enthalten)
    Signaturdateien f�r die Funktion phpMussel_mail().
    Dateien werden auf jeden Fall von der Funktion phpMussel_mail() ben�tigt.
    Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist.
    ~
 /vault/md5_clamav.cvd (Signaturen, enthalten)
 /vault/md5_custom.cvd (Signaturen, enthalten)
 /vault/md5_mussel.cvd (Signaturen, enthalten)
    Dateien der MD5-signaturen.
    Ben�tigt, wenn die Option "MD5" in der phpmussel.ini aktiviert ist.
    Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist.
    ~
 /vault/metadata_clamav.cvd (Signaturen, enthalten)
 /vault/metadata_custom.cvd (Signaturen, enthalten)
 /vault/metadata_mussel.cvd (Signaturen, enthalten)
    Dateien f�r die Signaturen der Archiv-Metadaten.
    Ben�tigt, wenn die Option "Archive Metadata Signatures" in der
    phpmussel.ini aktiviert ist. Die Dateien k�nnen entfernt werden, wenn
    die Option deaktiviert ist.
    ~
 /vault/ole_clamav_regex.cvd (Signaturen, enthalten)
 /vault/ole_clamav_regex.map (Signaturen, enthalten)
 /vault/ole_clamav_standard.cvd (Signaturen, enthalten)
 /vault/ole_clamav_standard.map (Signaturen, enthalten)
 /vault/ole_custom_regex.cvd (Signaturen, enthalten)
 /vault/ole_custom_standard.cvd (Signaturen, enthalten)
 /vault/ole_mussel_regex.cvd (Signaturen, enthalten)
 /vault/ole_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der OLE-Signaturen.
    Ben�tigt, wenn die Option "OLE Signatures" in der phpmussel.ini aktiviert
    ist. Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist.
    ~
 /vault/pdf_clamav_regex.cvd (Signaturen, enthalten)
 /vault/pdf_clamav_regex.map (Signaturen, enthalten)
 /vault/pdf_clamav_standard.cvd (Signaturen, enthalten)
 /vault/pdf_clamav_standard.map (Signaturen, enthalten)
 /vault/pdf_custom_regex.cvd (Signaturen, enthalten)
 /vault/pdf_custom_standard.cvd (Signaturen, enthalten)
 /vault/pdf_mussel_regex.cvd (Signaturen, enthalten)
 /vault/pdf_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der PDF-Signaturen.
    Ben�tigt, wenn die Option "PDF Signatures" in der phpmussel.ini aktiviert
    ist. Die Dateien k�nnen entfernt werden, wenn die Option deaktiviert ist
    (Dateien werden bei einem Update neu erstellt).
    ~
 /vault/pe_clamav.cvd (Signaturen, enthalten)
 /vault/pe_custom.cvd (Signaturen, enthalten)
 /vault/pe_mussel.cvd (Signaturen, enthalten)
    Dateien der PE-Sectional-Signatures.
    Ben�tigt, wenn die Option "PE Sectional signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist.
    ~
 /vault/phpmussel.inc (Script, enthalten)
    phpMussel Core Script (absolut notwendig)!
    ~
 /vault/phpmussel.ini (Sonstiges, enthalten)
    phpMussel Konfigurationsdatei; beinhaltet alle Konfigurationsm�glichkeiten
    von phpMussel (absolut notwendig)!
    ~
 /vault/scan_log.txt *(Logfile, wird erstellt)
    Eine Aufzeichnung aller von phpMussel gescanten Objekte.
    ~
 /vault/scan_kills.txt *(Logfile, wird erstellt)
    Eine Aufzeichnung aller von phpMussel blockierten Dateiuploads.
    ~
 /vault/swf_clamav_regex.cvd (Signaturen, enthalten)
 /vault/swf_clamav_regex.map (Signaturen, enthalten)
 /vault/swf_clamav_standard.cvd (Signaturen, enthalten)
 /vault/swf_clamav_standard.map (Signaturen, enthalten)
 /vault/swf_custom_regex.cvd (Signaturen, enthalten)
 /vault/swf_custom_standard.cvd (Signaturen, enthalten)
 /vault/swf_mussel_regex.cvd (Signaturen, enthalten)
 /vault/swf_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der Shockwave-Signaturen.
    Ben�tigt, wenn die Option "Shockwave Signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist.
    ~
 /vault/switch.dat (Other, Included)
    Diese Datei definiert bestimmte Variablen.
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
    phpMussel Update Script; Wird nur f�r die automatische manuelle
    Aktualisierung mittels Browser ben�tigt.
    ~
 /vault/whitelist_clamav.cvd (Signaturen, enthalten)
 /vault/whitelist_custom.cvd (Signaturen, enthalten)
 /vault/whitelist_mussel.cvd (Signaturen, enthalten)
    Datei-spezifische Whitelist.
    Ben�tigt, wenn die Option "Whitelist" in der phpmussel.ini aktiviert ist,
    und wenn Sie auf bestimmte Dateien Whitelist haben m�chten. Die Dateien
    k�nnen entfernt werden, wenn die Option deaktiviert ist.
    ~
 /vault/xmlxdp_clamav_regex.cvd (Signaturen, enthalten)
 /vault/xmlxdp_clamav_regex.map (Signaturen, enthalten)
 /vault/xmlxdp_clamav_standard.cvd (Signaturen, enthalten)
 /vault/xmlxdp_clamav_standard.map (Signaturen, enthalten)
 /vault/xmlxdp_custom_regex.cvd (Signaturen, enthalten)
 /vault/xmlxdp_custom_standard.cvd (Signaturen, enthalten)
 /vault/xmlxdp_mussel_regex.cvd (Signaturen, enthalten)
 /vault/xmlxdp_mussel_standard.cvd (Signaturen, enthalten)
    Dateien der XML/XDP-St�cke-Signaturen.
    Ben�tigt, wenn die Option "XML/XDP-Chunk Signatures" in der phpmussel.ini
    aktiviert ist. Die Dateien k�nnen entfernt werden, wenn die Option
    deaktiviert ist.
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
    nutzt diese Listen, um den Scanvorgang zu beschleunigen (der sonst recht
    langsam und ressourcenaufw�ndig w�re).
    ~
    Signaturdateien mit der Kennzeichnung "_regex" enthalten Signaturen,
    welche regul�re Ausdrucke verwenden (regex).
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

 "general" (Kategorie)
 - generelle Konfiguration von phpMussel.
    "script_password"
    - Als Komfort-Funktion erm�glicht es phpMussel, einige Funktionen
      (inkl. des schnellen Updates) manuell via POST, GET und QUERY auszul�sen.
      Um sicherzustellen, dass diese Anfrage auch nur von Ihnen und keinem
      anderen abgeschickt wurde, erwartet phpMussel das Passwort innerhalb der
      Anfrage. Setzen Sie das script_password nach Belieben, w�hlen Sie ein
      Passwort, das Sie sich leicht merken k�nnen, aber f�r andere schwer zu
      erraten ist. Ist kein Passwort vergeben, sind die manuellen Anfragen
      deaktiviert.
      * Kein Einfluss im CLI-Modus.
    "logs_password"
    - Wie script_password, allerdings nur zur Ausgabe des Inhalts von scan_log
      und scan_kills. Separate Passworte sind n�tzlich, wenn Sie jemandem
      Zugang zur einen Funktionalit�t gew�hren wollen, aber nicht zur anderen.
      * Kein Einfluss im CLI-Modus.
    "cleanup"
    - L�scht die Scriptvariablen und den Cache nach der Ausf�hrung. Sollten Sie
      das Script nach der �berpr�fung des Uploads nicht mehr nutzen, stellen
      Sie diese Option auf "yes", um die Speichernutzung zu minimieren.
      Verwenden Sie das Script noch f�r weitere Zwecke, stellen Sie die Option
      auf "no", um unn�tiges mehrfaches Einlesen der Daten in den Speicher zu
      vermeiden. Normalerweise sollte diese Option auf "yes" gesetzt werden,
      allerdings k�nnen Sie das Script dann nur zur Datei�berpr�fung verwenden.
      * Kein Einfluss im CLI-Modus.
    "scan_log"
    - Name einer Datei zum Aufzeichnen aller Resultate von �berpr�fungen. Geben
      Sie einen Dateinamen an oder lassen Sie die Option zum Deaktivieren leer.
    "scan_kills"
    - Name einer Datei zum Aufzeichnen aller blockierten Uploads. Geben Sie
      einen Dateinamen an oder lassen Sie die Option zum Deaktivieren leer.
    "ipaddr"
    - Ort der IP-Adresse der aktuellen Verbindung im gesamten Datenstrom
      (n�tzlich f�r Cloud-Services) Standardeinstellung = REMOTE_ADDR
      Achtung: �ndern Sie diesen Wert nur, wenn Sie wissen, was Sie tun!
    "forbid_on_block"
    - Zur�ckgegebener 403-HTTP-Header bei einem blockierten Dateiupload.
      0 = Nein (200) [Standardeinstellung], 1 Ja (403).
    "delete_on_sight"
    - Diese Option weist das Script an, Dateien w�hrend eines Scans sofort
      zu l�schen, wenn ein Erkennungsmerkmal, ob durch Signaturen oder
      andere Methoden, zutrifft. Dateien, die als nicht infiziert eingestuft
      werden, werden nicht ber�hrt. Im Falle von Archiven wird das gesamte
      Archiv gel�scht, auch wenn nur eine einzige Datei im Archiv infiziert
      sein sollte. Normalerweise ist es bei einem Dateiupload nicht notwendig,
      diese Option zu aktivieren, da PHP nach der Ausf�hrung von Scripten den
      Inhalt vom Cache l�scht, d.h. PHP l�scht jede Datei, die �ber den Server
      hochgeladen wird, sofern Sie nicht verschoben, kopiert oder bereits
      gel�scht wurde. Diese Option wurde als zus�tzliches Ma� an Sicherheit
      hinzugef�gt, au�erdem f�r Systeme, deren PHP-Installation nicht dem
      �blichen Verhalten entspricht.
      0 - Nach der �berpr�fung wird die Datei so belassen
          [Standardeinstellung],
      1 - Nach der �berpr�fung wird die Datei sofort gel�scht, sofern Sie
          infiziert ist.
    "lang"
    - Gibt die Standardsprache f�r phpMussel an.
    "quarantine_key"
    - phpMussel ist in der Lage, Versuche von Datei-Uploads in einem
      Quarant�ne-Verzeichnis zu isolieren, sofern Sie dies tun wollen. Nutzer,
      die nur daran interessiert sind, ihre Webauftritte oder ihre
      Hosting-Umgebung zu sch�tzen ohne das Interesse, die markierten Dateien
      weitergehend zu untersuchen, sollten diese Funktionalit�t deaktivieren,
      Nutzer, die diese Dateien zur Ananlyse auf Maleware o.�. ben�tigen,
      sollten diese Funktion aktivieren. Die Isolation von markierten Dateien
      kann manchmal auch bei der Fehlersuche von Fehlalarmen helfen, wenn dies
      h�ufiger bei Ihnen auftritt. Um die Quarant�nefunktion zu deaktivieren,
      lassen Sie die Richtlinie "quarantine_key" leer oder l�schen Sie den
      Inhalt dieser Richtlinie, wenn sie nicht bereits leer ist. Um die
      Quarant�nefunktion zu aktivieren, geben Sie einen Wert ein. Der
      "quarantine_key" ist ein wichtiges Sicherheitsmerkmal der
      Quarant�nfunktionen, um zu verhindern, dass die Quarant�nefunktionen
      einem Exploit ausgesetzt wird und gespeicherte Daten in der
      Quarant�neumgebung ausgef�hrt werden k�nnen. Der Wert des
      "quarantine_key" sollte so behandelt werden, wie Ihre Passw�rter: Je
      l�nger, desto besser, und halten Sie sie geheim. Optimal in Verbindung
      mit "delete_on_sight".
    "quarantine_max_filesize"
    - Die maximal zul�ssige Dateigr��e von Dateien, die in der Quarant�ne
      isoliert werden sollen. Dateien, die gr��er sind als der angegebene Wert,
      werden NICHT im Quarant�neverzeichnis gespeichert. Diese Richtlinie ist
      wichtig, um es einem potentiellen Angreifer zu erschweren, die Quarant�ne
      -und somit Ihren zugesicherten Speicher auf Ihrem Hostservice- mit
      unerw�nschten Daten zu �berfluten. Wert in KB.
      Standardeinstellung =2048 =2048KB =2MB.
    "quarantine_max_usage"
    - Die maximal zul�ssige Speichernutzung der Quarant�ne. Erreicht die
      Geamtgr��e der Dateien in der Quarant�ne diesen Wert, werden die �ltesten
      Dateien in der Quarant�ne gel�scht, bis der Wert unterschritten wird.
      Diese Richtlinie ist wichtig, um es einem potentiellen Angreifer zu
      erschweren, die Quarant�ne -und somit Ihren zugesicherten Speicher auf
      Ihrem Hostservice- mit unerw�nschten Daten zu �berfluten. Wert in KB.
      Standardwert =65536 =65536KB =64MB.
    "honeypot_mode"
    - Ist der Honeypot-Modus aktiviert, wird phpMussel jede Datei aus dem
      Dateiupload isolieren, ohne R�cksicht darauf zu nehmen, ob diese Dateien
      Signaturen enthalten, es findet auch keine weitere �berpr�fung statt.
      Diese Funktionalit�t dient ausschlie�lich dem Zweck der Viren
      -und Malewareforschung, es wird ausdr�cklich nicht empfohlen, phpMussel
      mit dieser Funktion zum Zwecke der Datei�berpr�fung von Uploads oder
      anderen Zwecken au�er "Honeypotting" zu verwenden. Standardm��ig ist
      diese Funktion deaktiviert.
      0 = Deativiert [Standardwert], 1 = Aktiviert.
 "signatures" (Kategorie)
 - Konfiguration der Signaturen.
   %%%_clamav = ClamAV-Signaturen (generelle Signaturen und t�gliche Updates).
   %%%_custom = Ihre eigenen Signaturen (sofern Sie welche erstellt haben).
   %%%_mussel = phpMussel-Signaturen, nicht aus der ClamAV-Datenbank.
   - Scan mit den MD5-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "md5_clamav"
     "md5_custom"
     "md5_mussel"
   - Scan mit den generellen Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "general_clamav"
     "general_custom"
     "general_mussel"
   - Scan mit den normierten ASCII Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "ascii_clamav"
     "ascii_custom"
     "ascii_mussel"
   - Scan mit den normierten HTML Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "html_clamav"
     "html_custom"
     "html_mussel"
   - Scan von PE-Dateien (Portable Executable, EXE, DLL, etc.)
     mit den PE-Sectional-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "pe_clamav"
     "pe_custom"
     "pe_mussel"
   - Scan von PE-Dateien (Portable Executable, EXE, DLL, etc.)
     mit den PE-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "exe_clamav"
     "exe_custom"
     "exe_mussel"
   - Scan von ELF-Dateien mit den ELF-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "elf_clamav"
     "elf_custom"
     "elf_mussel"
   - Scan von Mach-O-Dateien (OSX, etc.) mit den Mach-O-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "macho_clamav"
     "macho_custom"
     "macho_mussel"
   - Scan von Bilddateien mit den Grafik-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "graphics_clamav"
     "graphics_custom"
     "graphics_mussel"
   - Scan von Archivinhalten mit den Archiv-Metadata-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "metadata_clamav"
     "metadata_custom"
     "metadata_mussel"
   - Scan von OLE-Objekten mit den OLE-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "ole_clamav"
     "ole_custom"
     "ole_mussel"
   - Scan von Dateinamen mit den Dateinamen-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "filenames_clamav"
     "filenames_custom"
     "filenames_mussel"
   - Scan mit phpMussel_mail()? 0 = Nein, 1 = Ja [Standardeinstellung].
     "mail_clamav"
     "mail_custom"
     "mail_mussel"
   - Aktivieren Datei-spezifische Whitelist?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "whitelist_clamav"
     "whitelist_custom"
     "whitelist_mussel"
   - Scan von XML/XDP-St�cke mit den XML/XDP-St�cke-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "xmlxdp_clamav"
     "xmlxdp_custom"
     "xmlxdp_mussel"
   - Scan mit der Komplex-Erweitert-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "coex_clamav"
     "coex_custom"
     "coex_mussel"
   - Scan mit der PDF-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "pdf_clamav"
     "pdf_custom"
     "pdf_mussel"
   - Scan mit der Shockwave-Signaturen?
     0 = Nein, 1 = Ja [Standardeinstellung].
     "swf_clamav"
     "swf_custom"
     "swf_mussel"
   - Optionen f�r das Gr��enlimit der �bereinstimmungen. �ndern Sie diese Werte
     nur, wenn Sie wissen, was Sie tun. SD = Standardsignaturen. RX = PCRE
     (Perl Compatible Regular Expressions, bzw. "Regex")-Signaturen.
     FN = Dateinamen-Signaturen. Sollten Sie bemerken, dass PHP abst�rzt, wenn
     phpMussel aktiv wird, setzen Sie die "max"-Werte herab. Informieren Sie
     den Autor, was passiert ist und melden Sie die Ergebnisse Ihrer Versuche
     und Bem�hungen.
     "fn_siglen_min"
     "fn_siglen_max"
     "rx_siglen_min"
     "rx_siglen_max"
     "sd_siglen_min"
     "sd_siglen_max"
   - Reaktion von phpMussel auf fehlende oder defekte Signaturen.
     Ist fail_silently deaktiviert, werden fehlende oder defekte Signaturen
     w�hrend des Scanvorgangs gemeldet, ist fail_silently aktiviert, werden
     fehlende oder defekte Signaturen ignoriert, ohne dass entsprechende
     Probleme gemeldet werden. Diese Option sollte so belassen werden, es sei
     denn, Sie erwarten Abst�rze oder �hnliches.
     0 = Deaktiviert, 1 = Aktiviert [Standardeinstellung].
     "fail_silently"
 "files" (Kategorie)
 - Generelle Konfigurationen f�r die Handhabung von Dateien.
   "max_uploads"
   - Maximale erlaubte Anzahl zu �berpr�fender Dateien w�hrend eines
     Dateiuploads bevor der Scan abgebrochen und der Nutzer dar�ber informiert
     wird, dass er zu viele Dateien auf einmal hochgeladen hat. Bietet einen
     Schutz gegen den theoretischen Angriff eines DDoS auf Ihr System oder CMS,
     indem der Angreifer phpMussel �berlastet und den PHP-Prozess zum
     Stillstand bringt. Empfohlen: 10. Sie k�nnen den Wert abh�ngig von Ihrer
     Hardware erh�hen oder senken. Beachten Sie, dass dieser Wert nicht den
     Inhalt von Archiven ber�cksichtigt.
   "filesize_limit"
   - Begrenzung der Dateigr��e in KB. 65536 = 64MB [Standardeinstellung],
     0 = Keine Begrenzung (wird immer zur Greylist hinzugef�gt), jeder
     (positive) numerische Wert wird akzeptiert. Dies ist n�tzlich, wenn Ihre
     PHP-Konfiguration den verf�gbaren Speicherverbrauch je Prozess einschr�nkt
     oder die Dateigr��e von Uploads begrenzt.
   "filesize_response"
   - Handhabung von Dateien, die die Begrenzung der Dateigr��e (sofern
     angegeben) �berschreiten.
     0 - hinzuf�gen zur Whitelist,
     1 - hinzuf�gen zur Blacklist [Standardeinstellung].
   "filetype_whitelist", "filetype_blacklist", "filetype_greylist"
   - Sofern Ihr System spezielle Dareitypen im Upload erlaubt oder komplett
     verweigert, so unterteilen Sie diese Dateitypen in Whitelists, Blacklists
     oder Greylists, um den Scanvorgang zu beschleunigen, indem diese
     Dateitypen �bersprungen werden. Format ist CSV (comma separated values,
     Komma-getrennte Werte). M�chten Sie lieber alles �berpr�fen lassen, so
     lassen Sie die Variable(n) leer; Dies deaktiviert die
     Whitelist/Blacklist/Greylist. Logische Reihenfolge der Verarbeitung ist:
     - Wenn der Dateityp ist in die Whitelist, tun nicht scannen und tun nicht
       blockieren die Datei, und tun nicht �berpr�fen wenn die Datei ist in die
       Whitelist oder die Greylist.
     - Wenn der Dateityp ist in die Blacklist, tun nicht scannen die Datei aber
       blockieren es trotzdem, und tun nicht �berpr�fen wenn die Datei ist in
       die Greylist.
     - Wenn die Greylist leer ist oder wenn die Greylist nicht leer ist und der
       Dateityp ist in die Greylist, scannen die Datei wie f�r normale und
       festzustellen, ob es zu blockieren, basierend auf den Scan, aber wenn
       die Greylist nicht leer ist und der Dateityp nicht ist in die Greylist,
       behandeln die Datei als ob es ist in die Blacklist, nicht scannen es
       aber blockierung es trotzdem.
   "check_archives"
   - Soll der Inhalt von Archiven �berpr�ft werden?
     0 - Nein (keine �berpr�fung),
     1 - Ja (wird �berpr�ft) [Standardeinstellung].
     * Zur Zeit wird NUR die �berpr�fung von BZ, GZ, LZF und ZIP Archiven
       unterst�tzt (�berpr�fung von RAR, CAB, 7z usw. wird zur Zeit NICHT
       unterst�tzt).
     * Diese Funktion ist nicht sicher! Es wird dringend empfohlen, diese
       Funktion aktiviert zu lassen, es kann jedoch nicht garantiert werden,
       dass alles entdeckt wird.
     * Die Archiv�berpr�fung ist derzeit nicht rekursiv f�r ZIP-Archive.
   "filesize_archives"
   - Soll das Blacklisting/Whitelisting der Dateigr��e auf den Inhalt des
     Archivs �bertragen werden?
     0 - Nein (alles nur in die Greylist aufnehmen),
     1 - Ja [Standardeinstellung].
   "filetype_archives"
   - Soll das Blacklisting/Whitelisting des Dateityps auf den Inhalt des
     Archivs �bertragen werden?
     0 - Nein (alles nur in die Greylist aufnehmen) [Standardeinstellung],
     1 - Ja.
   "max_recursion"
   - Maximale Grenze der Rekursionstiefe von Archiven. Standardwert = 10.
 "attack_specific" (Kategorie)
 - Konfiguration f�r spezifische Angriffserkennung (nicht auf CVD basierend).
   * Chameleon-Angriffserkennung: 0 = deaktiviert, 1 = aktiviert.
   "chameleon_from_php"
   - Suche nach PHP-Headern in Dateien, die weder PHP-Dateien noch erkannte
     Archive sind.
   "chameleon_from_exe"
   - Suche nach ausf�hrbaren Headern in Dateien, die weder ausf�hrbar
     noch erkannte Archive sind und f�r ausf�hrbare Dateien, deren Header nicht
     korrekt sind.
   "chameleon_to_archive"
   - Suche nach Archiven,  deren Header nicht korrekt sind
     (Unterst�tzt: BZ, GZ, RAR, ZIP, RAR, GZ).
   "chameleon_to_doc"
   - Suche nach Office-Dokumenten, deren Header nicht korrekt sind.
     (Unterst�tzt: DOC, DOT, PPS, PPT, XLA, XLS, WIZ).
   "chameleon_to_img"
   - Suche nach Bildern, deren Header nicht korrekt sind.
     (Unterst�tzt: BMP, DIB, PNG, GIF, JPEG, JPG, XCF, PSD, PDD).
   "chameleon_to_pdf"
   - Suche nach PDF-Dateien, deren Header nicht korrekt sind.
   "archive_file_extensions" und "archive_file_extensions_wc"
   - Erkannte Archiv-Dateierweiterungen (Format ist CSV; nur bei Problemen
     hinzuf�gen oder entfernen; unn�tiges Entfernen k�nnte Fehlalarme f�r
     Archive ausl�sen, unn�tiges Hinzuf�gen f�gt das zur Whitelist hinzu, was
     vorher als m�glicher Angriff definiert wurde; �ndern Sie diese Liste
     �u�erst vorsichtig; Beachten Sie, dass dies keinen Einflu� darauf hat,
     wozu Archive f�hig sind und kann nicht auf Inhaltsebene analysiert
     werden). Diese Liste enth�lt die Archivformate, die am h�ufigsten von der
     Mehrzahl der Systeme und CMS verwendet werden, ist aber absichtlich nicht
     vollst�ndig.
   "general_commands"
   - Soll der Inhalt von Dateien auf allgemeine Befehle wie eval(), exec() und
     include() durchsucht werden?
     0 - Nein (nicht �berpr�fen) [Standardeinstellung], 1 - Ja (�berpr�fen).
     Stellen Sie diese Option aus, wenn Sie vorhaben, folgende Dateien mittels
     Browser auf Ihr System oder CMS hochzuladen: php, JavaScript, HTML,
     python, perl usw. Aktivieren Sie diese Option, falls Sie keine
     zus�tzlichen Schutzmechanismen auf Ihrem System haben und nicht planen,
     solche Dateien hochzuladen. Verwenden Sie zus�tzliche Sicherheitssoftware
     in Verbindung mit phpMussel wie ZB Block, ist es nicht notwendig, diese
     Option zu aktivieren, phpMussel w�rde nur unn�tigerweise (im Kontext
     dieser Option) danach suchen, wogegen das System bereits gesch�tzt ist.
   "block_control_characters"
   - Sollen Dateien, welche Steuerzeichen (andere als Newline/Zeilenumbruch)
     enthalten, blockiert werden?
     ([\x00-\x08\x0b\x0c\x0e\x1f\x7f]) Sofern Sie -nur- reinen Text hochladen,
     k�nnen Sie diese Option aktivieren, um Ihrem System zus�tzlichen Schutz zu
     bieten. Sollten Sie anderes als reinen Text hochladen, werden bei
     aktivierter Option Fehlalarme ausgel�st.
     0 - Nicht blockieren [Standardeinstellung], 1 - Blockieren.
   "corrupted_exe"
   - Defekte Dateien und Parse-Errors.
     0 = Ignorieren, 1 = Blockieren [Standardeinstellung].
     Soll auf potentiell defekte ausf�hrbare Dateien (PE - Portable Executable)
     gepr�ft und diese blockiert werden? Oftmals (aber nicht immer), wenn
     bestimmte Aspekte einer PE-Datei besch�digt sind oder nicht korrekt
     verarbeitet werden k�nnen, ist dies ein Hinweis auf eine infizierte Datei.
     Viele Antiviren-Programme nutzen verschiedene Methoden, um Viren in
     solchen Dateien zu erkennen, sofern sich der Programmierer eines Virus
     dieser Tatsache bewu�t ist, wird er versuchen, diese Ma�nahmen zu
     verhindern, damit der Virus unentdeckt bleibt.
   "decode_threshold"
   - Optionale Beschr�nkung oder Schwelle der Menge der Rohdaten, die durch den
     Decode-Befehl erkannt werden sollen (sofern w�hrend des Scanvorgangs
     sp�rbare Performance-Probleme auftreten). Der Wert ist ein Integer
     (Ganzzahl) und repr�sentiert die Dateigr��e in KB. Standardeinstellung ist
     512 (512 KB). Null oder ein Null-Wert deaktiviert die Beschr�nkung
     (Entfernen aller solcher Einschr�nkungen basierend auf die Dateigr��e).
   "scannable_threshold"
   - Optionale Beschr�nkung oder Schwelle der Menge der Rohdaten, die phpMussel
     lesen und scannen darf (sofern w�hrend des Scanvorgangs sp�rbare
     Performance-Probleme auftreten). Der Wert ist ein Integer (Ganzzahl) und
     repr�sentiert die Dateigr��e in KB. Standardeinstellung ist 32768 (32 MB).
     Null oder ein Null-Wert deaktiviert die Beschr�nkung. Generell sollte
     dieser Wert nicht kleiner sein als die durchschnittliche Dateigr��e von
     Datei-Uploads, die Sie auf Ihrem Server oder Ihrer Website erwarten,
     sollte nicht gr��er sein als die Richtlinie filesize_limit und sollte
     nicht mehr als ein F�nftel der Gesamtspeicherzuweisung f�r PHP in der
     Konfigurationsdatei php.ini. Diese Richtlinie verhindert, dass phpMussel
     zu viel Speicher benutzt (was phpMussel daran hindern w�rde, einen Scan
     ab einer bestimmten Dateigr��e erfolgreich durchzuf�hren).
 "compatibility" (Kategorie)
 - Kompatibilit�tsdirektiven f�r phpMussel.
   "ignore_upload_errors"
   - Diese Direktive sollte generell AUS geschaltet bleiben sofern es nicht f�r
     die korrekte Funktion von phpMussel auf Ihrem System ben�tigt wird.
     Normalerweise, sobald phpMussel bei AUS geschalteter Direktive ein Element
     in $_FILES array() erkennt, wird es beginnen, die Dateien, die diese
     Elemente representieren, zu �berpr�fen, sollten diese Elemente leer sein,
     gibt phpMussel eine Fehlermeldung zur�ck. Dies ist das normale Verhalten
     von phpMussel. Bei einigen CMS werden allerdings als normales Verhalten
     leere Elemente in $_FILES zur�ckgegeben oder Fehlermeldungen ausgel�st,
     sobald sich dort keine leeren Elemente befinden, in diesem Fall tritt ein
     Konflikt zwischen dem normalen Verhalten von phpMussel und dem CMS auf.
     Sollte eine solche Konstellation bei Ihrem CMS zutreffen, so stellen Sie
     diese Option AN, phpMussel wird somit nicht nach leeren Elementen suchen,
     Sie bei einem Fund ignorieren und keine zugeh�rigen Fehlermeldungen
     ausgeben, der Request zum Seitenaufruf kann somit fortgesetzt werden.
     0 - AUS/OFF, 1 - AN/ON.
   "only_allow_images"
   - Wenn Sie nur Bilder erwarten, die auf Ihr System oder CMS hochgeladen
     werden oder nur Bilder und keine anderen Dateien als Upload erlauben oder
     ben�tigen, so sollte diese Direktive aktiviert werden (ON), ansonsten
     deaktiviert bleiben (OFF). Ist diese Direktive aktiviert, wird phpMussel
     alle Uploads, die keine Bilddateien sind, blockieren, ohne sie zu scannen.
     Dies kann die Verarbeitungszeit und Speichernutzung resuzieren, sobald
     andere Nicht-Bilddateien hochgeladen werden. 0 - AUS/OFF, 1 - AN/ON.

                                     ~ ~ ~


 7. SIGNATURENFORMAT

 = DATEINAMEN-SIGNATUREN =
   Alle Dateinamen-Signaturen besitzen folgendes Format:
    NAME:FNRX
   NAME ist der Name, um die Signatur zu benennen und FNRX ist das
   Regex-Erkennungsmuster zum Vergleich von (nicht codierten) Dateinamen.

 = MD5-SIGNATUREN =
   Alle MD5-Signaturen besitzen folgendes Format:
    HASH:FILESIZE:NAME
   HASH ist der MD5-Hash der ganzen Datei, FILESIZE ist die gesamte Gr��e der
   Datei und NAME ist der Name, um die Signatur zu benennen.

 = ARCHIV-METADATA-SIGNATUREN =
   Alle Archiv-Metadata-Signaturen besitzen folgendes Format:
    NAME:FILESIZE:CRC32
   NAME ist der Name, um die Signatur zu benennen, FILESIZE ist die gesamte
   Gr��e (unkomprimiert) einer jeden Datei im Archiv und CRC32 ist die
   CRC32-Pr�fsumme jeder einzelnen Datei im Archiv.

 = PE-SECTIONAL-SIGNATUREN =
   Alle PE-Sectional-Signaturen besitzen folgendes Format:
    SIZE:HASH:NAME
   HASH ist der MD5-Hash einer PE-Sektion der Datei, FILESIZE ist die gesamte
   Gr��e der PE-Sektion und NAME ist der Name, um die Signatur zu benennen.

 = WHITELIST-SIGNATUREN =
   Alle Whitelist-Signaturen besitzen folgendes Format:
    HASH:FILESIZE:NAME
   HASH ist der MD5-Hash der ganzen Datei, FILESIZE ist die gesamte Gr��e der
   Datei und TYPE ist der Signaturtypen die Datei ist immun gegen.

 = KOMPLEX-ERWEITERT-SIGNATUREN =
   Komplex-Erweitert-Signaturen sind ziemlich verschieden von den anderen Typen
   von Signaturen mit phpMussel m�glich, in that what they are matching against
   is specified by the signatures themselves and they can match against
   multiple criteria. The match criterias are delimited by ";" and the match
   type and match data of each match criteria is delimited by ":" as so that
   format for these signatures tends to look a bit like:
    $variable1:SOMEDATA;$variable2:SOMEDATA;SignatureName

 = ALLE SONSTIGEN SIGNATUREN =
   Alle sonstigen Signaturen besitzen folgendes Format:
    NAME:HEX:FROM:TO
   NAME ist der Name, um die Signatur zu benennen und HEX ist ein
   hexidezimal-codediertes Segment der Datei, welches mit der gegebenen
   Signatur gepr�ft werden soll. FROM und TO sind optionale Parameter, Sie
   geben Start- und Endpunkt in den Quelldaten zur �berpr�fung an (wird nicht
   von der Mail-Funktion unterst�tzt).

 = REGEX =
   Jede Form von regul�ren Ausdr�cken, die von PHP verstanden und korrekt
   ausgef�hrt werden, sollten auch von phpMussel und den Signaturen verstanden
   und korrekt ausgef�hrt werden k�nnen. Lassen Sie extreme Vorsicht walten,
   wenn Sie neue Signaturen schreiben, die auf regul�ren Ausdr�cken basieren,
   wenn Sie nicht absulut sicher sind, was Sie dort machen, kann dies zu nicht
   korrekten und/oder unerwarteten Ergebnissen f�hren. Schauen Sie im Quelltext
   von phpMussel nach, wenn Sie sich nicht absolut sicher sind, wie die
   regul�ren Ausdr�cke verarbeitet werden. Beachten Sie bitte, dass alle
   Suchmuster (au�er Dateinamen, Archive-Metadata and MD5-Pr�fmuster)
   hexadezimal codiert sein m�ssen (mit Ausnahme von Syntax, nat�rlich)!

 = WO WERDEN EIGENE SIGNATUREN ABGELEGT? =
   Legen Sie Ihre eigenen Signaturen nur in den Dateien ab, die daf�r
   vorgesehen sind. Diese Dateien sollten "_custom" im Dateinamen enthalten.
   Sie sollten es vermeiden, die Standard-Signaturen direkt zu bearbeiten,
   sofern Sie nicht genau wissen, was Sie dort tun. Eigene Signaturdateien
   helfen Ihnen, zwischen Ihren und den von phpMussel mitgelieferten Signaturen
   zu unterscheiden. F�hren Sie �nderungen an den von phpMussel mitgelieferten
   Signaturen durch, ist es m�glich, dass diese nicht mehr richtig ausgef�hrt
   werden k�nnen, da die Map-Dateien, sofern Sie f�r verschiedene Operationen
   angefordert werden, nicht mehr mit den zugeh�rigen Signaturen synchronisiert
   sind. Sie k�nnen alles in Ihre einen Signaturen eintragen, sofern es der
   richtigen Syntax entspricht. Achten Sie darauf, neue Signaturen gr�ndlich zu
   testen, bevor Sie Sie mit anderen teilen oder in einer Live-Umgebung
   einsetzen.

 = AUFSCHL�SSELUNG DER SIGNATUREN =
   Im Folgenden eine Aufschl�sselung der Signaturen, die von phpMussel genutzt
   werden:
   - "Normierten ASCII-Signaturen" (ascii_*). �berpr�ft den Inhalt jeder Datei,
      die nicht in der Whitelist aufgef�hrt ist und �berpr�ft werden soll.
   - "ELF-Signaturen" (elf_*). �berpr�ft den Inhalt jeder Datei, die nicht in
      der Whitelist aufgef�hrt ist und �berpr�ft werden soll und dem ELF-Format
      entspricht.
   - "Portable Executable Signaturen" (exe_*). �berpr�ft den Inhalt jeder
      Datei, die nicht in der Whitelist aufgef�hrt ist und �berpr�ft werden
      soll und dem PE-Format entspricht.
   - "Dateinamen-Signaturen" (filenames_*). �berpr�ft die Dateinamen jeder
      Datei, die nicht in der Whitelist aufgef�hrt ist und �berpr�ft werden
      soll.
   - "Allgemeine Signaturen" (general_*). �berpr�ft den Inhalt jeder Datei, die
      nicht in der Whitelist aufgef�hrt ist und �berpr�ft werden soll.
   - "Grafiksignaturen" (graphics_*). �berpr�ft den Inhalt jeder Datei, die
      nicht in der Whitelist aufgef�hrt ist und �berpr�ft werden soll und einem
      bekannten Bildformat entspricht.
   - "Allgemeine Befehle" (hex_general_commands.csv). �berpr�ft den Inhalt
      jeder Datei, die nicht in der Whitelist aufgef�hrt ist und �berpr�ft
      werden soll.
   - "Normierten HTML-Signaturen" (html_*). �berpr�ft den Inhalt jeder
      HTML-Datei, die nicht in der Whitelist aufgef�hrt ist und �berpr�ft
      werden soll.
   - "Mach-O-Signaturen" (macho_*). �berpr�ft den Inhalt jeder Datei, die nicht
      in der Whitelist aufgef�hrt ist und �berpr�ft werden soll und dem
      Mach-O-Format entspricht.
   - "Email-Signaturen" (mail_*). �berpr�ft mittels der Funktion
      phpMussel_mail() die Variable $body von E-Mail-Nachrichten oder �hnlichen
      Eintr�gen (Foreneintr�ge etc.).
   - "MD5-Signaturen" (md5_*). �berpr�ft mittels MD5-Hash des Inhalts und der
      Dateigr��e jede Datei, die nicht in der Whitelist aufgef�hrt ist und
      �berpr�ft werden soll.
   - "Archiv-Metadata-Signaturen" (metadata_*). �berpr�ft die CRC32-Pr�fsumme
      und Dateigr��e der ersten Datei in jedem Archiv, welches nicht in der
      Whitelist aufgef�hrt ist und �berpr�ft werden soll.
   - "OLE-Signaturen" (ole_*). �berpr�ft den Inhalt jeder Objekten, die nicht
      in der Whitelist aufgef�hrt ist.
   - "PDF-Signaturen" (pdf_*). �berpr�ft den Inhalt jeder PDF-Dateien, die
      nicht in der Whitelist aufgef�hrt ist.
   - "Portable Executable Sectional Signaturen" (pe_*). �berpr�ft mittels der
      Gr��e und MD5-Hash des PE-Sektionen jeder Datei, die nicht in der
      Whitelist aufgef�hrt ist und �berpr�ft werden soll und dem PE-Format
      entspricht.
   - "SWF-Signaturen" (swf_*). �berpr�ft den Inhalt jeder Shockwave-Dateien,
      die nicht in der Whitelist aufgef�hrt ist.
   - "Whitelist-Signaturen" (whitelist_*). �berpr�ft mittels MD5-Hash des
      Inhalts und der Dateigr��e jede Datei. Abgestimmt Dateien werden immun
      gegen die von der Art der Signaturen in der Whitelist-Eintrag.
   - "XML/XDP-Chunk Signatures" (xmlxdp_*). �berpr�ft XML/XDP-St�cke aus jeder
      Datei, die nicht in der Whitelist aufgef�hrt ist und �berpr�ft werden
      soll.
   (Beachten Sie, dass jede dieser Signaturen auf einfache Weise in der
    phpmussel.ini deaktiviert werden kann).

                                     ~ ~ ~


 8. BEKANNTE KOMPATIBILIT�TSPROBLEME

 PHP und PCRE
 - phpMussel ben�tigt PHP und PCRE, um ausgef�hrt werden zu k�nnen. Ohne PHP
   und ohne die PCRE-Erweiterungen von PHP, kann phpMussel nicht oder nicht
   ordnungsgem�� ausgef�hrt werden. Stellen Sie sicher, dass auf Ihrem System
   PHP und PCRE installiert und verf�gbar ist, bevor Sie phpMussel
   herunterladen und installieren.

 KOMPATIBILIT�T ZU ANTIVIREN-SOFTWARE

 In den meisten F�llen sollte phpMussel mit den meisten anderen
 Antiviren-Softwareprodukten kompatibel sein. Jedoch wurden in der
 Vergangenheit Konflikte von anderen Nutzern festgestellt. Die folgenden
 Informationen stammen von VirusTotal.com, welches einige Fehlalarme von
 verschiedenen Antiviren-Programmen gegen phpMussel beschreibt. Diese
 Informationen garantieren nicht, ob Kompatibilit�tsprobleme zwischen phpMussel
 und Ihrem eingesetzten Antiviren-Produkt bestehen. Sollte Ihre
 Antiviren-Software als problematisch aufgelistet sein, sollten Sie entweder
 vor der Benutzung von phpMussel deaktivieren oder sich andere Alternativen
 �berlegen.

 Diese Informationen wurden zuletzt am 2015.02.04 aktualisiert und gelten f�r
 alle phpMussel Ver�ffentlichungen von der beiden letzten Nebenversionen
 (v0.5-v0.6) zu diesem Zeitpunkt.

 Ad-Aware                Keine bekannten Probleme
 Agnitum                 Keine bekannten Probleme
 AhnLab-V3               Keine bekannten Probleme
 AntiVir                 Keine bekannten Probleme
 Antiy-AVL               Keine bekannten Probleme
 Avast                !  Meldet "JS:ScriptSH-inf [Trj]"
 AVG                     Keine bekannten Probleme
 Baidu-International     Keine bekannten Probleme
 BitDefender             Keine bekannten Probleme
 Bkav                    Keine bekannten Probleme
 ByteHero                Keine bekannten Probleme
 CAT-QuickHeal           Keine bekannten Probleme
 ClamAV                  Keine bekannten Probleme
 CMC                     Keine bekannten Probleme
 Commtouch               Keine bekannten Probleme
 Comodo                  Keine bekannten Probleme
 DrWeb                   Keine bekannten Probleme
 Emsisoft                Keine bekannten Probleme
 ESET-NOD32              Keine bekannten Probleme
 F-Prot                  Keine bekannten Probleme
 F-Secure                Keine bekannten Probleme
 Fortinet                Keine bekannten Probleme
 GData                   Keine bekannten Probleme
 Ikarus                  Keine bekannten Probleme
 Jiangmin                Keine bekannten Probleme
 K7AntiVirus             Keine bekannten Probleme
 K7GW                    Keine bekannten Probleme
 Kaspersky               Keine bekannten Probleme
 Kingsoft                Keine bekannten Probleme
 Malwarebytes            Keine bekannten Probleme
 McAfee               !  Meldet "New Script.c"
 McAfee-GW-Edition    !  Meldet "New Script.c"
 Microsoft               Keine bekannten Probleme
 MicroWorld-eScan        Keine bekannten Probleme
 NANO-Antivirus          Keine bekannten Probleme
 Norman               !  Meldet "Kryptik.BQS"
 nProtect                Keine bekannten Probleme
 Panda                   Keine bekannten Probleme
 Qihoo-360               Keine bekannten Probleme
 Rising                  Keine bekannten Probleme
 Sophos                  Keine bekannten Probleme
 SUPERAntiSpyware        Keine bekannten Probleme
 Symantec             !  Meldet "WS.Reputation.1"
 TheHacker               Keine bekannten Probleme
 TotalDefense            Keine bekannten Probleme
 TrendMicro              Keine bekannten Probleme
 TrendMicro-HouseCall    Keine bekannten Probleme
 VBA32                   Keine bekannten Probleme
 VIPRE                   Keine bekannten Probleme
 ViRobot                 Keine bekannten Probleme


                                     ~ ~ ~


Zuletzt aktualisiert: 2015.04.13
EOF