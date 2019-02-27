Rechteverwalten
---------------------------------------------------------------------------------------------------------------

    1. Dokumentieren Sie die durchgeführten Arbeiten in diesem Auftrag
    -------------------------------------------------------------------
    Die Dokumentation gilt als Abgabe zum Auftrag
    -------------------------------------------------------------------


    2. Studieren Sie den Artikel zum Thema Rechte unter Linux bevor Sie beginnen
    -----------------------------------------------------------------------------
    https://wiki.ubuntuusers.de/Rechte/
    -----------------------------------------------------------------------------


    3. Erstellen Sie als [root] ein neues Verzeichnis
    /root/docs/business
    -----------------------------------------------------------------------------    
    mkdir /root/docs/business -p
    -----------------------------------------------------------------------------


    4. Erstellen Sie als [root] eine neue Datei
    /home/max/privat/schule/liste
    -----------------------------------------------------------------------------
    touch /home/max/privat/schule/liste -p
    -----------------------------------------------------------------------------


    5. Ändern Sie den Besitzer der Datei [liste] auf [max]
    Kann das nur root?
    -----------------------------------------------------------------------------
    chown max liste
    -----------------------------------------------------------------------------


    6. Ändern Sie die Hauptgruppe vom erstellten Verzeichnis [business] auf [fritz]
    Ist diese Änderung sinnvoll? Kann [fritz] das /root Verzeichnis überhaupt öffnen?
    ------------------------------------------------------------------------------------
    chgrp fritz /root/docs/business/
    ------------------------------------------------------------------------------------


    7. Setzen Sie mit chmod Rechte der neuen Datei [liste] auf [r--rwx--x]
    Welchen Wert hat diese Berechtigung in Zahlen?
    ------------------------------------------------------------------------------------
    chmod 471 liste
    chmod u=r,g=rwx,o=x liste
    ------------------------------------------------------------------------------------

    8. Setzen Sie mit chmod Rechte vom Verzeichnis [docs] rekursiv auf [rw---xrwx]
    Rekusiv heisst, dass das Recht auch auf alle Unterverzeichnisse und Dateien angewendet wird
    ------------------------------------------------------------------------------------
    chmod u=rw,g=x,o=rwx -R
    ------------------------------------------------------------------------------------


    9. Setzen Sie mit ACL Rechte der neuen Datei [liste] wie folgt
    eigener Benutzer hat 0, root Benutzer hat 5
    ------------------------------------------------------------------------------------
    setfacl -R -m u:daan:0 /home/max/privat/schule/liste
    setfacl -R -m u:root:7 /home/max/privat/schule/liste
    ------------------------------------------------------------------------------------


    10. Setzen Sie mit ACL Rechte vom erstellten Verzeichnis [docs] wie folgt
    eigener Benutzer hat 7, root Benutzer hat 2
    ------------------------------------------------------------------------------------
    setfacl -R -m u:daan:7 /root/docs
    setfacl -R -m u:root:2 /root/docs
    ------------------------------------------------------------------------------------


    11. Verschieben Sie das erstellte Verzeichnis [business] nach /home/max/
    ------------------------------------------------------------------------------------
    mv /root/docs/business/ /home/max/
    ------------------------------------------------------------------------------------


    12. Benennen Sie das erstellte Verzeichnis [business] nach [business-related] um
    ------------------------------------------------------------------------------------
    mv /home/max/business/ /home/max/business-related
    ------------------------------------------------------------------------------------


    13. Verschieben Sie die erstellte Datei [liste] ins Verzeichnis [business-related]
    ------------------------------------------------------------------------------------
    mv /home/max/privat/schule/liste /home/max/business-related/
    ------------------------------------------------------------------------------------

    14. Löschen Sie das erstellte Verzeichnis [business-related] und die darin enthaltene Datei [liste] mit einem Befehl
    ------------------------------------------------------------------------------------
    rm -rf /home/max/business-related/
    ------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------
