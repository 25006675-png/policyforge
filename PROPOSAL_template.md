# Competition Proposal

**Team Name:** [Insert team name]

**Project Name:** PolicyForge

**Case Study Category:** Case Study 3 — AI Governance & Responsible AI in Enterprise

**Team Members:**

- Member 1: [Insert name]
- Member 2: [Insert name]
- Member 3: [Insert name]
- Member 4: [Insert name, if applicable]

## 1. Introduction

### 1.1 Project overview

PolicyForge is an AI governance control center for enterprise AI agents. It helps an organization understand what an agent can do, translate organizational policies into understandable agent-specific controls, preserve the evidence behind consequential AI-assisted decisions, and identify decisions that may require reassessment when a policy or model risk changes.

The product connects a governance lifecycle that is often divided among separate documents, monitoring tools, logs, and manual review processes:

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

PolicyForge can be summarized in one sentence:

> PolicyForge turns organizational policy into controls for real AI agents, preserves the evidence behind every consequential decision, and finds the decisions that need correction when the rules change.

### 1.2 Background

Organizations are adopting generative AI assistants and autonomous agents faster than governance processes can respond. Employees and departments benefit from AI-assisted coding, analysis, drafting, customer communication, and decision support, but the organization may not know which tools are being used, what information they access, or whether their output receives appropriate oversight.

Written policies alone cannot inspect an agent's capabilities, intervene in an unsafe action, reconstruct the evidence behind an AI-assisted outcome, or identify historical decisions affected by a later policy correction. This creates a gap between governance intention and operational behavior.

PolicyForge addresses that gap by making governance visible at the level of agents, decisions, policy versions, and corrective action.

### 1.3 Main features

#### Agent Governance Workspace

- Registers a real AI agent and its owner.
- Displays agent capabilities, connected tools, accessed data, model, and risk level.
- Maps relevant organizational policy clauses to the agent.
- Generates proposed outcomes such as `ALLOW`, `TRANSFORM`, `HUMAN REVIEW`, or `BLOCK`.
- Lets an authorized administrator resolve ambiguities, test scenarios, and approve deployment.

#### Decision Capsules

- Reconstruct the evidence chain behind a consequential AI-assisted decision.
- Separate recorded input, model output, agent recommendation, policy determination, human decision, and external consequence.
- Preserve the agent, model, and policy versions active at the time.
- Support plain-language explanation and a reconsideration pathway for the person affected.

#### Policy Time Machine

- Compares an active policy with a proposed version.
- Replays representative historical decisions under the proposed policy.
- Identifies decisions whose governance outcome would change.
- Visualizes the downstream impact on notices, rankings, reports, and other actions.

#### Controlled Recall

- Converts replay findings or a model-risk incident into a remediation workflow.
- Assigns an accountable owner and human reviewers.
- Preserves original decisions while recording reassessment and correction.
- Tracks affected cases and related downstream consequences.

### 1.4 Prototype approach

The preliminary submission is a polished frontend-first interactive prototype. It focuses on communicating the complete product idea through one consistent scenario rather than implementing production infrastructure.

The interface will use representative agent, policy, decision, replay, and recall data. Essential state changes—such as approving an agent, running a replay, and creating a recall—will be interactive and consistent across screens. Enterprise integrations, large-scale processing, and notification delivery may be simulated transparently.

### 1.5 Technology summary

- **Frontend:** React or Next.js with TypeScript.
- **Styling:** Tailwind CSS or an equivalent component-based design system.
- **Visualization:** CSS, SVG, or a lightweight graph library for decision traces and blast-radius diagrams.
- **Prototype state:** Client-side state with browser storage for persistence and reliable demo reset.
- **Data:** Prepared TypeScript or JSON fixtures.
- **AI assistance:** Optional structured extraction of a short policy clause, with prepared fallback data.

## 2. Problem Statement

### 2.1 The governance gap

Enterprise AI adoption creates four connected problems.

#### Slow or unclear approval

Departments may adopt useful AI tools before IT, legal, security, and compliance teams can evaluate them. If the approval path is too slow or confusing, employees may use unapproved tools outside organizational visibility.

#### Sensitive-data exposure

Prompts and uploaded documents can move personal, confidential, or regulated data outside organizational control. Traditional cybersecurity tools may see an authorized employee and a normal web request while missing the governance context of the information and AI tool involved.

#### Weak accountability for consequential decisions

When AI contributes to recruitment, financial, employment, insurance, or account decisions, a conventional technical log may not explain what the model contributed, what policy applied, who reviewed the result, or how an affected person can request reconsideration.

#### No reliable way to repair historical impact

When a policy changes or a model flaw is discovered, organizations may correct future behavior without knowing which previous decisions, communications, and reports depended on the flawed rule. Risk detection without impact tracing leaves affected people and downstream systems unresolved.

### 2.2 Who is affected

