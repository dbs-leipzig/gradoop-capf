[![Apache License, Version 2.0, January 2004](https://img.shields.io/github/license/apache/maven.svg?label=License)](https://www.apache.org/licenses/LICENSE-2.0)
[![Maven Central](https://img.shields.io/badge/Maven_Central-0.5.1-blue.svg?label=Maven%20Central)](http://search.maven.org/#search%7Cga%7C1%7Cgradoop)
[![Build Status](https://travis-ci.org/dbs-leipzig/gradoop-capf.svg?branch=develop)](https://travis-ci.org/dbs-leipzig/gradoop-capf)

## Gradoop-CAPF: Cypher for Apache Flink

This [GRADOOP](https://github.com/dbs-leipzig/gradoop) operator is based on a work in progress master thesis ([GitHub](https://github.com/soerenreichardt/cypher-for-apache-flink)). CAPF is based on Neo4j's [Morpheus](https://github.com/opencypher/morpheus) project and supports the opencypher grammar. CAPF will be released alongside 
every Gradoop stable release. An example on how to use this operator is provided below and within the Gradoop 
[Wiki](https://github.com/dbs-leipzig/gradoop/wiki/Unary-Logical-Graph-Operators#pattern-matching).

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
    <version>0.5.1</version>
</dependency>
```

* Executed on a cluster the following lib's has to be included (maven-shade-plugin)

```
<include>org.gradoop:gradoop-capf</include>
<include>org.opencypher:*</include>
<include>org.apache.flink:flink-table_2.12</include>
<include>org.parboiled:parboiled-scala_2.12</include>
<include>com.lihaoyi:ujson_2.12</include>
<include>com.lihaoyi:upack_2.12</include>
<include>com.lihaoyi:upickle_2.12</include>
<include>com.lihaoyi:upickle-core_2.12</include>
<include>com.lihaoyi:upickle-implicits_2.12</include>
<include>org.typelevel:cats-kernel_2.12</include>
<include>org.typelevel:cats-core_2.12</include>
<include>org.atnos:eff_2.12</include>
<include>org.parboiled:*</include>
```

### Build requirements

* gradoop-capf requries Java 8
* CAPF requires scala 2.12

 