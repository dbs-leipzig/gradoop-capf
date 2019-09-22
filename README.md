## Gradoop-CAPF: Cypher for Apache Flink

This [GRADOOP](https://github.com/dbs-leipzig/gradoop) operator is based on a work in progress master thesis of Sören Reichhard ([GitHub](https://github.com/soerenreichardt/cypher-for-apache-flink)). CAPF is based on Neo4j's [Morpheus](https://github.com/opencypher/morpheus) project and supports the opencypher grammar. CAPF will be released alongside 
every Gradoop stable release. 

## Usage

### Use CAPF with Gradoop

```
LogicalGraph graph = source.getLogicalGraph(...)

String cypherString = "MATCH ()-->() RETURN *";

//Create CAPFQuery Object and execute cypher query
CAPFResult result = new CAPFQuery(cypherString, getExecutionEnvirontment())
.execute(graph);

GraphCollection collection = result.getGraphs();
```


### Use CAPF dependencies

* Add the following dependency to your gradoop project.

```xml
<dependency>
    <groupId>org.gradoop</groupId>
    <artifactId>gradoop-capf</artifactId>
    <version>0.5.0</version>
</dependency>
```

* Executed on a cluster the following lib's has to be included (maven-shade-plugin)

```
<include>org.opencypher:*</include>
<include>org.apache.flink:flink-table_2.12</include>
<include>org.parboiled:parboiled-scala_2.12</include>
<include>com.lihaoyi:ujson_2.12</include>
<include>com.lihaoyi:upickle_2.12</include>
<include>org.typelevel:cats-kernel_2.12</include>
<include>org.typelevel:cats-core_2.12</include>
<include>org.atnos:eff_2.12</include>
<include>org.parboiled:*</include>
```

### Build requirements

* gradoop-capf requries Java 8
* CAPF requires scala 2.12

 