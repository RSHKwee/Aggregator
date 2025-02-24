# Aggregator

Prerequisite for building the projects:

The following tools are used and should be installed in advance:
- HTML Workshop version 4.74.8702.0 is used, for generating and maintaining the Help files (.chm).
- InnoSetup 6.4.0 is used, for creating the windows installers.

Aggregator is used by the following projects:
![Dependencies](./dependency-graph.png)

This repository consists of:
- Buildtools, these are a common library for InnoSetup scripts and some script files.
- A JRE which is included in the installer.

Some Maven commands (cheatsheet):
- mvn clean install, for building and run tests.
- mvn versions:display-dependency-updates, check Dependencies
- mvn versions:display-plugin-updates
- mvn versions:display-parent-updates
- mvn versions:use-latest-releases
- mvn versions:use-latest-versions
- mvn io.github.floverfelt:pom-visualizer-maven-plugin:1.0.0:visualize
- mvn com.github.ferstl:depgraph-maven-plugin:aggregate -DcreateImage -Dincludes=kwee

