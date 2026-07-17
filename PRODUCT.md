# PolicyForge Product Definition

## Product Summary

PolicyForge is an AI governance control center for enterprise AI agents. It helps an organization understand what an agent can do, turn organizational policies into agent-specific controls, preserve the evidence behind consequential decisions, and identify decisions that require reassessment when policies or model risks change.

> Govern agents before they act. Explain every decision. Repair the consequences when rules change.

PolicyForge is not only a policy-document generator and not only an audit dashboard. It connects the complete governance lifecycle:

```text
Organizational policy
        ↓
Agent-specific controls
        ↓
Governed agent action
        ↓
Traceable decision
        ↓
Policy replay
        ↓
Recall and remediation
```

## Competition Problem

The project responds to Case Study 3: AI Governance and Responsible AI in Enterprise.

Organizations are adopting generative AI faster than their governance processes can respond. Employees and departments gain productivity from AI, but the organization may not know:

- Which AI tools and agents are being used.
- What data those tools can access.
- Which tools are approved for sensitive information.
- Whether an AI-assisted decision received appropriate human oversight.
- How to explain a decision to an affected person.
- Which historical decisions were affected when a model or policy was flawed.

Outright bans can push AI usage further out of sight. A useful governance product must make the compliant path understandable and convenient while preserving accountability.

## Target Users

### Primary users

- AI governance and compliance teams.
- Information security teams.
- Legal and privacy teams.
- IT administrators.
- Department owners such as Human Resources.

### Secondary users

- Employees using governed AI tools.
- Human reviewers responsible for consequential decisions.
- Auditors investigating AI usage.
- People affected by AI-assisted decisions.

## Product Promise

PolicyForge answers four questions:

1. **What may this agent do?**
2. **Why was this decision made and who was responsible?**
3. **What would change under a different policy?**
4. **How do we correct affected decisions safely?**

## Product Pillars

### 1. Forge — Agent Governance

PolicyForge begins with a real AI agent, not an abstract policy document.

For each agent, the organization can inspect:

- Business owner.
- Model and provider.
- Connected tools.
- Agent capabilities.
- Data categories accessed.
- Actions the agent may take.
- People potentially affected.
- Current approval and risk status.

PolicyForge maps these characteristics to organizational policy and proposes controls such as:

- `ALLOW`
- `TRANSFORM`
- `HUMAN REVIEW`
- `BLOCK`

Example:

```text
Candidate identity + external model
→ Remove identifying information before inference

Negative candidate recommendation
→ Require authorized HR review

Protected characteristics + candidate ranking
→ Block and record
```

AI may help interpret policy language and draft controls, but an authorized person resolves ambiguity and approves the deployed policy.

### 2. Trace — Decision Capsules

Every consequential AI-assisted action creates a Decision Capsule: a structured reconstruction of what happened.

A capsule records:

- Agent and model versions.
- Policy version active at the time.
- Categories of input data.
- Data transformations.
- Important recorded factors.
- Model outputs.
- Agent recommendations.
- Triggered policy controls.
- Human reviewer and action.
- Final consequence.
- Explanation and reconsideration history.

The trace separates responsibility clearly:

```text
Recorded facts
      ↓
Model classification
      ↓
Agent recommendation
      ↓
Policy determination
      ↓
Human decision
      ↓
External consequence
```

PolicyForge does not claim to expose private model chain-of-thought. It presents recorded evidence, rule evaluations, versions, actions, and accountable human decisions.

### 3. Policy Time Machine — Historical Replay

Before a proposed policy is deployed, PolicyForge compares it with the current version and re-evaluates representative historical decisions.

The Time Machine answers:

- Which decisions would remain unchanged?
- Which decisions would receive a different policy outcome?
- Which people or departments are affected?
- Which communications, rankings, reports, or downstream actions depend on those decisions?
- Which decisions require renewed human review?

Example:

```text
2,841 historical decisions replayed
2,768 unchanged
73 affected
73 require human reassessment
18 candidate notices connected
3 management reports affected
```

The Time Machine provides counterfactual analysis. It does not automatically reverse real-world decisions.

### 4. Recall — Controlled Remediation

Recall begins after PolicyForge has identified affected decisions.

It turns replay findings or a model-risk incident into an accountable remediation workflow:

```text
Confirm scope
      ↓
Assign responsible owner
      ↓
Reopen affected decisions
      ↓
Perform independent human review
      ↓
Record corrections
      ↓
Notify affected parties
      ↓
Close recall with evidence
```

Original decisions are preserved. Corrections are added as new events rather than silently rewriting history.

## Pitch Scenario

The preliminary prototype follows one Candidate Screening Agent through the complete lifecycle.

### Starting situation

Northstar Group's HR department wants to approve a new Candidate Screening Agent.

The agent can:

