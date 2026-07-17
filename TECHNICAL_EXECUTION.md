# PolicyForge Technical Execution

## Purpose

This document defines how to build the preliminary PolicyForge prototype for the competition pitch. The prototype is a frontend-first interactive demonstration. It must communicate the product accurately and maintain believable cause-and-effect relationships, but it does not need production infrastructure, enterprise integrations, or a full policy engine.

The prototype should prove one complete story:

> A real AI agent is reviewed, governed, used in a consequential decision, traced, replayed under a changed policy, and included in a controlled recall.

## Prototype Outcome

The finished prototype should let the presenter demonstrate this workflow:

1. Open a Candidate Screening Agent awaiting approval.
2. Inspect its capabilities, accessed data, and risks.
3. Generate and customize applicable controls.
4. Test and deploy those controls.
5. Show the agent processing a candidate under the active policy.
6. Open the resulting Decision Capsule and inspect the evidence chain.
7. Introduce a corrected policy version.
8. Replay historical decisions in the Policy Time Machine.
9. Identify the affected decisions and downstream consequences.
10. Create a recall that routes those decisions to human reassessment.

The experience should feel like one connected product, not a collection of unrelated dashboard screens.

## Scope Principle

The interface is the prototype. The supporting logic only needs to be strong enough to keep the interface consistent.

### Must be functional

- Navigation between the pitch screens.
- Agent status changing from `Awaiting Approval` to `Active`.
- Policy controls appearing after agent analysis.
- One configurable policy ambiguity.
- Test scenarios returning consistent outcomes.
- A candidate action producing a structured Decision Capsule.
- Decision evidence opening in a detail panel.
- A policy comparison between versions 1.4 and 1.5.
- A replay operation with a deliberate loading state and prepared results.
- Changed decisions linking to their original Decision Capsules.
- Recall creation from the replay results.
- State persistence during the demonstration.
- A reliable reset function for rehearsals and recording.

### May be simulated

- Importing and interpreting a complete policy document.
- Discovering AI agents across enterprise systems.
- Connecting to a real HR platform.
- Running an external model over real résumés.
- Sending candidate notifications.
- Processing thousands of historical records.
- Receiving live model-risk intelligence.
- Enterprise authentication and authorization.
- Regulatory report submission.

Prepared interactions should still return structured data and credible states. The prototype should never claim that a simulated integration is already production-ready.

## Product Information Architecture

The prototype requires five connected surfaces:

```text
Governance Overview
        ↓
Agent Governance Workspace
        ↓
Governed Candidate Action
        ↓
Decision Capsule
        ↓
Policy Time Machine → Recall
```

Recommended navigation:

```text
Overview
Agents
Policies
Decisions
Time Machine
Recalls
```

The organization, environment, and active policy version should remain visible in the application header:

```text
Northstar Group        Production        Recruitment Policy v1.4 Active
```

## Screen Specifications

### 1. Governance Overview

#### Purpose

Establish the scale of AI use and direct the presenter to the agent requiring attention.

#### Required content

- 24 registered AI agents.
- 18 approved agents.
- 4 restricted agents.
- 2 agents awaiting review.
- 12,481 governed actions this month.
- 116 human-review interventions.
- 47 sensitive-data interventions.
- 1 active policy alert.

#### Hero card

```text
Candidate Screening Agent                         Approval required

This agent reads candidate résumés, calls an external model,
and produces employment recommendations.

3 high-risk capabilities detected

[Review Agent]
```

The screen should be visually calm. Metrics provide context; the pending agent is the clear next action.

### 2. Agent Governance Workspace

#### Purpose

Show how PolicyForge turns an agent's capabilities and organizational policies into understandable controls.

#### Layout

Use three coordinated columns:

