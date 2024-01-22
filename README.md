# Wikidata Endpoint

This page contains information about the wikidata SPARQL endpoint available at
https://wikidata.imfd.cl/

The endpoint is using MillenniumDB, developed by the Millennium Institute for Foundational Research on Data. It is still under development and licensed under GPL v2 license.
The source code is available [here](https://github.com/MillenniumDB/MillenniumDB).

## Privacy policy
When you issue a request to our query service, we automatically receive
information like the time of the request, your I.P. address, the query
received, details of the agent (browser, etc.) that send the request.
Currently we perform no persistent logging of such information. In
future we may log such information, which will not be shared with third
parties, and will only be used internally to help us to improve the
service.


## Usage policy
There is a 1 minute query limit.

Currently we do not impose a result limit. However, if you have a query with millions of results the web interface will probably not work, or the engine will timeout.

## Hardware info

The service is currently running on a single machine in Chile
(Intel®Xeon®Silver 41.10 @2.10GHz CPU 30 cores (virtual), and 128GB of
DDR4/2666MHz RAM, running Ubuntu 22.04, with a PCIe 3.0 SSD). High
traffic may cause delays, and geographical distance may cause lag for
frequent simple queries.

## Limitations
- The dataset is currently loaded from weekly dumps, and thus updates
will be periodically for now.

- FILTERs and BGPs with property paths (C2RPQs) may sometimes be slow
since we lack specific optimizations for these features.

- BlazeGraph specific features are not yet supported. SERVICE features
for labels, for example, are not supported.

- Some queries are currently not functioning, such as catalog query answering
(e.g. count all triples), as they currently require processing the full
graph.

- There is no query caching, but sending the same query consecutively may give better performance due to storage caching.

- SPARQL Update and Named Graphs are not currently supported by
MillenniumDB, though this should not affect the current service.

- We have some differences to the SPARQL 1.1 Standard, more details [here](https://github.com/MillenniumDB/MillenniumDB/blob/main/doc/sparql/sparql_deviations.md).

## User Feedback
If you wish to report a problem or suggestion, please use [this repository issues](https://github.com/MillenniumDB/wikidata-endpoint/issues).
