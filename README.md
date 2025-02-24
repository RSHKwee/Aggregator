# Aggregator

Prerequisite for building the projects:
The following tools are used and should be installed in advance:
- HTML Workshop version 4.74.8702.0 is used, for generating and maintaining the Help files (.chm).
- InnoSetup 6.4.0 is used, for creating the windows installers.

Aggregator is used by the following apps:
![Dependencies](./dependency-graph.png)

Some Maven commands (cheatsheet):
- mvn clean install
  voor bouwen en run tests ook al falen enkele.....

- mvn versions:display-dependency-updates
- mvn versions:display-plugin-updates
- mvn versions:display-parent-updates
- mvn versions:use-latest-releases
- mvn versions:use-latest-versions
- mvn io.github.floverfelt:pom-visualizer-maven-plugin:1.0.0:visualize
- mvn com.github.ferstl:depgraph-maven-plugin:aggregate -DcreateImage -Dincludes=kwee

