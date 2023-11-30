# Lab3
Es wird davon ausgegangen, dass Docker Desktop installiert und gestartet wurde. Falls dies nicht der Fall ist, muss dies installiert werden.

## Aufgabe1

Um die docker-compose.yml auszuführen muss diese zunächst runtergeladen werden. Anschließend muss über das Terminal zu dem Verzeichnis navigiert werden, in dem die Datei gespeichert wurde ```cd dein/Verzeichnis```.
Sobald das Verzeichnis erreicht wurde, wird in das Terminal folgendes eingegeben: ```docker-compose up -d```
Nun sollte folgende Anzeige angezeigt werden:
![Lab3Auf1](https://github.com/RatteF/Lab3/assets/83348757/a36942d3-ee8a-4552-b705-4439929bc84f)
Nun sollten Sie, wenn sie folgenden Link aufsuchen http://localhost:8080/, eine wp-admin/install sehen.

## Aufgabe2

Hier wird zunächst der Ordner runtergeladen. Anschließend muss im Terminal dann zu diesem Ordner navigiert werden. Nun wird die "Wordpress-Dockerfile" mit dem Befehl ```docker build -t custom-wordpress ./wordpress-eigenes-image``` gestartet.

Danach muss die "MYSQL-Dockerfile" gestartet werden mit dem Befehl ```docker build -t custom-mysql ./mysql-eigenes-image``` und dann taucht eine Fehlermeldung auf.
![Error1](https://github.com/RatteF/Lab3/assets/83348757/9885d4af-33f0-4e80-ba0f-1ee6914c0b92)
![Error2](https://github.com/RatteF/Lab3/assets/83348757/c2188056-3a8d-44fa-acb8-3d069e856a2d)

Der Fehler scheint auf ein Problem mit dem Sicherheitsschlüssel hinzuweisen. Ich hatte verschiedene Lösungsansätze probiert, jedoch den Fehler nicht beseitigen können. Auch habe ich versucht auf den Sicherheitsschlüssel zu verzichten, jedoch traten daraufhin Zertifikationsprobleme auf. Ich hatte dann noch weiter versucht, das Dockerfile zum Laufen zu bringen, jedoch ohne Erfolg.