- Employees need a compliant path that still allows them to work efficiently.
- IT and security teams need visibility into agent capabilities and data access.
- Compliance and legal teams need clear policy evidence and version history.
- Department leaders need human-review and remediation workflows.
- Auditors need reconstructable records.
- People affected by AI-assisted decisions need disclosure, explanation, and redress.

### 2.3 Case-study alignment

| Case-study challenge | PolicyForge response |
| --- | --- |
| Responsible AI usage and employee compliance | Agent approval workspace, understandable controls, and a compliant route instead of a blanket ban |
| Data privacy and security | Data classification, model restrictions, redaction or transformation, and recorded interventions |
| Transparency and ethical boundaries | Decision Capsules, explicit human responsibility, candidate explanation, and reconsideration |
| Monitor model risks | Agent and model version visibility, policy alerts, and affected-decision tracing |
| Approval workflow for AI usage | Capability review, policy testing, ambiguity resolution, and administrator approval |
| Track AI usage | Governance overview and decision-level records |
| Suggest policies and automated checks | Policy-to-control generation with human confirmation |

## 3. Aim and Objectives

### 3.1 Aim

To design an understandable governance system that makes enterprise AI agents controllable before use, consequential decisions traceable after use, and historical impact discoverable when policies or model risks change.

### 3.2 Objectives

The preliminary prototype will:

1. Present an AI agent's capabilities, accessed data, model, owner, and approval status in one workspace.
2. Demonstrate how policy clauses become agent-specific controls with explicit outcomes.
3. Require an authorized person to resolve ambiguity and approve deployment.
4. Demonstrate sensitive-data transformation and human review during an agent action.
5. Create a visual Decision Capsule for one consequential candidate decision.
6. Show AI disclosure, important recorded factors, human responsibility, and a reconsideration pathway.
7. Compare two policy versions and replay representative historical decisions.
8. Identify affected decisions and visualize downstream consequences.
9. Convert replay findings into a controlled recall for human reassessment.
10. Maintain consistent agents, versions, decisions, counts, and states throughout the pitch.

## 4. Methodology

### 4.1 Implementation workflow

#### Step 1 — Product and visual foundation

- Freeze the pitch scenario, terminology, screen sequence, and fixed demonstration data.
- Define low-fidelity layouts and the common design system.
- Build the application shell, navigation, fixture data, and demo reset.

#### Step 2 — Agent governance

- Build the Governance Overview and Agent Governance Workspace.
- Add agent analysis, proposed controls, policy evidence, ambiguity resolution, and test scenarios.
- Add the approval and deployment interaction.

#### Step 3 — Governed action and trace

- Build the candidate-processing sequence and sensitive-data transformation.
- Add the required HR review.
- Build the Decision Capsule, evidence panels, candidate explanation, and reconsideration confirmation.

#### Step 4 — Time Machine and recall

- Build policy-version comparison and historical replay states.
- Present affected decisions, before-and-after outcomes, and blast radius.
- Create the recall confirmation and success flow.

#### Step 5 — Integration and refinement

- Verify data and terminology across all screens.
- Refine typography, spacing, color, motion, and interaction feedback.
- Add disabled, loading, warning, and success states.
- Rehearse and record the pitch from a reliable reset state.

### 4.2 Prototype data and behavior

The prototype follows one Candidate Screening Agent and one candidate case.

Fixed demonstration data includes:

- Organization: Northstar Group.
- Agent: Candidate Screening Agent v2.1.
- Model: TalentModel v4.2.
- Active policy: Recruitment Policy v1.4.
- Proposed policy: Recruitment Policy v1.5.
- Main decision: PF-2841.
- Historical decisions: 2,841.
- Decisions affected by the policy change: 73.
- Recall: RC-017.

The prototype will preserve state during the demonstration so that deploying a policy, completing a candidate action, running a replay, and creating a recall all produce visible and consistent results.

### 4.3 Technical design

The preliminary version does not require a production backend. Prepared fixtures and client-side state are sufficient because the judging focus is the idea and interface.

Suggested structure:

```text
Frontend application
 ├── Organization and agent fixtures
 ├── Policy versions and controls
 ├── Candidate decision events
 ├── Replay results
 ├── Recall state
 └── Mock service operations
      ├── Analyse agent
      ├── Test controls
      ├── Deploy policy
      ├── Process candidate
      ├── Run replay
      └── Create recall
```

Mock operations should use structured inputs and outputs so that future development can replace them with real APIs without redesigning the interface.

### 4.4 Testing and refinement

The team will validate:

- Whether a viewer understands each screen without extensive explanation.
- Whether every pitch action has a visible cause and result.
- Whether policy and model versions remain consistent.
- Whether the Decision Capsule separates AI and human responsibility.
- Whether replay clearly explains why an outcome changed.
- Whether recall scope matches the replay findings.
- Whether the complete demonstration can be reset and repeated reliably.
- Whether color, labels, and interaction states remain accessible and understandable.

