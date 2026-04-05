# Managing Anomalies

## Purpose
Institute rapid detection and response workflows for unexpected AI spend surges.

## Learning Objectives
- Define anomaly signals tailored to AI workloads (GPU queue spikes, token overages, rogue fine-tuning)
- Build incident triage processes that engage engineering within hours, not days
- Quantify business impact and capture remediation learnings for future prevention

## Discussion Topics
- Threshold- vs. ML-based anomaly detection strategies
- Noise reduction techniques for experimentation-heavy environments
- Governance hooks: kill switches, budget alerts, FinOps response teams

## Practical Activities
- Configure sample alerts using historical GPU utilization data
- Run a tabletop exercise walking through escalation, comms, and root cause analysis
- Document post-incident review template optimized for AI anomalies

## Artifacts & Metrics
- Alert catalog
- Incident playbook
- Post-incident review template

## References
- FinOps anomaly management: https://www.finops.org/framework/capabilities/anomaly-management/
- Cloud provider anomaly tools (AWS CUDOS, Azure Cost Alerts, GCP Recommender)
