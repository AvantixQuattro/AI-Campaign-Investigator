# AI Campaign Investigator
## Business Requirements & Research Project Specification

**Document status:** Draft for implementation  
**Project type:** AI research / technical assessment project  
**Primary audience:** Prospective employer, CTO, engineering leadership, AI/ML leadership  
**Primary objective:** Evaluate the measurable value of an AI Agent for open-ended loyalty-program business investigation  
**Initial dataset:** dunnhumby — The Complete Journey  
**Target architecture:** PostgreSQL + pgvector, Python Agent, LLM API, Web UI

---

## 1. Executive Summary

This project is a research-oriented prototype designed to determine whether an **AI Agent provides measurable value over conventional SQL/rule-based analytics and conventional ML/statistical approaches** when investigating loyalty-program performance and generating evidence-based marketing hypotheses.

The system, referred to as **AI Campaign Investigator**, will assist a marketing professional with questions such as:

> "Why did win-back campaign performance decline during the last three months, and what should we investigate next?"

The Agent will not replace deterministic analytics or ML. Instead, it will orchestrate specialized analytical capabilities:

- SQL-based quantitative analysis;
- statistical/ML models where appropriate;
- semantic retrieval of historical campaign knowledge;
- multi-step investigation;
- hypothesis generation;
- evidence synthesis;
- recommendation generation.

The core research question is:

> **Can an AI Agent materially improve the speed, quality, breadth, and usefulness of open-ended loyalty-program investigations compared with conventional analytical approaches?**

The project is explicitly intended to test this hypothesis rather than assume that AI is superior.

---

# 2. Research Hypotheses

## 2.1 Primary hypothesis

**H1**

> For open-ended loyalty business investigations requiring synthesis of structured customer/campaign data and unstructured business knowledge, an AI Agent can provide higher-quality and/or faster insights than deterministic SQL/rule-based and conventional ML/statistical approaches.

## 2.2 Null hypothesis

**H0**

> An AI Agent does not provide a material advantage over conventional SQL/rule-based and ML/statistical approaches for the selected loyalty-program investigation tasks.

## 2.3 Important qualification

The project does **not** assume that AI is the best solution for every analytical task.

For deterministic calculations, SQL is expected to be superior.

For predictive problems such as churn propensity, response prediction, or uplift estimation, conventional ML may be superior.

The research focuses specifically on tasks involving:

- ambiguous business questions;
- iterative investigation;
- heterogeneous information sources;
- unstructured marketing knowledge;
- hypothesis formation;
- selection of subsequent investigative steps.

---

# 3. Business Problem

A loyalty-program organization typically has several information sources:

- customer transactions;
- customer attributes;
- campaign definitions;
- campaign exposure;
- campaign results;
- promotions;
- product/category information;
- experiment results;
- campaign briefs;
- marketer hypotheses;
- post-mortems;
- analyst comments;
- decision logs.

Conventional BI systems are highly effective at answering predefined questions:

> What was the campaign ROI?

> Which segment had the highest conversion?

> How many customers redeemed the offer?

However, business stakeholders frequently ask open-ended questions:

> Why did performance decline?

> What changed?

> Have we seen something similar before?

> What could explain the change?

> What should we investigate next?

> Which previous experiments are relevant?

Answering these questions typically requires a human analyst to manually:

1. interpret the question;
2. identify relevant metrics;
3. formulate SQL queries;
4. inspect segments;
5. compare historical periods;
6. search campaign documentation;
7. review previous experiments;
8. formulate hypotheses;
9. validate hypotheses;
10. produce a recommendation.

The project investigates whether an AI Agent can reduce this manual analytical workflow while preserving factual correctness and analytical rigor.

---

# 4. Project Objectives

## 4.1 Primary objectives

The system shall:

1. Investigate open-ended loyalty-program business questions.
2. Dynamically select appropriate analytical tools.
3. Query structured data through controlled interfaces.
4. Search unstructured campaign knowledge using semantic retrieval.
5. Use statistical/ML analysis where appropriate.
6. Compare current situations with historical campaigns.
7. Generate explicit hypotheses.
8. Distinguish facts, inferences, hypotheses, and recommendations.
9. Provide evidence for quantitative and qualitative conclusions.
10. Produce actionable recommendations for a marketing professional.
11. Record an auditable investigation trace.
12. Measure the performance of the AI approach against conventional baselines.

## 4.2 Secondary objectives

The project shall also demonstrate:

- modular AI-agent architecture;
- safe interaction between LLMs and databases;
- replaceable datasets;
- replaceable LLM providers;
- production-oriented engineering practices;
- reproducible evaluation;
- measurable AI economics.

---

# 5. Scope

## 5.1 In scope

The MVP will support:

- loyalty customer analytics;
- campaign performance analysis;
- customer-segment analysis;
- campaign comparison;
- historical campaign retrieval;
- marketing-knowledge retrieval;
- multi-step investigation;
- hypothesis generation;
- evidence-backed recommendations;
- statistical analysis;
- optional ML models;
- investigation trace;
- evaluation against conventional approaches;
- cost and performance measurement;
- web-based demonstration interface.

## 5.2 Out of scope

The MVP will not:

- automatically launch campaigns;
- modify customer records;
- send offers to customers;
- make irreversible business decisions;
- claim causal relationships without appropriate statistical evidence;
- replace an ML model where an ML model is demonstrably the appropriate solution;
- expose unrestricted database access to the LLM;
- rely on LLM-generated numerical calculations when deterministic calculation is available.

---

# 6. Target Users

## 6.1 Primary user

**Marketing Analyst / CRM Manager / Loyalty Manager**

The user is expected to understand:

- campaigns;
- customer segments;
- KPIs;
- marketing experiments;
- business objectives;

but should not need to write SQL or understand the internal Agent architecture.

## 6.2 Secondary users

- Data Analyst
- Data Scientist
- AI Engineer
- CTO / Technical Lead
- Product Manager

---

# 7. Core User Experience

The primary interaction is a natural-language business question.

Example:

> **Why did win-back campaign performance decline during the last three months?**

The Agent should:

```text
Business Question
        |
        v
Interpret objective
        |
        v
Initial investigation
        |
        +---- SQL / structured data
        |
        +---- Statistical analysis
        |
        +---- Historical campaign search
        |
        +---- Marketing knowledge search
        |
        v
Generate hypotheses
        |
        v
Test / refine hypotheses
        |
        v
Synthesize evidence
        |
        v
Recommendations
```

The system should not require the user to specify the analytical procedure.

---

# 8. Representative Business Scenarios

The MVP shall support ten representative scenarios.

## Scenario 1 — Campaign Performance Decline

> Why did win-back campaign performance decline during the last three months?

Expected investigation:

- establish baseline;
- identify affected segments;
- compare customer composition;
- inspect campaign exposure;
- inspect offer characteristics;
- search historical analogues;
- formulate and test hypotheses.

## Scenario 2 — Segment Deterioration

> Which customer segments are showing the most concerning behavioral deterioration?

Expected output:

- affected segments;
- relevant metrics;
- magnitude of change;
- historical comparison;
- possible explanations.

## Scenario 3 — Historical Campaign Similarity

> Have we previously seen a situation similar to the current one?

Expected output:

- similar campaigns;
- similarity rationale;
- actual outcomes;
- relevant lessons.

## Scenario 4 — Campaign Comparison

> Why did Campaign A outperform Campaign B?

The Agent should compare:

- audience;
- offer;
- timing;
- exposure;
- customer behavior;
- campaign outcomes;
- historical precedents.

## Scenario 5 — Reactivation Opportunity

> Which customer populations currently represent the strongest reactivation opportunity?

The Agent may use analytical models but must explain the evidence behind the recommendation.

## Scenario 6 — Campaign Fatigue

> Is campaign fatigue a plausible explanation for declining response?

The Agent should:

- formulate the hypothesis;
- identify relevant exposure metrics;
- test association;
- search historical evidence;
- distinguish association from causation.