## 5. Potential Impact

### 5.1 Organizational impact

PolicyForge could help organizations:

- Reduce the delay between an AI-tool request and a governed approval decision.
- Make safe AI use more convenient than unapproved workarounds.
- Reduce accidental disclosure of sensitive information.
- Improve accountability for AI-assisted decisions.
- Respond to policy and model incidents with evidence rather than guesswork.
- Identify affected people and downstream actions before deploying a policy correction.
- Provide auditors and regulators with a clearer record of governance decisions.

### 5.2 Market research and existing solutions

Policy-as-code is an established and growing category. PolicyForge does not claim that converting natural-language rules into executable controls is entirely new.

Amazon Bedrock AgentCore Policy allows organizations to define Cedar policies around agent tool calls. AWS documents natural-language policy generation, deterministic gateway enforcement, and policy-decision logging. This is strong infrastructure-level control for agents operating through the AgentCore gateway.

Kyndryl's policy-as-code capability translates organizational and regulatory requirements into machine-readable policies for agentic workflows. Its published material emphasizes deterministic execution, explainability, reviewability, auditing, and human supervision.

Other governance products commonly focus on model inventory, risk monitoring, compliance dashboards, or individual policy enforcement. These are valuable functions, but they may leave decision evidence, counterfactual policy analysis, and corrective workflow in separate systems.

### 5.3 PolicyForge differentiation

PolicyForge's proposed distinction is the connection between:

1. The capabilities and data access of a real agent.
2. Human-approved policy controls.
3. A structured Decision Capsule for each consequential outcome.
4. Historical replay under a proposed policy version.
5. A recall workflow for affected decisions and downstream consequences.
6. A plain explanation and reconsideration pathway for the affected person.

PolicyForge therefore goes beyond asking whether an agent action is permitted. It also asks:

- What actually happened?
- Who was responsible?
- Who may already have been affected?
- What needs to be reviewed or corrected now?

### 5.4 Relationship to governance frameworks

The NIST AI Risk Management Framework organizes AI risk work around Govern, Map, Measure, and Manage. PolicyForge's agent approval and policy controls support governance and mapping; Decision Capsules support measurement and evidence; Time Machine and Recall support management and response.

The product also reflects broader principles found in the EU AI Act, including transparency, documentation, risk management, and meaningful human oversight for higher-risk uses. PolicyForge is not presented as an automatic compliance guarantee; it is a practical system for operationalizing and evidencing responsible practices.

### 5.5 Target market

Initial target organizations include:

- Medium and large enterprises adopting multiple AI agents.
- Regulated organizations in finance, healthcare, insurance, government, and employment services.
- Organizations using AI in consequential workflows.
- Governance teams that currently coordinate approvals and incident response manually.

The initial buyer or product owner would likely sit within AI governance, compliance, information security, or enterprise IT. Department leaders and affected-person support teams would participate in review and remediation workflows.

## 6. Prototype Interface Appendix

The prototype will contain these connected views:

1. **Governance Overview** — agent inventory, approval status, governance activity, and policy alerts.
2. **Agent Governance Workspace** — capabilities, data access, proposed controls, policy evidence, tests, and approval.
3. **Governed Candidate Action** — data transformation, agent recommendation, and required human review.
4. **Decision Capsule** — the complete evidence and responsibility chain.
5. **Candidate Explanation** — AI disclosure, important factors, human responsibility, and reconsideration.
6. **Policy Time Machine** — version comparison, replay results, changed decisions, and blast radius.
7. **Recall** — affected cases, responsible owner, human reassessment, and correction status.

Detailed screen behavior and visual requirements are maintained in [TECHNICAL_EXECUTION.md](TECHNICAL_EXECUTION.md). The pitch sequence is maintained in [PITCH.md](PITCH.md).

## 7. References

1. Competition Case Study 3, “AI Governance & Responsible AI in Enterprise,” provided competition brief.
2. National Institute of Standards and Technology, [Artificial Intelligence Risk Management Framework (AI RMF 1.0)](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf), 2023.
3. National Institute of Standards and Technology, [AI RMF Core: Govern, Map, Measure, and Manage](https://airc.nist.gov/airmf-resources/airmf/5-sec-core/).
4. European Union, [Regulation (EU) 2024/1689 — Artificial Intelligence Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689), 2024.
5. Amazon Web Services, [Policy in Amazon Bedrock AgentCore](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/policy.html).
6. Amazon Web Services, [Getting Started with Policy in Amazon Bedrock AgentCore](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/policy-getting-started.html).
7. Kyndryl, [Kyndryl Introduces Policy-Governed Agentic AI](https://www.kyndryl.com/ca/en/about-us/news/2026/02/policy-as-code-agentic-ai-governance), 2026.
