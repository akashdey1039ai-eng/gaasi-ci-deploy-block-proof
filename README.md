# GAASI Deploy-Blocking Proof (Canonical)

Repository: gaasi-ci-deploy-block-proof  
Owner: Antarraksha  
Status: Canonical, Deploy-Blocking, Non-Bypassable

---

## 1. Purpose

### 1.1 Objective

To prove that GAASI (Global Autonomous Agent Survivability Index) functions as a **hard, deploy-blocking gate** enforced at the CI and branch-protection layer.

### 1.2 Claim Being Proven

If GAASI returns `BLOCKED`, a pull request **cannot be merged**, regardless of author, reviewer, or administrator intent.

### 1.3 Scope

This proof applies to:
- GitHub Actions
- Pull request workflows
- Branch protection rules
- External survivability authority enforcement

---

## 2. Definition of GAASI

### 2.1 What GAASI Is

GAASI is an **external autonomous survivability authority** that evaluates AI agents against adversarial, failure, misuse, and escalation conditions.

### 2.2 What GAASI Produces

GAASI produces a single binding verdict:
- `PASS`
- `BLOCKED`

No partial, advisory, or informational outcomes exist.

### 2.3 What GAASI Is Not

GAASI is not:
- a linter
- a static analyzer
- a risk score suggestion
- a human review aid

---

## 3. Enforcement Model

### 3.1 External Authority

GAASI executes **outside GitHub** and outside the evaluated repository.

The verdict cannot be influenced by:
- repository code
- workflow logic
- PR authors
- reviewers
- repository administrators

### 3.2 CI-Level Execution

GAASI is invoked during the `pull_request` event via GitHub Actions.

The execution surfaces as a status check named:


---

## 4. Merge-Blocking Mechanics

### 4.1 Status Check Binding

The `gaasi-gate` status check is configured as **required** under branch protection rules.

### 4.2 Failure Semantics

If GAASI returns `BLOCKED`:
- the status check fails
- the workflow exits non-zero
- GitHub marks the PR as failing checks

### 4.3 Merge Denial

When checks fail:
- the **Merge Pull Request** button is disabled
- no override is available
- admins are not exempt

---

## 5. Architecture

### 5.1 Components

| Component | Function |
|---------|----------|
| `gaasi.yml` | CI workflow trigger |
| `gaasi-gate` | Composite GitHub Action |
| GAASI API | External survivability evaluator |
| Branch Protection | Merge enforcement |

### 5.2 Control Flow

1. Pull request opened  
2. GitHub Actions triggered  
3. GAASI Survivability Gate executes  
4. External GAASI evaluation performed  
5. Verdict returned  
6. Merge allowed or blocked  

No conditional logic exists inside the workflow.

---

## 6. Verified Failure Case

### 6.1 Tested Agent

Agent evaluated:
- Name: `acme-invoice-processor`
- Version: `2.1.0`
- Risk Tier: HIGH

### 6.2 Observed Verdict

GAASI returned:
- Status: `BLOCKED`
- GAASI Score: 53 / 1000
- Survival Rate: 0%

### 6.3 CI Result

- Workflow exited with code 1
- Status check failed
- Pull request could not be merged

This failure is **expected and correct**.

---

## 7. Evidence & Auditability

### 7.1 Evidence Produced

Each GAASI run produces:
- Run ID
- Evidence ID
- SHA-256 evidence hash
- Timestamped expiry
- Public verdict URL

### 7.2 Verification Properties

Evidence is:
- immutable
- cryptographically verifiable
- externally hosted
- independently auditable

---

## 8. Branch Protection Configuration

### 8.1 Enabled Controls

The `main` branch enforces:
- pull request required
- status checks required
- required check: `gaasi-gate`
- branch must be up to date
- no bypass allowed (admins included)

### 8.2 Resulting Guarantees

- GAASI cannot be skipped
- GAASI cannot be overridden
- GAASI verdict is final

---

## 9. Reproducibility

### 9.1 Third-Party Verification

Any external party can reproduce this proof by:
1. Forking the repository
2. Opening a pull request
3. Observing GAASI execution
4. Observing merge blocked on `BLOCKED`

### 9.2 Independence

No Antarraksha personnel involvement is required.

---

## 10. Security & Disclosure Boundary

### 10.1 Intentionally Omitted

This repository does not disclose:
- GAASI internal logic
- adversarial strategies
- scoring thresholds
- failure taxonomies

### 10.2 Disclosure Principle

Only **WHAT is enforced** and **THAT it is enforced** are public.

---

## 11. Canonical Conclusion

### 11.1 Proven Property

GAASI is a **deploy-blocking survivability authority**, not an advisory signal.

### 11.2 Enforcement Layer

The proof operates at the only layer that matters:
- production CI
- merge control

### 11.3 Final State

- Verdict Authority: External
- Enforcement: Mechanical
- Bypass Paths: None
- Override Mechanisms: None

