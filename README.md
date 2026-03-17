# Cloud LLM Risk Scoring Dashboard

This project demonstrates a production-style cloud-native security platform that evaluates risks in Large Language Model (LLM) applications.

It ingests findings from LLM systems (prompts, APIs, agents), maps them to:

		•	OWASP Top 10 for LLM Applications (2025)
		•	NIST AI Risk Management Framework (AI RMF)

and computes a dynamic risk score with a dashboard.

# Solution

This project builds a serverless AWS platform that:

	Ingests LLM security findings
	Maps them to OWASP LLM Top 10 categories
	Aligns them with NIST AI RMF controls
	Computes a weighted risk score
	Tracks remediation status
	Visualizes insights in a dashboard

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


# Risk Scoring Model

Risk score is calculated using:

	Risk Score = Severity × Confidence × Exploitability × Business Impact × Exposure Modifier


# Dashboard Insights

	•	Which LLM applications have the highest risk?
	•	Which OWASP categories dominate?
	•	Where are NIST control gaps?
	•	Are risks trending up or down?
	•	Which findings remain unresolved?

# Future Enhancements
	•	Integration with Amazon Bedrock Guardrails
	•	Automated scanning using AI agents
	•	Real-time alerting (SNS / EventBridge)
	•	Multi-tenant risk scoring
	•	React-based UI dashboard
	•	Integration with SAST tools (Semgrep, CodeQL)


