# Windows Reiniger

- 1. Temporäre Dateien löschen (Temp-Ordner)
Funktion: clean_temp()
Was passiert?: Das Skript löscht temporäre Dateien, die im Systemordner für temporäre Dateien gespeichert sind. Dieser Ordner befindet sich typischerweise unter C:\Users\<Username>\AppData\Local\Temp und wird von verschiedenen Programmen genutzt, um temporäre Dateien zwischenzuspeichern.
Wie wird es durchgeführt?: Es wird überprüft, ob Dateien oder Verzeichnisse im Temp-Ordner vorhanden sind. Wenn ja, werden diese gelöscht. Das Skript entfernt sowohl Dateien als auch Unterordner.
Fehlerbehandlung: Falls Dateien von anderen Programmen verwendet werden und daher nicht gelöscht werden können, wird der Fehler ausgegeben, aber der Vorgang wird nicht gestoppt.
- 2. Windows Temp-Ordner bereinigen
Funktion: clean_windows_temp()
Was passiert?: Das Skript löscht Dateien im Windows-Systemordner für temporäre Dateien, in den der Ordner C:\Windows\Temp gehört. Auch der temporäre Ordner im Benutzerprofil (C:\Users\<Username>\AppData\Local\Temp) wird überprüft und gegebenenfalls bereinigt.
Fehlerbehandlung: Wenn der Ordner oder einzelne Dateien nicht gelöscht werden können (z.B. durch fehlende Berechtigungen), wird eine entsprechende Fehlermeldung ausgegeben.
- 3. Chrome Browser-Cache löschen
Funktion: clean_browser_cache()
Was passiert?: Wenn Google Chrome auf dem System installiert ist, wird der Cache von Chrome gelöscht. Der Cache befindet sich im Ordner C:\Users\<Username>\AppData\Local\Google\Chrome\User Data\Default\Cache.
Wie wird es durchgeführt?: Das Skript löscht den gesamten Inhalt des Cache-Ordners.
Fehlerbehandlung: Falls der Ordner nicht gefunden wird oder ein anderer Fehler auftritt, wird dieser ausgegeben.
- 4. Prefetch-Dateien löschen
Funktion: clean_prefetch()
Was passiert?: Windows speichert bestimmte Programmstarts im Prefetch-Ordner (C:\Windows\Prefetch), um die Systemleistung zu verbessern. Das Skript löscht alle Dateien in diesem Ordner.
Wie wird es durchgeführt?: Alle Dateien im Prefetch-Ordner werden gelöscht.
Fehlerbehandlung: Falls der Ordner nicht gefunden wird oder andere Fehler auftreten, wird dies ausgegeben.
- 5. Datenträgerbereinigung ausführen
Funktion: run_disk_cleanup()
Was passiert?: Das Skript startet die Windows-Datenträgerbereinigung, um unnötige Systemdateien zu entfernen. Diese Funktion wird über das Windows-Befehlszeilenwerkzeug cleanmgr ausgeführt.
Wie wird es durchgeführt?: Der Befehl cleanmgr /sagerun:1 wird ausgeführt, der die vordefinierten Bereinigungseinstellungen von Windows nutzt.
Fehlerbehandlung: Falls die Datenträgerbereinigung nicht erfolgreich ausgeführt werden kann, wird dies ausgegeben.
- 6. Systemwiederherstellungspunkte löschen
Funktion: clean_system_restore_points()
Was passiert?: Das Skript versucht, alle Systemwiederherstellungspunkte (auch Schattenkopien genannt) zu löschen. Dies erfolgt über das Windows-Befehlszeilenwerkzeug vssadmin.
Wie wird es durchgeführt?: Der Befehl vssadmin delete shadows /all /quiet wird verwendet, um alle Schattenkopien zu löschen.
Fehlerbehandlung: Falls keine Schattenkopien vorhanden sind oder der Befehl aus anderen Gründen fehlschlägt (z.B. durch fehlende Berechtigungen), wird dies ausgegeben.


Das Skript löscht nicht die Festplatten oder wichtige Datein. Ich hafte für keine schäden an irgendwas. Benutzt es wenn Ihr euch nicht sicher sein ob euer PC gereinigt und wirklich frei von Problemen und Fehlern ist.