## Scenario 7 — Previous Experiment Evidence

> What previous experiments support or contradict the proposed approach?

The Agent should search campaign knowledge and compare documented hypotheses with observed results.

## Scenario 8 — Unexpected KPI Movement

> Redemption increased, but campaign ROI decreased. Why?

The Agent should investigate:

- redemption;
- reward cost;
- incremental revenue;
- customer composition;
- offer economics;
- campaign mix.

## Scenario 9 — Marketing Knowledge Retrieval

> What have we learned historically about reactivating high-value customers?

The Agent should synthesize multiple campaign briefs, post-mortems, notes, and results.

## Scenario 10 — Next Investigation

> What should the marketing team investigate next?

The Agent should prioritize unresolved hypotheses based on:

- potential business impact;
- available evidence;
- uncertainty;
- feasibility of validation.

---

# 9. Data Requirements

## 9.1 Primary dataset

The initial implementation shall use:

**dunnhumby — The Complete Journey**

The dataset provides real retail loyalty-style historical data including customer households, transactions, campaigns, promotions, coupons, and campaign-related information.

The dataset is static. The prototype shall therefore support a **historical replay/simulation layer** so that data can be exposed progressively by simulated time period.

## 9.2 Dataset abstraction

The system shall not hard-code the application to dunnhumby-specific identifiers.

A logical data model shall separate:

- canonical business entities;
- source-specific mappings;
- source ingestion;
- analytical views.

The system should allow a future dataset to replace the initial dataset without redesigning the Agent.

## 9.3 Synthetic marketing knowledge

The public dataset does not provide a complete corpus of real internal marketing briefs, post-mortems, decision logs, and marketer notes.

Therefore, the project shall create a **synthetic marketing-knowledge layer**.

These documents shall be explicitly labeled as synthetic.

The synthetic documents must be **grounded in actual dataset facts**.

Examples:

- campaign brief;
- campaign hypothesis;
- experiment plan;
- campaign result summary;
- post-mortem;
- marketer note;
- decision log.

Quantitative statements in synthetic documents shall be generated from or validated against the structured dataset.

The system shall never represent synthetic documents as real company documents.

## 9.4 Intentionally conflicting knowledge

The evaluation dataset should contain selected synthetic documents where the documented marketer interpretation is incomplete, questionable, or contradicted by structured evidence.

Example:

> Marketing team hypothesis: the campaign failed because the offer was insufficient.

Structured data may show:

- redemption increased;
- reward cost increased;
- incremental revenue did not increase.

The Agent should identify the discrepancy rather than blindly repeat the documented hypothesis.

---

# 10. Data Model — Logical View

The core logical entities should include:

```text
Customer
CustomerSegment
Product
Category
Transaction
Basket
Campaign
CampaignAudience
CampaignExposure
CampaignResult
Promotion
Experiment
MarketingDocument
CampaignHypothesis
CampaignPostMortem
MarketingNote
DecisionLog
```

The model should support temporal analysis.

Important dimensions include:

- customer;
- campaign;
- product/category;
- segment;
- date/week;
- offer;
- exposure;
- outcome.

---

# 11. Analytical Architecture

## 11.1 High-level architecture

```text
                         Web UI
                           |
                           v
                    Agent API / Backend
                           |
                           v
                    AI Campaign Agent
                           |
            +--------------+--------------+
            |              |              |
            v              v              v
       SQL Tools       RAG Tools      ML/Stats Tools
            |              |              |
            v              v              v
       PostgreSQL       pgvector      Python/SQL
            |
            +-----------------------------+
            |
            v
      Structured Data
      Marketing Knowledge
```

## 11.2 Core technology stack

The reference implementation shall use:

- **PostgreSQL** for structured data;
- **pgvector** for vector retrieval;
- **Python** for Agent and analytical services;
- **LLM API** for language reasoning and synthesis;
- **Web UI** for demonstration;
- containerized deployment;
- automated deployment pipeline.

The architecture should keep the LLM provider abstract enough to allow substitution.

---

