# Prerequisite

Prerequisite for building the projects:

The following tools are used and should be installed in advance:
- _HTML Workshop_ (version 4.74.8702.0), is used for generating and maintaining the Help files (.chm).
- _InnoSetup_ (version 6.4.0), is used for creating the windows installers.

Build projects with command: _mvn clean install_

# Content repository
Aggregator is used by the following projects:
![Dependencies](./dependency-graph.png)

This repository consists of:
- Buildtools, these are a common library for InnoSetup scripts and some script files.
- A JRE which is included in the installer.

# Cheatsheet
Maven cycles:

Voert pre-clean → clean uit
Voert validate → compile → test → package → verify → install uit

FASE                    | WAT GEBEURT ER
-----------------------|------------------------------------------------
CLEAN LIFECYCLE:
  pre-clean            | 
  clean                | Verwijderd target/ directory
  post-clean           |
                       
DEFAULT LIFECYCLE:
  validate             | Controleert POM
  initialize           | Initialiseert build
  generate-sources     | Genereert broncode (jaxb, etc.)
  process-sources      | Verwerkt broncode
  generate-resources   | 
  process-resources    | Kopieert resources naar target/classes
  compile              | Compileert Java code
  process-classes      | Bytecode manipulatie (aspectj, etc.)
  generate-test-sources| 
  process-test-sources | 
  generate-test-resources | 
  process-test-resources | 
  test-compile         | Compileert test code
  process-test-classes | 
  test                 | Voert JUnit tests uit
  prepare-package      | Voorbereiding voor packaging
  package              | Maakt JAR/WAR (assembly uber-jar)
  pre-integration-test | 
  integration-test     | 
  post-integration-test| 
  verify               | Extra checks (jpackage + jouw cleanup)
  install              | Installeert artifact + maakt distributie


PHASE                 | JOUW PLUGINS/ACTIES
---------------------|-------------------------------------------------
initialize           | maven-resources-plugin (CopyTools)
generate-resources   | exec-maven-plugin (HelpChm - help bestanden)
process-resources    | maven-resources-plugin (readme.md)
compile              | maven-compiler-plugin (standaard)
test                 | maven-surefire-plugin (standaard)
package              | 1. assembly:create-uber-jar
                     | 2. launch4j (maakt .exe)
                     | 3. jsign (tekent .exe)
                     | 4. maven-resources-plugin (kopieert help)
verify               | 1. jpackage (maakt USB/Programs)
                     | 2. maven-antrun-plugin (cleanup-temp-files)
install              | 1. assembly:create-distribution
                     | 2. Installeert artifact in ~/.m2/repository

Some Maven commands (cheatsheet):
- _mvn clean install_, for building and run tests.
- _mvn versions:display-dependency-updates_, check Dependencies
- _mvn versions:display-plugin-updates_
- _mvn versions:display-parent-updates_
- _mvn versions:use-latest-releases_
- _mvn versions:use-latest-versions_
- _mvn io.github.floverfelt:pom-visualizer-maven-plugin:1.0.0:visualize_
- _mvn com.github.ferstl:depgraph-maven-plugin:aggregate -DcreateImage -Dincludes=kwee_
- _mvn install -DskipTests_


