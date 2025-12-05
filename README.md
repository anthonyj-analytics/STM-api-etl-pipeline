# STM-api-etl-pipeline
## Overview

This project demonstrates a fully automated real-time ETL data pipeline that retrieves live metro service status from the STM Open Data API, processes the JSON stream using FME Workbench, and updates a PostgreSQL/PostGIS database used for transit analysis.

The workflow authenticates to the STM API, then extracts and restructures the JSON response, before filtering relevant metro alerts (lines 1, 2, 4 and 5). The output is comprised of cleaned attributes written into a relational database where they can be joined with existing transit layers.

Although compact, this project showcases a complete end-to-end pipeline: API acquisition → transformation → validation → automated database write-back.

## Abilities Demonstrated

• API authentication and ingestion
Connection to the STM iBUS “État du Service” API, using API keys, authentication headers, and an OpenAPI specification to configure the HTTP request. The system retrieves real-time service alerts for Montreal’s metro network.

• JSON parsing and transformation
Using FME components—HTTPCaller, JSONFormatter, JSONFragmenter, and JSONExtractor—the pipeline isolates the relevant JSON nodes (alerts, informed entities, messages) and converts them into structured tabular attributes.

• Data filtering and attribute management
Logical filtering selects only metro-related alerts (lines 1, 2, 4, 5). Attribute cleaning ensures that only meaningful fields (line, message, info) are stored.

• Automated database integration (PostgreSQL/PostGIS)
A PostGIS writer pushes the processed alerts into a dedicated SQL table. The resulting dataset can be instantly joined with transit network layers for dashboards, maps, or additional analytics.

• Real-time ETL orchestration
The workflow is designed to run automatically and can provide up-to-date metro service information suitable for operational dashboards.

## Conclusion

This project illustrates my ability to design and implement a streamlined real-time ETL pipeline that combines API integration, JSON processing, and automated SQL output. Despite its modest scope, it demonstrates essential data-engineering skills: authentication, transformation logic, error-free structuring of semi-structured data, and integration with enterprise-grade databases. This type of workflow can be extended to larger pipelines, real-time monitoring systems, or scalable data ingestion architectures.
