

# LibPortablePlus
  
[Build Firefox_ESR.91.xxx32-64.(22.07.12) herunterladen](https://github.com/wvxwxvw/LibPortablePlus/raw/main/Firefox_ESR.91.xxx32-64.(22.07.12).7z)  
Es gibt auch ein vorkonfiguriertes Profil:  
[Lesen](https://github.com/wvxwxvw/LibPortablePlus_Profiles/blob/main/README.md) | [Herunterladen](https://github.com/wvxwxvw/LibPortablePlus_Profiles/raw/main/Firefox.91.ESR.LPP.profile.220714.7z) | [Mit TST anzeigen](https://github.com/wvxwxvw/LibPortablePlus_Profiles/blob/main/tstex-screen.md) | [Ohne TST anzeigen](https://github.com/wvxwxvw/LibPortablePlus_Profiles/blob/main/ntfex-screen.md)  
  
[Build Firefox_ESR.102.xxx32-64.(10.22.03) herunterladen](https://github.com/wvxwxvw/LibPortablePlus/raw/main/Firefox_ESR.102.xxx32-64.(10.22.03).7z)
  
## Tragbarer Firefox ESR (32-64)  
  
* Bedingte Portabilität durch portable*.dll  
* Mehrere Optionen für Einstellungsdateien  
* Mehrere Möglichkeiten, Arbeitsspuren zu beseitigen  
* Sicherungsmethode  
* Integrierter Skript-Loader – user_chrome_files  
* usw.  
  
  
## Allgemeine Beschreibung:  
  
#### • Zukünftiger Profilordner enthält:  
##### Steckerpaar:  
         Wird benötigt, um sicherzustellen, dass keine Papierkorbordner erstellt werden  
##### search.json.mozlz4:  
         · Fügt mehrere Suchmaschinen hinzu, darunter auch verbotene  
#####prefs.js:  
         Aktiviert die Skriptunterstützung und zeigt eine Skriptschaltfläche im Bedienfeld an  
            Schnelles Umschalten der about:config-Parameter  
         · Stellt mehrere in der Schaltfläche verfügbare Parameter vor  
         · Voreingestellte Anzeige von Suchmaschinen, Änderungen in den Einstellungen  
         Pinnt Top-Links zu zwei alternativen neuen Tabs  
#####user.js:  
         Die Hauptkonfigurationsdatei des zukünftigen Build-Profils  

#### • Der Kernel-Ordner enthält:  
##### Einstellungsdateien  
         · Integrieren Sie die Möglichkeit, Skripte und Stile in user_chrome_files zu installieren  
  
##### Richtliniendatei  
         Deaktiviert: Telemetrie, CaptivePortal, Mozilla Services, GMP, CDM,  
            Möglichkeit, Hintergrundbild, erste Ausführungsseite, PostUpdatePage festzulegen,  
            Erstellen Sie Standard-Lesezeichenordner für ein neues Profil  
         Deaktiviert die automatische Aktualisierung: Browser, Erweiterungen, Suchmaschinen,  
            Systemerweiterungen
  
#### • Temporäre Dateien werden nach %TEMP% geschrieben  
#### • Skript zum Bereinigen von Kernel-, Profil- und temporären Dateien hinzugefügt (manueller Start)  
#### • Es wurde eine Möglichkeit hinzugefügt, ein Profil oder ausgewählte Ordner/Dateien schnell zu sichern  
#### • Firefox-Konten, Pocket- und Service-Worker deaktiviert, aber einfach zu aktivieren  
#### • Weitere Komponenten und detailliertere Beschreibungen finden Sie im Wartungsordner  
  
  
## Assembly-Stamm:  
  
„scharf
    Wartungsordner
        Zusätzliche Komponenten und Beschreibungen dazu
        Build-Beschreibung
        Ordner „Maintenance/7z“.
            Archiver-Komponenten
        Maintenance/SQLite-Ordner
            *.SQLite-Dienstprogramm zur Datenbankkomprimierung
    _include.txt
        Backup-Liste, kann bearbeitet werden
            Es wurde ein Beispiel für die Auswahl aus Unterordnern hinzugefügt
    FF-102esr-Cleaner.exe
        Bereinigt Profilmüll, Kernel, temporäre Ordner und einige andere Orte.
        Der Ordner „bookmarkbackups“ wird ebenfalls gelöscht, er wird bei Konstante einfach nicht benötigt
        Vollständige Profilsicherungen. Beendet beim Start alle Firefox-Prozesse.
        Quellen in Wartung können Sie in Aut2Exe auf Ihre eigene Weise neu kompilieren,
        welches in AutoIt enthalten ist.
    Firefox 102esr RUN.lnk
        Verknüpfung zum Ausführen von firefox.exe aus dem Kernordner
    VAKUUM-.bat
        Presst alle .sqlite im Profil und seinen Unterordnern
        Kann Ad-Cutter-Basen und den Verlauf einzelner Erweiterungen löschen
            Beschreibung an sich und in Maintenance\sources\bat
            Erfordert einen Ordner „wartung\SQLite“ in der Nähe
    xBACKUP.bat
        Erstellt ein Archiv gemäß der Liste aus _include.txt
            Das Passwort für das Archiv lautet 12345, es ändert sich in der Batchdatei selbst
            Erfordert einen Ordner „wartung\7z“ in der Nähe
„
  
  
## Vorbereiten für den Einsatz (und Aktualisieren der Baugruppe):  
„scharf
    • Laden Sie die erforderliche Version der gewünschten Bittiefe herunter, z. B.
      von https://ftp.mozilla.org/pub/firefox/releases/
    • Öffnen Sie die Firefox-Distribution mit 7-zip oder WinRAR.
    • Ziehen Sie den Ordner „core“ aus der Distribution in das Stammverzeichnis des Ordners mit der Assembly,
      stimmen Sie dem Überschreiben von Dateien zu.
    • Öffnen Sie „dependentlibs.list“ mit dem alternativen Editor und der ersten Zeile
      schreiben Sie portable32.dll oder portable64.dll vor (abhängig von der Bittiefe).
    • Führen Sie FF-102esr-Cleaner.exe aus, um den Müll der Distribution zu bereinigen.
„
  
  
## So beginnen Sie mit der Verwendung:  
  
„scharf
    1. Um ein neues Profil zu erstellen  
        • Führen Sie core/firefox.exe oder die Verknüpfung „Firefox 102esr RUN.lnk“ aus.  
        • Wir gebrauchen  
      
    2. Um Ihr altes Profil zu verwenden  
        • Wir werfen Dateien und Ordner von unserem Profil nach „Profil“  
            Wir weigern uns zu ersetzen, ignorieren Fehler, klicken Sie auf „Überspringen“  
            Weiter unten können Sie „Übernahme des alten Profils“ vorlesen.  
        • Führen Sie FF-102esr-Cleaner.exe aus und warten Sie einige Sekunden  
        • Führen Sie core/firefox.exe oder die Verknüpfung „Firefox 102esr RUN.lnk“ aus.  
        • Wir gebrauchen  
„
  
        ! In der Seitenleiste finden Sie eine blaue Schaltfläche. Lesen Sie den entsprechenden Hinweis.  
  
        !! Wenn Erweiterungen aus dem alten Profil ihre Einstellungen verlieren, entfernen Sie sie  
            addonStartup.json.lz4 im Profil und starten Sie den Browser zweimal neu  
            Bei der ersten Ausführung wird ein neuer Erweiterungsladecache erstellt und so weiter  
            Beim zweiten Start beginnen die Erweiterungen mit dem neuen Cache. Einstellungen  
            Erweiterungen werden wiederhergestellt.  
  
        !!! Es empfiehlt sich, gleich eine Alternative zur Homepage zu installieren,
            etwas Eigenes oder zum Beispiel von Mozilla empfohlenes:
            https://addons.mozilla.org/en/firefox/addon/tabliss/
            https://addons.mozilla.org/en/firefox/addon/new-tab-override/
            Nicht alle Telemetrie- und Netzwerkverbindungen der Standard-Startseite
            werden durch Konfigurationsdateien deaktiviert, daher ist die ideale Lösung
            Benutzen oder öffnen Sie es nicht.
  
## Altes Profil migrieren  
  
Sie können das gesamte alte Profil verwenden.  
Aber ich empfehle dringend nicht, den ganzen Müll wegzuschleppen, sondern nur das mitzunehmen, was Sie brauchen  
und für Sie verständlich.  
  
Idealerweise können Sie nur diese einnehmen:  
„scharf
    favicons.sqlite – Symbole für Lesezeichen und Browserverlauf
    key*.db – Passwortverschlüsselungsschlüssel (relevant bei einer größeren Zahl)
    logins.json – gespeicherte Passwörter
    persdict.dat – Ausschlusswörter, die Sie dem Wörterbuch hinzugefügt haben
    places.sqlite – Lesezeichen und Browserverlauf
    search.json.mozlz4 – Ihre Suchmaschinen (falls geändert), aber
      Ihre alte Datei wird möglicherweise von Firefox überschrieben, wenn dies nicht der Fall ist
      Standard-Firefox-Suchmaschinen für diese Version.
„
  
Auf keinen Fall sollten Sie die alten pref.js in das neue Profil ziehen,  
und user.js müssen sorgfältig inventarisiert werden.  
Die Optionen können sich zwischen Firefox-Versionen und älteren Einstellungen ändern  
funktionieren in der neuen Version anders.  
  
Der Schlüssel zu einem stabilen Browserbetrieb ist die regelmäßige Neuerstellung des Profils  
  
Artikel zu Profildateien unter support.mozilla.org en  
  
  
## Profilsicherung (Sicherung):  
  
„scharf
    Führen Sie xBACKUP.bat aus und holen Sie sich ein Backup-Archiv
    (Das Passwort für das Archiv ist 12345, Änderungen in der Batchdatei).
    Vor dem Backup können Sie VACUUM-.bat ausführen, nachdem Sie es zuvor gelesen haben
    mit seinem Inhalt, Kodierung „Cyrillic OEM 866“ (sonst DOS/OEM) und
    für mich selbst bearbeitet.
„
 
  
  
## Baugruppenbereinigung:  
  
„scharf
    Nach dem Update, nach der Arbeit an der Maschine eines anderen und einfach für
    Für die regelmäßige Reinigung können Sie FF-102esr-Cleaner.exe verwenden.
    Es bereinigt den Ordner Kernel, Profil, ProgramData, LocalLow und %TEMP%.
    Bereinigt NICHT: Lesezeichen, Verlauf, Passwörter, Cookies/Speicher/Sitzungen und Formularverlauf,
    Das Löschen dieser Positionen beim Schließen des Browsers wird in Abschnitt 2811 von user.js konfiguriert.
    aber es ist in der blauen Schaltfläche in der Seitenleiste oder im Abschnitt 2810 user.js enthalten.
„

  
  
## Nützliche Links:  
  
simpleMenuWizard  
userChrome/userContent-Stile zum Bearbeiten aller Kontextmenüs  
Firefox, vom Autor der alten Simple Menu Wizard-Erweiterung  
  
Firefox-UI-Fix  
Mehrere Bausätze für die Protoneneliminierung  
Klassische CSS-Optimierungen für Firefox Quantum  
userChrome/userContent-Stile, vom Autor des alten ClassicThemeRestorer  
Megabar – Konfigurieren und Stylen  
Stilgenerator für Megabar (Adressleiste)  
  
arkenfox user.js  
Parameterreferenz zum Kompilieren Ihrer eigenen user.js,  
für verschiedene Versionen von Firefox (Datenschutz und Sicherheit)  
Richtlinienvorlagen für Firefox  
Richtlinienvorlagen für Firefox  
  
## Verwendete Entwicklungen & Credits:  
  
      mozilla   
      mozilla-russia.org   
      libportable    
      arkenfox   
      VitaliyVstyle   
      7-zip   
      sqlite  

