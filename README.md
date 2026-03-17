# Cloud LLM Risk Scoring Dashboard

AI security analytics platform on AWS that evaluates LLM risks using OWASP categories and NIST guardrails, with scoring, tracking, and visualization

Perfect — this is the right move.
A strong README will guide your entire build and make your project look production-grade from day 1.

Below is a ready-to-use GitHub README.md tailored to your profile (cloud + security + AI).



# AWS LLM Risk Scoring Dashboard

OWASP LLM Top 10 + NIST AI RMF Aligned Security Analytics Platform

# Overview

This project demonstrates a production-style cloud-native security platform that evaluates risks in Large Language Model (LLM) applications.

It ingests findings from LLM systems (prompts, APIs, agents), maps them to:
	•	OWASP Top 10 for LLM Applications (2025)
	•	NIST AI Risk Management Framework (AI RMF)

…and computes a dynamic risk score with an executive-ready dashboard.

# Problem Statement

Modern AI/LLM applications introduce new security risks such as:
	•	Prompt Injection
	•	Sensitive Data Leakage
	•	Excessive Agent Autonomy
	•	System Prompt Exposure
	•	Supply Chain Risks

However, organizations lack:

❌ Standardized risk scoring
❌ Unified visibility across LLM apps
❌ Governance mapping (OWASP + NIST)
❌ Executive dashboards for AI risk posture

# Solution

This project builds a serverless AWS platform that:

✅ Ingests LLM security findings
✅ Maps them to OWASP LLM Top 10 categories
✅ Aligns them with NIST AI RMF controls
✅ Computes a weighted risk score
✅ Tracks remediation status
✅ Visualizes insights in a dashboard

# Architecture

Frontend (S3 / React - optional)
        ↓
API Gateway
        ↓
Lambda (Ingest Findings)
        ↓
DynamoDB (Findings Table)
        ↓
DynamoDB Streams
        ↓
Lambda (Risk Scoring Engine)
        ↓
DynamoDB (Summary Table)
        ↓
QuickSight Dashboard

# AWS Services Used
	•	Amazon API Gateway – API layer
	•	AWS Lambda – serverless compute
	•	Amazon DynamoDB – NoSQL storage
	•	DynamoDB Streams – event-driven processing
	•	Amazon QuickSight – dashboard visualization
	•	Amazon CloudWatch – logging & metrics
	•	AWS CloudTrail – audit logging

# Data Model

🔹 Findings Table (llm-risk-findings)

Stores individual LLM security findings.

Field	Description
applicationId	LLM application identifier
findingId	Unique finding ID
owaspId	OWASP category (LLM01, LLM02…)
severity	Low / Medium / High / Critical
confidence	Detection confidence
businessImpact	Impact level
exploitability	Attack feasibility
score	Computed risk score
nistFunction	Govern / Map / Measure / Manage
status	Open / Mitigated


# Summary Table (llm-risk-summary)

Stores aggregated risk metrics.

Field	Description
applicationId	LLM application
overallRiskScore	Final normalized score
openCriticalCount	Number of critical risks
owaspBreakdown	Category distribution
nistCoverageScore	Governance coverage
trend	Risk over time


# Risk Scoring Model

Risk score is calculated using:

Risk Score = Severity × Confidence × Exploitability × Business Impact × Exposure Modifier

Example Weights

Severity	Weight
Low	2
Medium	5
High	8
Critical	10

Modifiers
	•	Internet-facing → +25%
	•	Handles PII → +25%
	•	Agent-enabled → +30%
	•	Mitigation present → -30%

# OWASP LLM Top 10 Coverage

This project currently supports:
	•	LLM01 – Prompt Injection
	•	LLM02 – Sensitive Information Disclosure
	•	LLM05 – Supply Chain Vulnerabilities
	•	LLM06 – Excessive Agency
	•	LLM07 – System Prompt Leakage

#  NIST AI RMF Mapping

Each finding is mapped to:
	•	Govern
	•	Map
	•	Measure
	•	Manage

This enables:
	•	Compliance tracking
	•	Risk governance visibility
	•	Control gap analysis

# Dashboard Insights

The dashboard answers:
	•	Which LLM applications have the highest risk?
	•	Which OWASP categories dominate?
	•	Where are NIST control gaps?
	•	Are risks trending up or down?
	•	Which findings remain unresolved?

# Data Flow

POST /findings → API Gateway → Lambda → DynamoDB
                                   ↓
                          DynamoDB Streams
                                   ↓
                          Scoring Lambda
                                   ↓
                         Summary Table
                                   ↓
                          Dashboard (QuickSight)


# Sample Input

{
  "applicationId": "customer-support-bot",
  "findings": [
    {
      "id": "F-001",
      "category": "LLM01",
      "severity": "High",
      "confidence": 0.9,
      "description": "Prompt injection vulnerability"
    }
  ]
}


# How to Run (Coming Soon)
	•	Setup AWS infrastructure (Lambda, DynamoDB, API Gateway)
	•	Deploy backend services
	•	Ingest sample findings
	•	Generate dashboard

# Future Enhancements
	•	🔹 Integration with Amazon Bedrock Guardrails
	•	🔹 Automated scanning using AI agents
	•	🔹 Real-time alerting (SNS / EventBridge)
	•	🔹 Multi-tenant risk scoring
	•	🔹 React-based UI dashboard
	•	🔹 Integration with SAST tools (Semgrep, CodeQL)

# Portfolio Value

This project demonstrates:
	•	Cloud architecture (AWS serverless)
	•	AI/LLM security expertise
	•	Risk modeling and scoring
	•	OWASP & NIST alignment
	•	Event-driven system design
	•	Security observability