- Read candidate résumés.
- Extract qualifications.
- Rank candidates.
- Draft candidate communications.
- Request inference from an external model.

This creates governance questions:

- May candidate identity be sent to the external model?
- May protected characteristics affect ranking?
- Can the agent issue a final rejection?
- Who must review a negative recommendation?
- How will the candidate learn that AI was involved?
- What happens if a policy is later found to be incomplete?

### Governance outcome

PolicyForge proposes and tests these controls:

| Agent situation | PolicyForge outcome |
| --- | --- |
| Candidate identity sent to an external model | `TRANSFORM` — remove identity first |
| Candidate ranking based on job-related qualifications | `ALLOW AND RECORD` |
| Negative candidate recommendation | `HUMAN REVIEW` |
| Protected-attribute profiling | `BLOCK` |
| Candidate outcome notification | Disclose AI involvement and review pathway |

After the administrator resolves one ambiguity and approves the controls, the agent becomes active under Recruitment Policy v1.4.

### Consequential decision

The agent evaluates a candidate and treats an 18-month caregiving period as an unexplained employment gap. It recommends rejection. PolicyForge requires HR review, and the reviewer approves the recommendation.

The Decision Capsule preserves:

- The original application event.
- Removal of candidate identity before external inference.
- The model's employment-gap classification.
- The agent recommendation.
- The policy requirement for human review.
- The HR reviewer's approval.
- The candidate notice.

The candidate sees that AI assisted with the evaluation, receives a plain explanation of the recorded factors, and can request human reconsideration.

### Policy change

The organization proposes Recruitment Policy v1.5:

> Documented caregiving, medical, and professional-development leave must not be treated as a negative employment gap.

PolicyForge replays historical decisions and finds 73 affected cases. The selected candidate changes from `Rejection recommendation permitted` to `Independent reassessment required`.

### Recall

The administrator creates Recall RC-017 from the replay result. The affected decisions are assigned for renewed human review, connected notices and reports are flagged, and the original evidence remains intact.

## Primary Product Surfaces

### Governance Overview

Shows agent inventory, approval status, governed activity, human-review interventions, policy alerts, and recalls.

### Agent Governance Workspace

Shows agent capabilities, accessed data, generated controls, policy sources, ambiguity resolution, test scenarios, and deployment.

### Governed Action

Shows how PolicyForge allows, transforms, escalates, or blocks a proposed agent action.

### Decision Capsule

Shows the complete evidence and responsibility chain behind an AI-assisted outcome.

### Candidate Explanation

Shows AI disclosure, important recorded factors, human responsibility, and a reconsideration pathway.

### Policy Time Machine

Shows policy-version comparison, historical replay, affected decisions, and downstream blast radius.

### Recall Center

Shows remediation scope, responsible owner, review progress, corrections, and closure evidence.

## What Makes PolicyForge Distinctive

Policy-as-code and AI monitoring already exist. PolicyForge should not claim that converting documents into rules is entirely new.

Its stronger differentiation is the connected lifecycle:

- Governance begins from the capabilities of a real agent.
- Controls remain linked to their policy evidence.
- Consequential actions produce structured Decision Capsules.
- Policy versions can be replayed against historical decisions.
- Replay findings can become controlled recall campaigns.
- People affected by AI receive explanation and redress.

The product does not stop after detecting a risk. It shows what was affected and provides a path to correction.

## Product Guardrails

- AI drafts controls; authorized humans approve them.
- Consequential decisions must show human responsibility.
- Runtime outcomes must be explicit: allow, transform, review, or block.
- Historical policy and decision versions must not be overwritten.
- Evidence must be distinguishable from model-generated explanation.
- Private chain-of-thought must not be presented as an audit artifact.
- Sensitive raw data should not be stored unnecessarily.
- Simulations and historical replays must be labelled clearly.
- Replay must not automatically reverse real decisions.
- Recall must route consequential corrections through accountable human review.
- Candidate explanations must avoid guarantees and unsupported causal claims.
- The compliant path should be easier than bypassing governance.

## Preliminary Prototype Boundary

The preliminary prototype is a polished interactive visualization of the product idea.

It should demonstrate:

- A coherent navigation flow.
- Believable state changes.
- Consistent agent and policy versions.
- Understandable governance controls.
- A readable decision trace.
- A convincing policy comparison and replay.
- A controlled recall action.

It does not need:

- Production agent integrations.
- Enterprise authentication.
- Real HR data.
- Large-scale event processing.
- A general-purpose policy compiler.
- Real notification delivery.
- Production-grade security or infrastructure.

Prepared data and client-side state are acceptable for the preliminary round as long as the demonstration is internally consistent and the simulated nature of integrations is represented honestly.

## One-Sentence Pitch

> PolicyForge turns organizational policy into controls for real AI agents, preserves the evidence behind every consequential decision, and finds the decisions that need correction when the rules change.
