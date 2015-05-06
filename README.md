# arc42-maven

Maven project template for architecture documentation based on the arc42 template (s. http://www.arc42.de/) 

## Purpose

This Maven project template contains pre-filled markdown files to document software architecture based on the arc42 template. The markdown files can then be transformed to a Maven site to be published. 

For simple UML diagrams you can use PlantUML (http://plantuml.sourceforge.net/) files which will be rendered as images during the build process. To do this you need to have installed `graphvizdot`. If the `dot` executable is not in your path, please explicitly link it in the `pom.xml` (see comment in plantuml-maven-plugin `configuration` element). 

## Usage

The markdown input files can be found under `src/site/markdown`. The `index.md` contains detailed information on the template. The chapters of the arc42 template are stored in `src/site/markdown/doc`. Images can be linked using the standard markdown syntax and should be stored under `src/site/resources` (see example image at `index.md`). 

The site will be built with `mvn site` and is stored in the `target` directory. 
