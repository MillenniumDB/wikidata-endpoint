# Wikidata Endpoint

This page contains information about the Wikidata SPARQL endpoint available at
https://wikidata.imfd.cl/

The endpoint uses MillenniumDB, developed by the [Millennium Institute for Foundational Research on Data](https://imfd.cl/en/). It is still under development and licensed under GPL v2 license.
The source code is available [here](https://github.com/MillenniumDB/MillenniumDB). More details about the core of the engine, including some performance data, are available [in our paper](https://direct.mit.edu/dint/article/5/3/560/117375/MillenniumDB-An-Open-Source-Graph-Database-System). Since the paper was published, we have extended MillenniumDB to support SPARQL 1.1. (The underlying system supports further features not covered by the SPARQL syntax, such as returning paths.)

## Privacy policy

When you issue a request to our query service, we automatically receive
information like the time of the request, your I.P. address, the query
received, details of the agent (browser, etc.) that sent the request.
Currently we perform no persistent logging of such information. In
future we may log such information, which will not be shared with third
parties, and will only be used internally to help us to improve the
service.

## Usage policy

There is a 1 minute query limit. Queries that require longer processing will time out.

Currently we do not impose a result limit. However, if you have a query with millions of results the web interface may not work, or the engine may timeout.

## Hardware info

The service is currently running on a single machine in Chile
(Intel®Xeon®Silver 41.10 @2.10GHz CPU 30 cores (virtual), and 128GB of
DDR4/2666MHz RAM, running Ubuntu 22.04, with a PCIe 3.0 SSD). High
traffic may cause delays, and geographical distance may cause lag for
frequent simple queries.

## Limitations

MillenniumDB is under active development. Here we list some current limitations.

- The Wikidata dataset is currently loaded from weekly dumps, and thus updates
will be periodical for now.

- Some `FILTER` operations and complex BGPs with property paths (C2RPQs) may sometimes be slow
since we currently lack specific optimizations for these features.

- Blazegraph-specific features are not yet supported. `SERVICE` features
for labels, for example, are not supported.

- Some queries are currently disabled, such as catalog query answering
(e.g. count all triples), as they currently require processing the full
graph.

- There is no query caching, but sending the same query consecutively may give better performance due to storage caching.

- SPARQL Update and Named Graphs are not currently supported by
MillenniumDB, though this should not affect the current service.

- We have some differences to the SPARQL 1.1 Standard, more details [here](https://github.com/MillenniumDB/MillenniumDB/blob/main/doc/sparql/sparql_deviations.md).

If you wish to comment about such a limitation, please leave us feedback below.

## User Feedback

We are happy to receive feedback about the service and about MillenniumDB. If you wish to report a problem or suggestion, please use [this issue tracker](https://github.com/MillenniumDB/wikidata-endpoint/issues).