# 12. AI Agent Architecture

## 12.1 Agent role

The LLM is not the analytical database and is not the system of record.

The Agent acts as an **investigation orchestrator**.

Its responsibilities are:

1. interpret the business question;
2. identify required evidence;
3. select appropriate tools;
4. evaluate returned evidence;
5. formulate hypotheses;
6. select subsequent investigations;
7. synthesize results;
8. produce recommendations.

## 12.2 Tool categories

The MVP shall provide a limited set of controlled tools.

### Structured-data tools

Examples:

```text
get_campaign_metrics()
get_segment_metrics()
compare_periods()
get_customer_behavior()
get_campaign_exposure()
compare_campaigns()
```

### Knowledge retrieval tools

Examples:

```text
search_campaign_knowledge()
find_similar_campaigns()
search_postmortems()
search_experiments()
```

### Statistical / analytical tools

Examples:

```text
analyze_exposure_vs_response()
calculate_segment_change()
run_statistical_test()
```

The exact implementation may evolve.

## 12.3 Agent loop

The intended interaction pattern is:

```text
Question
   |
   v
Reason about required evidence
   |
   v
Tool call
   |
   v
Observation
   |
   v
Update hypothesis
   |
   v
Next tool call
   |
   v
...
   |
   v
Evidence-backed conclusion
```

The system is therefore **Agentic RAG / tool-augmented Agent**, not a single-pass RAG application.

---

# 13. RAG Requirements

RAG shall be used specifically for unstructured or semi-structured business knowledge.

The system shall support semantic retrieval of:

- campaign briefs;
- hypotheses;
- post-mortems;
- experiment reports;
- marketer notes;
- decision logs.

RAG shall not replace SQL for numerical analysis.

The Agent shall combine:

```text
Structured evidence
        +
Retrieved knowledge
        +
Statistical/ML evidence
```

before generating a final recommendation.

---

# 14. LLM Interaction Requirements

## AI-001 — Evidence-based reasoning

The Agent shall ground quantitative claims in tool results.

## AI-002 — Fact / inference / hypothesis separation

The output shall clearly distinguish:

- **Fact** — directly observed from data or documents;
- **Inference** — interpretation supported by evidence;
- **Hypothesis** — plausible explanation requiring further validation;
- **Recommendation** — proposed action or next investigation.

## AI-003 — No unsupported quantitative claims

The LLM shall not invent:

- KPI values;
- customer counts;
- campaign results;
- dates;
- statistical significance;
- ROI.

## AI-004 — Causality discipline

Correlation shall not be presented as causation without appropriate causal evidence.

## AI-005 — Evidence citation

Important conclusions shall identify the supporting source/tool result.

## AI-006 — Insufficient evidence

The Agent shall explicitly state when available evidence is insufficient.

## AI-007 — Contradiction detection

The Agent should identify conflicts between:

- structured data;
- historical documentation;
- marketer hypotheses.

## AI-008 — Dynamic investigation

The Agent should be capable of selecting different investigative paths for different questions.

## AI-009 — No unrestricted database access

The LLM shall not receive unrestricted database credentials or arbitrary production write access.

## AI-010 — Read-only analytical access

MVP analytical database access shall be read-only from the Agent perspective.

---

# 15. Security Requirements

The system shall follow production-oriented security principles.

## 15.1 Database security

- read-only Agent database credentials;
- parameterized queries;
- no arbitrary write operations;
- query timeout;
- result-size limits;
- resource limits.

## 15.2 LLM security

The implementation should address:

- prompt injection;
- malicious content in retrieved documents;
- tool-call validation;
- excessive tool execution;
- data exfiltration;
- secret leakage.

## 15.3 Data isolation

The system should establish clear boundaries between:

- user input;
- retrieved content;
- system instructions;
- tool results.

Retrieved documents must be treated as **data**, not instructions.

---

# 16. Investigation Trace and Explainability

The UI shall provide an investigation trace.

Example:

