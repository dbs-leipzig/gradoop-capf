## Gradoop-CAPF: Cypher for Apache Flink

This [GRADOOP](https://github.com/dbs-leipzig/gradoop) operator is based on a work in progress master thesis of Sören Reichhard ([GitHub](https://github.com/soerenreichardt/cypher-for-apache-flink)). CAPF is based on Neo4j's [Morpheus](https://github.com/opencypher/morpheus) project and supports the opencypher grammar. CAPF will be released alongside 
every Gradoop stable release. 

## Usage

### Use CAPF with Gradoop

* Add the following dependency to your gradoop project.

```xml
<dependency>
    <groupId>org.gradoop</groupId>
    <artifactId>gradoop-capf</artifactId>
    <version>0.5.0</version>
</dependency>
```

### Build requirements

* gradoop-capf requries Java 8
* CAPF requires scala 2.12

 