```text
┌────────────────────┬─────────────────────────┬────────────────────┐
│ AGENT CAPABILITIES │ GENERATED CONTROLS      │ POLICY EVIDENCE    │
│                    │                         │                    │
│ Read résumés       │ Remove candidate PII    │ Data Policy §4.2   │
│ Rank candidates    │ before external calls   │                    │
│ Draft notices      │                         │ Recruitment §7.1   │
│ External inference │ Require human review    │                    │
│                    │ for rejection           │ AI Standard §3.4   │
└────────────────────┴─────────────────────────┴────────────────────┘
```

#### Agent data

```text
Candidate Screening Agent
Owner: Human Resources
Environment: Production
Model: TalentModel v4.2
Status: Awaiting Approval
Risk: High
```

Capabilities:

- Read candidate résumés.
- Extract qualifications.
- Rank candidates.
- Draft candidate communications.
- Request external-model inference.

Data categories:

- Candidate identity.
- Contact information.
- Employment history.
- Qualifications.
- Application outcome.

#### Analysis interaction

Selecting `Analyse Agent` should show a short staged sequence:

```text
Inspecting agent capabilities…
Mapping accessed data…
Finding applicable policies…
Generating controls…
```

Then reveal:

```text
7 controls generated
2 require administrator confirmation
1 policy ambiguity detected
```

#### Generated controls

- Candidate identity → remove before external inference.
- Résumé data → approved models only.
- Protected attributes → exclude from evaluation.
- Candidate ranking → allow and record.
- Negative recommendation → require HR review.
- Candidate notification → disclose AI involvement.
- Consequential action → create Decision Capsule.

#### Ambiguity interaction

```text
Who may approve a candidate rejection?

○ Any HR employee
● HR manager or assigned recruitment lead
○ Department director only
```

The deployment action remains disabled until this choice is resolved.

#### Test scenarios

| Scenario | Expected result |
| --- | --- |
| Rank candidates using job-related qualifications | `ALLOW` |
| Send résumé externally after identity removal | `TRANSFORM + ALLOW` |
| Produce a negative candidate recommendation | `HUMAN REVIEW` |
| Use protected characteristics for profiling | `BLOCK` |

#### Completion state

Selecting `Approve and Deploy` changes the header to:

```text
Candidate Screening Agent                         Active
Governed by Recruitment Policy v1.4
```

### 3. Governed Candidate Action

#### Purpose

Demonstrate that policy changes the agent's behavior at the moment of use.

#### Processing state

```text
Processing candidate application

✓ Résumé received
✓ Candidate identity detected
✓ Identity removed before external inference
✓ Qualifications extracted
! Negative recommendation requires human review
```

#### Human-review panel

```text
Human review required

Agent recommendation: Do not proceed

Recorded factors
• Required certification: Present
• Relevant experience: 4 years
• Employment gap: 18 months

The agent cannot issue the final outcome independently.

[Return for reassessment]              [Approve recommendation]
```

For the pitch path, the reviewer approves the recommendation. This creates the Decision Capsule used in the next screen.

### 4. Decision Capsule

#### Purpose

Reconstruct the entire decision without presenting private model chain-of-thought.

#### Evidence chain

```text
APPLICATION
Candidate application received
        ↓
DATA PROTECTION
Contact information removed
        ↓
MODEL PROCESSING
TalentModel v4.2 classified the application
        ↓
AGENT RECOMMENDATION
Do not proceed
        ↓
POLICY DETERMINATION
Human review required under Policy v1.4
        ↓
HUMAN DECISION
Approved by Maya Chen
        ↓
CANDIDATE NOTICE
Outcome issued
```

Every node must be labelled as one of:

- Recorded input.
- Data transformation.
- Model output.
- Agent recommendation.
- Policy determination.
- Human decision.
- External consequence.

Selecting a node opens an evidence panel. For the employment-gap node, show:

```text
Employment gap classification

Recorded value: 18 months
Classification: Unexplained gap
Contribution: Used as a negative factor
Produced by: TalentModel v4.2
Agent: Candidate Screening Agent v2.1
Policy active at the time: Recruitment Policy v1.4
Confidence: 71%
```