```text
Investigation started

1. get_campaign_metrics()
   Result: ROI declined from 2.9 to 1.8

2. compare_segments()
   Result: decline concentrated in high-value customers

3. get_campaign_exposure()
   Result: exposure increased from 1.4 to 3.7

4. search_campaign_knowledge()
   Result: 3 historical cases found

5. analyze_exposure_vs_response()
   Result: strong negative association

6. Final synthesis
```

The trace shall expose:

- tools invoked;
- tool parameters at an appropriate abstraction level;
- returned evidence;
- retrieved documents;
- execution timing;
- errors/retries;
- final evidence mapping.

## Optional Chain-of-Thought display

The system may provide an optional configuration for an appropriate **reasoning summary / internal analysis visualization**, subject to the capabilities and policies of the selected LLM provider.

The implementation shall not depend on exposing private chain-of-thought.

The default UI should show an **auditable investigation trace**, not private model reasoning.

---

# 17. Evaluation Methodology

The research shall compare three approaches.

## 17.1 Baseline A — Deterministic Analytics

Implementation using:

- SQL;
- predefined business rules;
- deterministic calculations;
- standard analytical queries.

## 17.2 Baseline B — Conventional ML / Statistical Analytics

Where appropriate:

- classification;
- regression;
- propensity models;
- clustering;
- anomaly detection;
- uplift modeling;
- statistical tests.

The exact ML method shall depend on the scenario.

## 17.3 Approach C — AI Agent

The Agent may use:

- SQL;
- ML/statistical tools;
- RAG;
- multiple tool calls;
- iterative investigation.

The Agent should not be evaluated as a replacement for the underlying analytical tools.

It is evaluated on its ability to **orchestrate and synthesize them**.

---

# 18. Evaluation Dataset

The evaluation dataset shall contain approximately ten representative business questions.

It should include:

1. ordinary analytical questions;
2. open-ended investigation questions;
3. questions requiring historical knowledge;
4. questions requiring structured + unstructured evidence;
5. questions with conflicting evidence;
6. questions where the correct conclusion is "insufficient evidence";
7. known scenarios with injected effects.

---

# 19. Ground Truth

Selected scenarios shall have known ground truth.

Example:

```text
Injected condition:
Campaign exposure increased significantly.

Expected investigative hypothesis:
Campaign fatigue.

Supporting evidence:
Response decreases with increasing exposure.
```

Ground-truth scenarios allow objective measurement of:

- hypothesis discovery;
- evidence retrieval;
- false positives;
- missed explanations.

Ground truth should not be exposed to the Agent during evaluation.

---

# 20. Human Evaluation

A human evaluator shall score outputs using a predefined rubric.

Recommended dimensions:

| Dimension | Description |
|---|---|
| Factual correctness | Are factual claims supported? |
| Relevance | Does the answer address the question? |
| Evidence quality | Is evidence appropriate and sufficient? |
| Reasoning quality | Is the investigative path sensible? |
| Hypothesis quality | Are hypotheses plausible and useful? |
| Actionability | Can a marketer act on the result? |
| Completeness | Were important evidence sources considered? |
| Transparency | Are uncertainty and limitations explicit? |

Scores should be normalized, for example, on a 1–5 scale.

---

# 21. Quantitative Evaluation Metrics

The project shall measure:

## 21.1 Investigation quality

- factual accuracy;
- evidence coverage;
- hypothesis precision;
- useful insight rate;
- recommendation usefulness;
- false-positive rate;
- unsupported-claim rate.

## 21.2 Efficiency

- time to answer;
- number of manual analytical steps;
- number of tool calls;
- number of SQL queries;
- number of retrieved documents;
- investigation duration.

## 21.3 AI efficiency

- LLM calls;
- input tokens;
- output tokens;
- estimated LLM cost;
- cost per investigation;
- average latency;
- failed tool calls;
- retries.

## 21.4 Business/analyst productivity

Where feasible:

```text
Analyst investigation time without Agent
vs.
Analyst verification time with Agent
```

The objective is not to eliminate the analyst but to reduce investigative effort.

---

# 22. Research Result

The final research report shall answer:

