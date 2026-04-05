# Managing AI Data Sources

## Purpose
Build authoritative, timely data pipelines that blend cloud billing, GPU telemetry, and ML platform metadata.

## Learning Objectives
- Catalog the systems supplying AI cost, usage, and performance data
- Define data quality SLAs for ingestion frequency, lineage, and reconciliation
- Align AI data governance controls with FinOps reporting needs

## Discussion Topics
- Billing exports (AWS CUR, Azure CEF, GCP BQ exports) with AI-specific dimensions
- GPU fleet telemetry, job schedulers, and ML platform metadata
- Data stewardship roles and exception handling

## Practical Activities
- Create a data inventory sheet listing producers, consumers, refresh cadence, and owners
- Design validation rules for tagging completeness and GPU utilization accuracy
- Run a mock incident response for missing AI telemetry and define escalation paths

## Artifacts & Metrics
- AI FinOps data inventory
- Data quality checklist
- Incident response playbook

## References
- FinOps data ingestion guidance: https://www.finops.org/framework/capabilities/data-ingestion/
- OpenTelemetry for GPUs and ML workloads (CNCF blogs)