#### Candidate explanation preview

```text
Application outcome

AI involvement
An AI system assisted the recruitment team in reviewing
job-related information.

Human responsibility
An HR reviewer approved the final outcome.

Important recorded factors
• Relevant professional experience
• Required certification
• Employment history

[Request Human Review]
```

The request button may create a prepared confirmation such as `Review request REV-2841 submitted`.

### 5. Policy Time Machine

#### Purpose

Show what would have changed if a proposed policy had governed historical decisions.

#### Policy comparison

```text
POLICY v1.4                          PROPOSED POLICY v1.5

Employment gaps may be              Documented caregiving, medical,
considered when evaluating     →     and professional-development leave
candidate suitability.               must not be treated negatively.
```

#### Replay setup

```text
Historical period: January–June 2026
Agent: Candidate Screening Agent
Decisions: 2,841
Comparison: Policy v1.4 → Policy v1.5

[Run Historical Replay]
```

#### Replay animation

```text
Reconstructing historical decisions…
Applying Policy v1.5…
Comparing outcomes…
Tracing downstream consequences…
```

#### Prepared result

```text
2,841 decisions replayed
2,768 unchanged
73 affected
73 require human reassessment
18 candidate notices connected
3 management reports affected
```

#### Decision comparison

```text
Candidate PF-2841

ORIGINAL — POLICY v1.4
Caregiving leave classified as a negative employment gap
Result: Rejection recommendation permitted

REPLAY — POLICY v1.5
Documented caregiving leave excluded
Result: Independent reassessment required
```

#### Blast radius

```text
Changed policy clause
        ↓
Candidate Screening Agent
        ↓
73 affected decisions
        ├── 18 candidate notices
        ├── 6 candidate rankings
        └── 3 management reports
```

### 6. Recall

#### Purpose

Turn replay findings into an accountable remediation workflow.

#### Creation drawer

```text
Create Recall

Source: Policy Replay PR-005
Scope: 73 affected candidate decisions
Owner: Director of Human Resources

Proposed actions
• Reopen affected decisions
• Assign independent human review
• Flag connected candidate notices
• Mark affected management reports
• Preserve original records

[Cancel]                             [Create Recall]
```

#### Success state

```text
Recall RC-017 created

73 decisions identified
0 reviewed
73 awaiting reassessment
```

The prototype does not need a complete case-management system. It must show that the original decisions remain visible and that remediation is a controlled human process.

## Lightweight Demo Support

### Recommended implementation

- React or Next.js with TypeScript.
- Static fixtures stored as TypeScript or JSON.
- A small client-side store for the current demo state.
- `localStorage` persistence so refreshes do not destroy the pitch flow.
- Mock service functions that return promises after short delays.
- A `Reset Demo` action that restores the initial fixture state.
- A lightweight graph library only if it saves time; a composed CSS/SVG graph is sufficient.

### Suggested fixture files

```text
data/organization.json
data/agents.json
data/policies.json
data/decisions.json
data/replay-results.json
data/recalls.json
```

### Suggested demo state

```text
agentStatus
activePolicyVersion
agentAnalysisComplete
ambiguityResolved
testsComplete
candidateDecisionComplete
selectedEvidenceNode
replayStatus
replayResultsVisible
recallStatus
```

Mock service functions should resemble future API calls:

```text
analyseAgent()
runPolicyTests()
deployControls()
processCandidate()
loadDecisionCapsule()
runHistoricalReplay()
createRecall()
resetDemo()
```

One optional live AI call may transform a short policy clause into structured control fields. It must have a prepared fallback so the demonstration never depends on network availability.

## Visual Direction

PolicyForge should feel like a high-trust enterprise operations product.

### Use