1. Where does AI provide measurable value?
2. Where does SQL remain superior?
3. Where does ML remain superior?
4. Which questions benefit most from Agentic investigation?
5. Does the Agent discover useful hypotheses that deterministic systems miss?
6. Does the Agent reduce investigation time?
7. What is the factual-error rate?
8. What is the cost per investigation?
9. How much human verification remains necessary?
10. Is the AI approach justified for this class of business problem?

The project must allow the final conclusion to be:

> **AI provides insufficient additional value.**

A negative result is considered a valid research outcome.

---

# 23. Functional Requirements

## FR-001 — Natural-language question

The user shall be able to submit a business question in natural language.

## FR-002 — Investigation planning

The Agent shall determine an initial investigation strategy.

## FR-003 — Tool selection

The Agent shall dynamically select analytical and retrieval tools.

## FR-004 — Structured analysis

The system shall support deterministic SQL-based analysis.

## FR-005 — Historical comparison

The system shall support comparisons between current and historical periods.

## FR-006 — Segment analysis

The system shall support customer-segment investigation.

## FR-007 — Campaign comparison

The system shall support campaign-to-campaign comparisons.

## FR-008 — Semantic knowledge search

The system shall support semantic retrieval of marketing documents.

## FR-009 — Multi-step investigation

An investigation shall support multiple tool calls and iterative refinement.

## FR-010 — Hypothesis generation

The Agent shall generate explicit hypotheses.

## FR-011 — Hypothesis validation

The Agent shall attempt to validate important hypotheses using available analytical tools.

## FR-012 — Recommendations

The Agent shall produce recommendations or recommended next investigations.

## FR-013 — Evidence

The final response shall provide evidence supporting major conclusions.

## FR-014 — Uncertainty

The Agent shall report uncertainty and insufficient evidence.

## FR-015 — Trace

The system shall record an investigation trace.

## FR-016 — Evaluation

The system shall record metrics required for research evaluation.

## FR-017 — Dataset abstraction

The ingestion and logical data model shall support replacing the initial dataset.

## FR-018 — LLM abstraction

The system should allow changing the LLM provider without rewriting the business logic.

---

# 24. Non-Functional Requirements

## NFR-001 — Reproducibility

The same dataset version, configuration, and scenario should permit repeatable evaluation.

## NFR-002 — Observability

The system shall log:

- Agent executions;
- tool calls;
- errors;
- latency;
- token usage where available;
- evaluation metrics.

## NFR-003 — Reliability

A failed tool call shall not necessarily terminate the entire investigation.

The Agent should recover or report the failure appropriately.

## NFR-004 — Performance

The system should provide reasonable interactive response times for demonstration workloads.

## NFR-005 — Scalability

The architecture should permit:

- larger datasets;
- additional tools;
- additional datasets;
- additional LLM providers;
- more users.

## NFR-006 — Security

Secrets must not be embedded in source code.

Database access shall use least privilege.

## NFR-007 — Maintainability

Agent logic, tools, data access, prompts, and evaluation logic shall be modular.

## NFR-008 — Auditability

Investigations shall be traceable after execution.

---

# 25. MVP Definition

The MVP is complete when a user can:

1. open the web application;
2. enter one of the defined business questions;
3. start an investigation;
4. observe the investigation trace;
5. see structured analytical evidence;
6. see relevant historical campaign knowledge;
7. see generated hypotheses;
8. see hypothesis validation;
9. receive evidence-backed recommendations;
10. inspect supporting evidence;
11. repeat the investigation;
12. record evaluation metrics.

---

# 26. MVP Technical Components

```text
Web UI
  |
  v
Python Backend
  |
  +-- Agent Orchestrator
  |
  +-- Tool Registry
  |
  +-- Evaluation Framework
  |
  +-- Audit / Observability
  |
  v
PostgreSQL
  |
  +-- Structured loyalty data
  +-- Synthetic marketing knowledge
  +-- pgvector embeddings
```

External:

```text
Python Agent
     |
     v
LLM Provider
```

---

