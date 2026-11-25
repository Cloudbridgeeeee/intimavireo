# IntimaVireo — proposed AWS architecture

IntimaVireo uses AWS to protect privacy at every step: encryption with KMS, anonymisation with Comprehend and careful analysis with Bedrock — all in your chosen region.

## Request flow

1. Feedback
2. AWS KMS
3. AWS Lambda
4. Comprehend
5. Bedrock
6. Amazon S3
7. Aggregate dashboards

## Services

### Amazon Comprehend

**Role:** Detect personal information

Finds names, contact details, addresses and order identifiers in feedback so they can be removed before any analysis or storage.

### Amazon Bedrock

**Role:** Classify, cluster and report

Classifies anonymised feedback into themes, clusters recurring issues and drafts aggregate improvement reports — with Guardrails keeping outputs factual and non-explicit.

### Amazon S3

**Role:** Store anonymised feedback

Keeps only anonymised feedback for analysis, encrypted at rest and separated per brand.

### AWS KMS

**Role:** Encrypt everything

Manages encryption keys for data at rest and in processing, with customer-managed key options for enterprise brands.

### AWS Lambda

**Role:** Run the privacy pipeline

Orchestrates detection, redaction, classification and aggregation, enforcing minimum group sizes before results reach dashboards.

## Principles

- **Anonymise first** — Personal information never reaches the analysis stage.
- **Aggregate only** — Minimum group sizes protect every customer.
- **Keys under control** — KMS encryption with customer-managed key options.

## Safeguards

- **Anonymised by default** — Personal details are removed before any analysis or storage.
- **No individual profiling** — Insights are aggregate, with a minimum group size of ten.
- **No medical claims** — Reports describe customer feedback; they don’t make health or therapeutic claims.
- **Encrypted throughout** — AWS KMS protects data at rest and in processing.

## MVP scope

We connect one or two feedback sources, anonymise and classify several months of feedback, and deliver aggregate product and service analytics with a first improvement report.

- Feedback import from 1–2 sources
- Automatic anonymisation
- Theme classification and clustering
- Aggregate dashboards
- First improvement report