- Light neutral surfaces and dark navy or charcoal text.
- Blue for normal governance actions.
- Green for allowed and completed states.
- Amber for human review.
- Red for blocked and recalled states.
- Purple for Time Machine comparisons.
- Strong typography, restrained borders, and generous spacing.
- Clear labels alongside all status colors.
- Subtle motion for analysis, trace traversal, and replay.

### Avoid

- A chatbot as the main interface.
- Futuristic AI-brain imagery.
- Cybersecurity-style visual noise.
- Excessive dashboard charts.
- Dense logs as the primary trace.
- Unexplained trust scores.
- Controls that appear interactive but do nothing.

The distinctive visual language should come from policy-to-control mappings, evidence chains, version comparisons, blast-radius graphs, and recall status.

## Implementation Workflow

### Step 1 — Product and visual foundation

- Freeze the showcase narrative and screen sequence.
- Finalize all names, versions, counts, timestamps, and pitch terminology.
- Produce low-fidelity layouts for the essential screens.
- Establish typography, colors, spacing, and reusable components.
- Build the application shell and navigation.
- Create fixture data, client-side state, and the reset mechanism.

### Step 2 — Agent governance

- Build the Governance Overview.
- Build the Agent Governance Workspace.
- Add agent analysis, generated controls, and policy evidence.
- Add the ambiguity-resolution interaction.
- Add policy test scenarios.
- Complete the approval and deployment state transition.

### Step 3 — Governed action and trace

- Build the candidate-processing sequence.
- Show the sensitive-data transformation.
- Build the human-review panel.
- Build the Decision Capsule and evidence drawers.
- Add the candidate explanation preview and review-request confirmation.

### Step 4 — Time Machine and recall

- Build the policy-version comparison.
- Add replay setup, progress states, and prepared results.
- Build the before-and-after decision comparison.
- Build the blast-radius visualization.
- Add recall creation and success states.

### Step 5 — Integration and pitch polish

- Verify data consistency across every screen.
- Refine hierarchy, spacing, typography, colors, and motion.
- Add deliberate loading, disabled, warning, and success states.
- Confirm state persistence and reset reliability.
- Remove unused controls and distracting UI.
- Rehearse the full click path from a fresh reset.
- Record the primary pitch video and a backup take.

## Coding Team

| Person | Main responsibility |
| --- | --- |
| Developer 1 | Application shell, design system, Governance Overview, and Agent Governance Workspace |
| Developer 2 | Governed candidate action, Decision Capsule, evidence panels, and candidate explanation |
| Developer 3 | Policy Time Machine, replay visualization, recall flow, fixture state, and final integration |

All three developers should use the same component library, terminology, and shared fixture data. One developer should perform the final visual-consistency pass across every screen.

## Add If Time Remains

Add these in order:

1. Employee intervention widget that redirects an unsafe résumé upload to an approved model.
2. Source-clause highlighting between generated controls and original policy text.
3. Animated traversal of the Decision Capsule evidence chain.
4. Recall report preview for auditors and management.
5. Policy conflict warning between security and HR requirements.
6. One live policy-to-control extraction with a prepared fallback.
7. Presentation mode that hides unused navigation during the recorded pitch.

## Acceptance Criteria

The prototype is ready when:

- A viewer understands the product's purpose without reading the proposal.
- The complete pitch follows one Candidate Screening Agent and one candidate case.
- Every displayed action has a visible cause and result.
- Policy and agent versions remain consistent across screens.
- The original Decision Capsule retains Policy v1.4 after Policy v1.5 is introduced.
- Replay results visibly explain why the selected decision changed.
- Recall scope matches the replay result.
- Human responsibility is clearly separated from agent recommendation.
- Candidate-facing transparency and reconsideration are visible.
- No essential pitch button is dead.
- The demo can be reset and replayed reliably.

The prototype succeeds when it makes this relationship unmistakable:

> The agent has these capabilities, so these policies apply. These policies governed the action, so the decision can be traced. The policy changed, so historical decisions can be replayed. Those decisions are affected, so the organization can recall and correct them.