# 27. Synthetic Knowledge Generation Requirements

Synthetic documents shall be generated through a controlled pipeline.

Example:

```text
Real campaign data
       |
       v
Campaign facts extraction
       |
       v
Document generation
       |
       v
Fact validation
       |
       v
Synthetic knowledge base
```

Each generated document should retain references to the structured entities from which it was derived.

Example metadata:

```text
document_id
campaign_id
source_type = synthetic
generation_version
generation_model
source_data_version
created_at
```

This ensures that synthetic knowledge can be audited.

---

# 28. Historical Replay

Because the primary dataset is static, the system shall support a simulated timeline.

Example:

```text
Week 1
  |
Week 2
  |
...
  |
Week 70  <-- Agent sees only data available at this point
  |
Week 71
  |
...
Week 102
```

The Agent must not access future data during an evaluation scenario.

This enables:

- backtesting;
- temporal evaluation;
- leakage prevention;
- realistic campaign investigation.

---

# 29. Data Leakage Prevention

The evaluation framework shall prevent:

- future transactions from being exposed to the Agent;
- future campaign results from being retrieved;
- future post-mortems from being used;
- ground-truth information from being present in prompts/documents.

This is essential for credible evaluation.

---

# 30. Agent Guardrails

The Agent shall:

- use approved tools only;
- avoid unrestricted SQL execution;
- avoid database writes;
- respect temporal boundaries;
- cite evidence;
- distinguish hypotheses from facts;
- avoid unsupported causal claims;
- detect contradictory evidence;
- stop when sufficient evidence has been obtained;
- avoid unnecessary tool calls.

An investigation budget may be imposed:

```text
max tool calls
max execution time
max retrieved documents
max LLM calls
max token budget
```

---

# 31. Cost Evaluation

Each investigation should record:

```text
LLM calls
Input tokens
Output tokens
Estimated LLM cost
Database queries
Vector searches
Execution time
```

The research should compare:

```text
AI Agent cost
vs.
estimated analyst effort
```

The project should not assume that a technically successful Agent is economically justified.

---

# 32. Failure Modes to Evaluate

The test suite should intentionally include:

- ambiguous questions;
- insufficient data;
- conflicting documents;
- misleading marketer hypotheses;
- statistically weak relationships;
- missing historical campaigns;
- irrelevant retrieved documents;
- tool failures;
- LLM hallucinations;
- excessive tool loops;
- contradictory analytical results.

The Agent should fail **safely and transparently**.

---

# 33. Key Risks

| Risk | Mitigation |
|---|---|
| LLM hallucination | Evidence grounding and validation |
| Incorrect SQL | Controlled analytical tools |
| Prompt injection | Treat retrieved text as untrusted data |
| False causal claims | Explicit causal guardrails |
| Synthetic knowledge bias | Clearly label and validate generated documents |
| Evaluation bias | Fixed scenarios and human rubric |
| Dataset limitations | Dataset abstraction |
| Excessive LLM cost | Tool/call/token budgets |
| Overengineering | Small MVP toolset |
| AI provides no advantage | Explicitly accept negative research result |

---

# 34. Success Criteria

The project should be considered successful as a **research project** if it produces a credible, reproducible answer to the primary hypothesis.

Technical implementation alone is not sufficient.

A successful outcome must demonstrate:

- measurable comparison with conventional approaches;
- reproducible scenarios;
- evidence-backed Agent behavior;
- quantitative evaluation;
- human evaluation;
- cost measurement;
- documented limitations;
- clear recommendation regarding when AI is and is not justified.

---

# 35. Expected Final Deliverables

## 35.1 Software

- Web UI;
- Agent backend;
- PostgreSQL schema;
- pgvector knowledge store;
- ingestion pipeline;
- synthetic knowledge generator;
- analytical tools;
- evaluation framework;
- deployment configuration.

## 35.2 Documentation

- Business Requirements;
- architecture overview;
- data model;
- tool specifications;
- Agent behavior specification;
- evaluation methodology;
- deployment instructions;
- security considerations.

