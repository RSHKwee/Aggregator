# Aggregator

mvn clean install

voor bouwen en run tests ook al falen enkele.....


mvn versions:display-dependency-updates
mvn versions:display-plugin-updates
mvn versions:display-parent-updates
mvn versions:use-latest-releases
mvn versions:use-latest-versions
mvn io.github.floverfelt:pom-visualizer-maven-plugin:1.0.0:visualize
mvn com.github.ferstl:depgraph-maven-plugin:aggregate -DcreateImage -Dincludes=kwee

