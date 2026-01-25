# Demo Guide – AI Tender Compliance Automation

This document explains how the demo version of the AI-powered tender compliance system works and what to look for when reviewing the results.

---

## Demo purpose
This demo showcases how AI and workflow orchestration can automate tender compliance analysis.

The focus is on:
- Requirement extraction accuracy
- AI-based comparison logic
- Clear, structured compliance reporting

This is **not** a production deployment.

---

## Demo input
The demo uses **two uploaded documents**:

1. **Tender requirements document**
   - Contains multiple technical and functional requirements
   - Written in natural language (paragraphs and bullet points)

2. **Vendor proposal document**
   - Contains the vendor’s response to the tender
   - May fully, partially, or not address each requirement

Documents are uploaded through the demo web interface and sent to the system via webhook.

---

## What happens during the demo

### Step 1 – Tender processing
- The tender document is extracted as plain text.
- An AI agent parses the text and extracts individual requirements.
- Each requirement is converted into a structured item (Req1, Req2, …).

### Step 2 – Vendor processing
- The vendor proposal is extracted as plain text.
- The full content is preserved for semantic comparison.

### Step 3 – Requirement batching
- Extracted requirements are split into **four batches**.
- Each batch is processed independently to handle large documents and token limits.

### Step 4 – AI comparison
For each requirement:
- An AI agent compares the requirement against the **entire vendor proposal**.
- The requirement is classified as:
  - Fully Satisfied
  - Partially Satisfied
  - Not Satisfied
- A short justification sentence is generated.

### Step 5 – Aggregation & formatting
- Results from all AI agents are merged.
- Filters and AI summarization are applied.
- A structured compliance table and summary statistics are generated.

---

## Demo output

The demo interface displays:

### Summary view
- Total number of requirements
- Count of:
  - Fully Satisfied
  - Partially Satisfied
  - Not Satisfied

### Detailed table
For each requirement:
- Requirement ID
- Short title
- Compliance status
- AI-generated justification

---

## Important demo notes
- Internal workflows and AI prompts are **not exposed** publicly.
- Token and rate-limit handling is simplified for demonstration.
- The UI is intentionally minimal and focused on results.
- Output quality depends on the clarity of the uploaded documents.

---

## What this demo demonstrates
- AI-driven requirement extraction
- Token-aware multi-agent orchestration
- Reliable comparison at scale
- Clear, decision-ready reporting

---

## What is out of scope
- User authentication
- Document storage
- Role-based access control
- Legal validation of results

---

## Disclaimer
This demo is intended for **technical demonstration purposes only**.  
Final procurement or legal decisions should always involve human review.