## 35.3 Research results

A final report containing:

- experimental design;
- baseline results;
- Agent results;
- quality metrics;
- performance metrics;
- cost metrics;
- human evaluation;
- failure analysis;
- conclusions;
- recommendations.

---

# 36. Proposed Project Phases

## Phase 1 — Dataset and Data Model

- obtain and normalize dunnhumby data;
- implement canonical schema;
- implement temporal replay;
- validate data.

## Phase 2 — Conventional Baselines

- implement deterministic SQL investigations;
- implement selected statistical/ML baselines;
- establish evaluation scenarios.

## Phase 3 — Marketing Knowledge

- define campaign-document schema;
- generate synthetic knowledge;
- validate factual consistency;
- create conflicting/ambiguous cases.

## Phase 4 — Agent MVP

- implement Agent;
- implement tool registry;
- implement SQL tools;
- implement RAG;
- implement multi-step investigation.

## Phase 5 — Evaluation

- run standardized scenarios;
- collect quantitative metrics;
- perform human evaluation;
- compare approaches.

## Phase 6 — Production-oriented Hardening

- security;
- observability;
- audit trail;
- error handling;
- configurable providers;
- deployment.

## Phase 7 — Demonstration

- polished UI;
- investigation trace;
- representative scenarios;
- evaluation dashboard;
- final research report.

---

# 37. Reference Investigation Example

A representative investigation should look approximately like this:

```text
USER

Why did win-back campaign performance decline during
the last three months?


AGENT

1. Establish campaign performance baseline.

   -> get_campaign_metrics()

   ROI:
   Historical: 2.9
   Current:    1.8


2. Identify affected segments.

   -> compare_segments()

   High-value customers: -22%
   Medium-value customers: -8%
   Low-value customers: +2%


3. Investigate campaign exposure.

   -> get_campaign_exposure()

   Average exposure:
   Historical: 1.4
   Current:    3.7


4. Form hypothesis:

   Campaign fatigue may be contributing to the decline.


5. Search historical knowledge.

   -> search_campaign_knowledge()

   Found three historically similar cases.


6. Validate hypothesis.

   -> analyze_exposure_vs_response()

   Response decreases materially with repeated exposure.


7. Synthesize evidence.

   Current structured data and historical campaign
   post-mortems show a consistent pattern.


8. Recommendation.

   Test reduced campaign frequency for high-value
   customers using a controlled experiment.


9. Caveat.

   The evidence supports an association but does not
   establish causality.
```

---

# 38. Architectural Principle

The project shall follow one central architectural principle:

> **The LLM should not replace deterministic analytics. It should orchestrate deterministic analytics, ML/statistics, and business knowledge retrieval to investigate questions that are difficult to formalize in advance.**

This principle is central to the research hypothesis.

---

# 39. Expected Differentiation from a Conventional BI System

A conventional BI system answers predefined questions:

```text
What happened?
How much?
When?
Where?
Which segment?
```

An ML system answers predictive questions:

```text
What is likely to happen?
Who is likely to churn?
Who is likely to respond?
What is the expected uplift?
```

The AI Campaign Investigator addresses a different class:

```text
Why might this be happening?
What previous situations resemble it?
Which hypotheses are worth investigating?
What evidence supports or contradicts each hypothesis?
What should we investigate next?
```

The Agent is valuable precisely because the investigation path is **not fully specified beforehand**.

---

# 40. Final Research Principle

The project must not be designed to prove that AI is useful.

It must be designed to determine **where AI is useful, where it is not, and whether the additional complexity and cost are justified**.

The expected conclusion should therefore be expressed in terms of decision boundaries such as:

> Use SQL for deterministic measurement.

> Use ML for predictive optimization.

> Use statistical methods for hypothesis validation and causal analysis.

> Use an AI Agent when the problem requires dynamic investigation across heterogeneous structured and unstructured information.

The ultimate deliverable is therefore not merely an AI application.

It is an **evidence-based assessment of whether AI Agents are an economically and technically justified tool for loyalty-program business investigation.**
