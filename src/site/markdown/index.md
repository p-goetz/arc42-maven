### Dokumentation von Software Architekturen mit arc42

Dieses Maven Projekt bildet das arc42 Template zur Dokumentation von Software Architekturen ab. Die Dokumentation wird
dabei in [Markdown](http://markdown.de/) erstellt, graphische Modelle (z.B. in UML) können mit
[PlantUML](http://plantuml.sourceforge.net/) notiert werden und werden beim Build von Maven als Grafiken gerendert und
der Maven Site hinzugefügt.

Es gibt für jedes Kapitel aus dem arc42 Template eine Markdown Datei im Verzeichnis `src/site/markdown/doc`. Diese werden
wie gewünscht mit der Dokumentation befüllt. Graphische Modelle können im Verzeichnis `src/site/plantuml` in PlantUML
Syntax erstellt werden. Diese werden beim Aufruf von `mvn site` automatisch als PNG Grafiken gerendert. Über die normale
Markdown Syntax können diese Bilder in die Dokumentation eingebunden werden. So kann ein Modell in der Datei
`src/site/plantuml/domain-classes.puml` in der Dokumentation über den folgenden Verweis eingebunden werden:
`images/uml/domain-classes.puml` s. Beispiel unten.

![Beispiel UML-Modell](images/uml/domain-classes.png "Beispiel UML-Modell")

Über den Aufruf von `mvn site` wird die Dokumentation erzeugt und unter `target/site` abgelegt.

Die Seiten übergreifenden Texte können in `src/site/site.xml` auf das konkrete Projekt angepasst werden, z.B. Titel der
generierten Dokumentation. Der Text der Startseite wird in `src/site/markdown/index.md` geändert. Die Inhalte unter
"Project Information" werden großteils aus den Angaben in der `pom.xml` erzeugt.

Der Aufruf `mvn package` fasst die einzelnen Kapitel der Dokumentation (01 bis 12) zu einer Datei zusammen und kopiert
die resultierende Datei sowie die erzeugten Grafiken des UML Modells nach `target/markdown`, wo sie dann z.B. zu einem
einzigen PDF konvertiert werden könnten. Die Grafiken werden dabei natürlich so abgelegt, dass die Referenzierung aus
den Kapiteln heraus funktioniert wie im Beispiel oben.

Dieses Maven Projekt kann als Template frei und ohne Einschränkungen verwendet und verändert werden. Die einzige
Bedingung ist, dass ich als Autor mit Namen und E-Mail Adresse genannt werde (das darf
versteckt in der pom.xml sein). Bei Fragen könnt Ihr Euch gerne an mich wenden.

*Peter Götz* (peter.s.goetz@gmail.com)
