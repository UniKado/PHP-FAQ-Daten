# PHP-FAQ-Daten

Dieses Projekt stellt die Daten der PHP-FAQ von de.comp.lang.php in unterschiedlichen Formaten bereit

Einfach zum Bearbeiten auf Euren Rechner clonen mit:

`git clone https://github.com/UniKado/PHP-FAQ-Daten.git ./PHP-FAQ-Daten`

Ich hab lange überlegt in welchen Format man die Daten am sinnvollsten bereit stellt.

Es sollte definitiv ein Format sein das systemunabhängig einfach weiterverarbeitet werden kann.
Gut vom Menschen lesbar muss es eigentlich nicht sein. XML böte sich da sicher als gute Basis an.

Ich habs mal so gemacht:

Pro Format ist ein neues Unterverzeichnis in data/ und in api/ zu erstellen.

# Das XML Format

Die XML Version ist keine reine XML-Version, da die Beiträge wegen besserer Wartbarkeit
in separaten Dateien abgelegt werden die das HTML Format haben.

Der Aufbau sollte wie folgt aussehen:

- in categories.xml werden alle Kategorien definiert. (Formatbeschreibung steht in der XML-Datei)
- für jeden Alias einer Kategorie wird ein Unterverzeichnis angelegt das genau so heist wie der Alias
- in jedem Kategorie-Alias Unterverzeichnis wird eine Datei headers.xml angelegt in der die grundlegenden
  Informationen zu allen Beiträgen der Kategorie festgelegt werden. (Formatbeschreibung steht in der XML-Datei)
- Zu jeden Alias eines Beitrags der Kategorie wird eine HTML-Datei angelegt, in der die Beantwortung
  der FAQ-Frage definiert wird. Wenn der FAQ in headers.xml z.B. der Alias 'the-ultimate-answer' zugewiesen ist
  so musst die Beantwortung der FAQ-Frage in der Datei the-ultimate-answer.html, im selben Verzeichnis wie
  die header.xml angelegt werden.
