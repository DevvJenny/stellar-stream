# StellarStream — Drips Wave Sprint & Work Plan

## Overview
StellarStream is an open-source, continuous payment-streaming protocol and dashboard built on the Stellar network and Soroban smart contracts. It enables automated, second-by-second linear token streaming for payroll, subscriptions, vesting, and grants.

Through the **Drips Wave Program**, we aim to empower external developers and accelerate our roadmap by publishing modular, tightly scoped issues across two-week sprint cycles. Every issue will feature clear acceptance criteria, reproducible test cases, and dedicated maintainer review.

---

## Issue Scoping & Contributor Workflow
To ensure contributor success and high code quality, all issues posted to Wave will follow a standardized template:
- **Defined Scope & Context**: User story, affected components (`contracts/`, `backend/`, `frontend/`), and reference ADRs.
- **Explicit Acceptance Criteria**: Quantifiable definitions of done (e.g., unit test coverage, lint checks, type safety).
- **Complexity Tiering**: Labeled as `good-first-issue` (1–3 days), `intermediate` (3–5 days), or `advanced` (sprint-long).
- **Maintainer SLA**: Initial PR review within 24–48 hours, active guidance, and automated CI feedback.

---

## Planned Work Categories

### 1. Bug Fixes & System Hardening
- **Vesting Calculation & Rounding Precision**: Resolve fractional token discrepancies on extreme durations (micro-stroop precision).
- **Webhook Resilience & Dead-Letter Recovery**: Harden delivery worker retry semantics, idempotency headers, and queue backlog alerts.
- **Wallet Connection Edge Cases**: Fix session expiration and reconnection states with Freighter and Stellar wallet adapters.
- **SQLite Concurrency**: Prevent database locking bottlenecks under concurrent high-throughput stream events.

### 2. Feature Expansions
- **WebSocket Streaming Updates**: Transition from periodic polling to real-time WebSocket / SSE telemetry for active stream balances.
- **Stream Controls**: Add support for stream top-ups, sender-controlled pauses, and multi-asset routing (XLM, USDC).
- **Soroban Contract Upgrades**: Expand Soroban smart contract logic to support cliff periods and revocable vs. irrevocable streams.
- **Batch Stream Operations**: Implement CSV/JSON batch disbursement to initiate multiple recipient streams in a single transaction.

### 3. Testing & Reliability
- **Soroban Rust Contract Tests**: Author invariant and fuzz tests for payment distribution and emergency withdrawals.
- **End-to-End Suite Expansion**: Extend Playwright E2E suites covering the complete user journey: wallet connect -> stream funding -> live vesting -> cancellation.
- **Load & Chaos Testing**: Mock high-frequency payment streams to validate backend event indexing performance.

### 4. UI/UX & Accessibility (a11y)
- **Interactive Visualizers**: Build live canvas/SVG vesting curve visualizers showing real-time accrued funds.
- **Accessibility Compliance**: Audit and remediate color contrast, keyboard navigation, and ARIA attributes to meet WCAG 2.1 AA standards.
- **Mobile Responsive Polish**: Optimize dashboard controls for mobile web wallets.

### 5. Documentation & Developer Experience
- **Interactive API Documentation**: Build OpenAPI / Swagger UI specs with runnable code samples in TypeScript and Python.
- **Soroban Integration Recipes**: Step-by-step guides for developers integrating StellarStream into dApps and DAOs.
- **Local Dev Sandbox**: Streamline one-command Docker container spin-up for local Soroban RPC and mock Horizon instances.

---

## Sprint Execution & Milestones
- **Sprint Cycle 1–2**: Foundations, bug triage, test coverage, and documentation refactor (`good-first-issue` focus).
- **Sprint Cycle 3–4**: WebSockets, interactive vesting graphs, and contract fuzzing (`intermediate`).
- **Sprint Cycle 5+**: Advanced Soroban contract features, multi-token streams, and batch payouts (`advanced`).

By partnering with Drips Wave, StellarStream turns community contributions into a sustainable, production-grade Web3 streaming primitive.
