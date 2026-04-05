# FinOps for AI Demo Playbook

Hands-on demos reinforce each section of the syllabus with practical walk-throughs that can be delivered live or recorded. The following scenarios are optimized for AWS environments to match the current delivery preference. Every demo outlines the scenario, prerequisites, execution steps, and tangible takeaways.

## 1. AI Cost Allocation Demo
- **Maps to**: `02-ai-cost-allocation/allocating-ai-related-costs`
- **Tools**: AWS Cost Allocation Tags, Cost Explorer, AWS CUR sample dataset (CSV)
- **Setup**:
  1. Import a sanitized AWS Cost and Usage Report with GPU spend.
  2. Configure cost allocation tags for `Model`, `Owner`, and `Environment`.
- **Steps**:
  1. Show raw spend grouped by service to highlight lack of accountability.
  2. Enable tags and refresh Cost Explorer filters to allocate GPU charges.
  3. Export grouped results and pivot by business unit.
- **Deliverables**: Allocation workbook (CSV), screenshot deck illustrating pre/post tagging.
- **Key Takeaways**: Tag hygiene converts opaque accelerator costs into actionable chargeback data.

## 2. Data Sources Integration Demo
- **Maps to**: `03-data-sources-and-reporting/managing-ai-data-sources`
- **Tools**: AWS Cost and Usage Report (CUR), AWS Glue Data Catalog, Amazon Athena, Amazon QuickSight, sample ML metadata table stored in Amazon S3
- **Setup**:
  1. Configure an AWS CUR export with resource IDs enabled and deliver it to an S3 bucket.
  2. Add an AWS Glue crawler to catalog the CUR data for Athena queries.
  3. Upload a mock `ml_jobs.csv` (model, dataset, owner, environment) to S3 and catalog it with Glue.
- **Steps**:
  1. Use Athena to join CUR line items with the `ml_jobs` table, enriching costs with workload metadata.
  2. Save a query that surfaces GPU spend lacking the `Model` tag or owner metadata.
  3. Visualize the enriched dataset in QuickSight, highlighting spend by model, team, and tagging coverage.
- **Deliverables**: Athena SQL scripts, QuickSight dashboard link or screenshots, data quality checklist.
- **Key Takeaways**: Unified telemetry built on AWS CUR plus custom metadata enables trustworthy FinOps reporting.

## 3. Anomaly Detection Demo
- **Maps to**: `04-anomaly-detection-and-invoicing/managing-anomalies`
- **Tools**: AWS Cost Anomaly Detection, AWS Budgets, Amazon SNS/AWS Chatbot notifications, sample AI payer account
- **Setup**:
  1. Enable AWS Cost Anomaly Detection with a monitor scoped to GPU-related services (Amazon EC2 P/F instances, Amazon SageMaker, Amazon Bedrock).
  2. Configure an AWS Budget with thresholds at 80% and 110% of expected monthly spend and wire alerts to Slack or Teams via SNS + AWS Chatbot.
- **Steps**:
  1. Simulate a spike by launching a scripted GPU workload or replaying a historical spend file.
  2. Demonstrate how the anomaly alert surfaces in the console and notification channel, then trace the root cause.
  3. Execute the triage workflow: tag investigation, workload shutdown, escalation log, and catalog update.
- **Deliverables**: Monitor screenshots, SNS notification samples, incident playbook updates.
- **Key Takeaways**: Rapid detection plus predefined AWS response paths minimizes expensive overages.

## 4. Invoicing Analysis Demo
- **Maps to**: `04-anomaly-detection-and-invoicing/ai-invoices`
- **Tools**: AWS invoice PDF/CSV, spreadsheet template, procurement checklist
- **Setup**:
  1. Download a redacted invoice featuring Bedrock or SageMaker GPU usage.
  2. Prepare a reconciliation template referencing FinOps allocations.
- **Steps**:
  1. Highlight invoice line items tied to AI services and map to tagging fields.
  2. Reconcile totals against FinOps allocation outputs, noting deltas.
  3. Identify optimization opportunities (unused commitments, burst pricing).
- **Deliverables**: Annotated invoice, reconciliation log, optimization backlog entries.
- **Key Takeaways**: Deep invoice knowledge reveals savings and validates governance.

## 5. Forecasting Demo
- **Maps to**: `06-strategic-governance-and-planning/ai-forecasting`
- **Tools**: AWS Cost Explorer, AWS Cost Intelligence Dashboard (CUDOS), spreadsheet for scenario modeling
- **Setup**:
  1. Export 6–12 months of AI spend focused on services such as Amazon SageMaker, EC2 GPU families, and Bedrock usage.
  2. Document roadmap milestones (new model launches, inference expansions, procurement commitments) expected next quarter.
- **Steps**:
  1. Use Cost Explorer forecasts and seasonality trends to build a baseline.
  2. Extend the baseline in a spreadsheet, layering driver-based adjustments (GPU capacity adds, Savings Plans, expected adoption).
  3. Present base/aggressive/conservative scenarios with narrative commentary for executives.
- **Deliverables**: Cost Explorer exports, scenario workbook, executive-ready summary slide.
- **Key Takeaways**: AWS-native historical data combined with roadmap intelligence keeps forecasts credible.

## 6. Workload Optimization Demo
- **Maps to**: `07-advanced-optimization-and-certification/ai-workload-optimization`
- **Tools**: Amazon SageMaker Training Jobs, SageMaker Studio, TensorBoard Profiler, Amazon EKS with Karpenter for GPU scheduling
- **Setup**:
  1. Launch a sample BERT fine-tuning job in SageMaker using a baseline instance type (e.g., `ml.p3.2xlarge`).
  2. Enable SageMaker Profiler or TensorBoard to capture GPU and CPU utilization metrics.
- **Steps**:
  1. Highlight inefficiencies such as idle GPU time, underutilized CPUs, or lack of spot capacity usage.
  2. Apply optimizations: switch to managed spot training, adopt mixed precision, rightsize instance families, or migrate to EKS with Karpenter-driven autoscaling.
  3. Compare runtime, cost, and utilization metrics before vs. after adjustments.
- **Deliverables**: Profiler exports, optimization backlog entries, savings summary table.
- **Key Takeaways**: AWS-native tooling makes it straightforward to quantify and reclaim GPU spend.

## 7. Unit Economics Demo
- **Maps to**: `07-advanced-optimization-and-certification/unit-economics-for-ai-workloads`
- **Tools**: Spreadsheet or Amazon QuickSight dashboard, outputs from AWS allocation + forecasting demos
- **Setup**:
  1. Select an AWS-hosted AI product (e.g., Bedrock-powered chatbot or SageMaker inference endpoint).
  2. Gather volume metrics (API requests, tokens, customers) plus allocated costs derived from the CUR/Athena pipeline.
- **Steps**:
  1. Build a cost driver tree linking AWS services (SageMaker endpoints, API Gateway, Lambda, DynamoDB) to value streams.
  2. Calculate cost per 1K tokens or per customer interaction and benchmark vs. targets.
  3. Highlight levers to improve margins: inference autoscaling, model optimization, pricing adjustments, experimentation guardrails.
- **Deliverables**: Unit economics dashboard or spreadsheet, action plan, executive narrative.
- **Key Takeaways**: AWS cost transparency enables a clear link between technical efficiency and business value.

---

### Delivery Tips
- Record short demo videos (5–7 minutes) for asynchronous learners.
- Package datasets, scripts, and templates in a shared folder so participants can replicate results safely.
- Tie each demo to lesson objectives and end with reflection questions or quizzes.
