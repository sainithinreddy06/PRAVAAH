# PRAVAAH Evaluator Demo Guide

## What this demonstration shows

PRAVAAH demonstrates a structured workspace for approval-related records, evidence review, compliance obligations, readiness assessment, notifications, operational metrics, and audit traceability. Use synthetic demonstration records only.

## Suggested walkthrough

### 1. Introduce the problem

Explain how application review can involve multiple stakeholders, documents, deadlines, and changing requirements. The goal is to make workflow status and evidence easier to follow—not to replace authorized regulatory decisions.

### 2. Show the application workflow

- Sign in using an authorized demo account provided for the demonstration.
- Open an application and explain its current workflow state.
- Show the supported application details and state-transition actions.
- Explain how role and regional permissions limit access.

Do not share passwords or use real institutional personal data in a public demonstration.

### 3. Show evidence and compliance follow-up

- Open the evidence area and show document metadata and review actions.
- Explain that uploaded evidence has a stored digest and that download-time verification can detect changed file content.
- Open the obligations view and show ownership, due dates, and status.
- Show any available undertaking or readiness snapshot to explain how reviewers can identify outstanding items.

### 4. Show recommendations and notifications

Describe rule-based recommendations as transparent decision support based on configured workflow conditions. The supported notification channel is in-app; do not claim email or SMS delivery unless it has been separately implemented and verified in the environment being demonstrated.

### 5. Demonstrate audit integrity

- Open the administrator audit verification view or call the documented endpoint from an authorized session.
- Use only the result returned by the live environment.
- Explain the event count, whether the calculated chain head matches the stored head, and whether an invalid event was found.
- If presenting a previously recorded result, label it with its date and environment rather than describing it as a fresh test.

A hash-chain check detects certain changes to recorded events. It does not prove that all real-world actions were captured, that event contents were truthful, or that a privileged database operator could not rewrite both the events and chain head.

## Suggested closing

PRAVAAH connects workflow records, evidence, obligations, and audit verification in one demonstrable prototype. Its value is traceability and operational coordination, with human review retained for consequential decisions.

## Demo integrity checklist

- Use synthetic records and approved demo credentials.
- Distinguish implemented features from future integrations.
- Do not claim official AICTE endorsement or integration.
- Do not invent performance improvements or compliance outcomes.
- Show current test and audit results from the actual environment where possible.
