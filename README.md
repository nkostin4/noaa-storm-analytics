# NOAA Storm Analytics

A documentation-first data engineering project that ingests publicly available data from the [NOAA Storm Events Database](https://www.ncei.noaa.gov/access/storm-events-database/), processes it through a [medallion architecture](https://www.databricks.com/blog/what-is-medallion-architecture), and makes curated datasets available for analytical querying using AWS.

!Architecture Diagram

---

## Project Overview

This project demonstrates the design and implementation of a cloud-based data lake using publicly accessible storm events observations from the National Oceanic and Atmospheric Administration (NOAA).

The data lake adheres to the **medallion architecture**, organizing data into three progressively refined layers:

- **Bronze**: Raw data ingested from the Storm Events Database and preserved in its original format.
- **Silver**: Cleaned, standardized, validated, and structured data.
- **Gold**: Aggregated, analytics-ready datasets designed to support downstream querying and analysis.

This project emphasizes not only the implemenation of a functional data pipeline, but also the documentation of architectural decisions, data transformations, data lineage, data quality expectations, and operational procedures.

### Project Objectives

1. Build an end-to-end data ingestion and transformation pipeline.
2. Implement a medallion architecture using Amazon S3.
3. Provision cloud infrastructure using AWS CloudFormation.
4. Make curated datasets accessible through AWS Glue and Amazon Athena.
5. Establish data quality check and validation rules.
6. Document the architecture, data models, lineage, and operational procedures.
7. Demonstrate reproducability through automated deployment and execution instructions.

---

## Data Source

The project uses the **Storm Events Database** provided by NOAA's National Centers for Environmental Information.

**Source**: <https://www.ncei.noaa.gov/access/storm-events-database/>

The Storm Events Database is a collection of significant weather phenomena that have sufficient intensity to cause loss of life, injuries, significant property damage, and/or disruption to commerce in the United States and adjacent water bodies.

### Scope

To keep the project manageable, the initial implementation limits ingestion to the years from 2020 to 2026.

## Data Quality

Data quality checks are performed during the transformation process.

The initial implementation focuses on the following dimensions:

| **Dimension** | **Validation** |
| --- | --- |
| Completeness | Required columns and values are present. |
| Validity | Values conform to expected data types and formats. |
| Uniqueness | Duplicate station/date/measurement combinations are identified |
| Consistency | Measurement units and data types are standardized |
| Accuracy | Plausible value ranges are evaluated. |

Validation outcomes are recorded and made available for inspection.

---

## Getting Started

Before running the project, ensure that

- Git is installed
- an AWS account with appropriate IAM roles is available

### Clone the Repository

```
git clone https://github.com/nkostin4/noaa-storm-analytics.git

cd noaa-storm-analytics
```

## Querying the Data

Curated datasets are registered in AWS Glue and can be queried through Amazon Athena.

Example SQL query

## Project Scope and Limitations

The project is intentionally scoped as a small, reproducible data engineering implementation.

The following capabilities are outside the scope of the initial version:
    - Automated schema evolution
    - Multi-region AWS deployment
    - Production-grade alerting and observability
    - Enterprise-scale access governance

These limitations are deliberate and provide opportunities for future enhancements.

## Future Enhancements

Potential future improvements include:
    - Add additional NOAA datasets
    - Create a dashboard for exploring Gold-layer datasets.

## License

This project is distributed under the GNU General Public License v3.0. See LICENSE for details.

---

**Project Status**: Initial Development
**Maintainer**: Nicholas Kostin
**Last Updated**: 2026-11-17
