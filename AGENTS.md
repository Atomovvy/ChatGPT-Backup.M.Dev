# AGENTS.md

Atomovvy-local operating overlay for agents working in `Atomovvy/ChatGPT-Backup.M.Dev`.

## Repository role

This repository is an Atomovvy-maintained external copy of the upstream ChatGPT Backup Tool project by Fredy Sandoval. Upstream source, authorship and licensing remain distinct from Atomovvy policy metadata.

```text
REPOSITORY_ROLE=EXTERNAL_COPY
UPSTREAM_PRODUCT_OWNERSHIP!=ATOMOVVY
LOCAL_POLICY_OVERLAY!=UPSTREAM_PROJECT_POLICY
```

The current repository license is MIT. Preserve upstream copyright and license notices.

## Central policy inheritance

For Atomovvy-specific repository work, inherit current policy from `Atomovvy/Atomovvy`, including current `AGENTS_BASE.md`, `GIT_POLICY.md`, `PROMPT_POLICY.md`, `MULTI_AGENT_LOCK_POLICY.md`, `P2C_SIMPLE_LOCK_V2_RUNBOOK.md`, `VALIDATION_POLICY.md` and `HANDOFF_POLICY.md`.

If required central policy is unavailable, report `CENTRAL_POLICY_UNAVAILABLE` and remain read-only for Atomovvy-directed mutations.

## External-copy and data boundary

- Confirm upstream origin, license and the Atomovvy-local purpose before modifying product code.
- Do not present upstream code, history, branding or authorship as Atomovvy-original work.
- This rollout changes no extension product code, export behavior, ChatGPT data handling, build, release or upstream workflow.
- Exported conversations, projects and user data are potentially private content. This policy overlay grants no authority to collect, inspect, publish, upload or redistribute such data.
- Other repositories remain read-only unless separately authorized.
- Upstream synchronization, rebases, force pushes, history rewriting, releases and publication require separate bounded review.

## Repository writer coordination

For ordinary hosted Atomovvy GitHub mutations in this repository, use P2-C Simple Lock v2:

```text
P2C_SIMPLE_LOCK_V2_STATUS=ACTIVE
COORDINATION_MODE=P2C_SIMPLE_LOCK_V2
LOCK_REF=coordination/write-lock-v2
LOCK_FILE=LOCK.json
P2C_LEGACY_STRONG_STATUS=FROZEN_REFERENCE
LEGACY_STRONG_DEFAULT_FOR_ORDINARY_WRITES=NO
```

Freshly fetch and validate the live lock, acquire it by exact file-SHA compare-and-swap, and verify exact ownership before the first ordinary mutation. Read-only work does not require the lock. Coordination failure fails closed without Legacy Strong fallback.

The lock coordinates conforming writers only. It does not replace Git/target freshness, upstream provenance checks, privacy review, licensing review, validation or merge authority.

## Git workflow

Atomovvy-specific tracked changes use a dedicated branch and Draft PR by default. Do not merge without explicit user approval.

## Handoff

Atomovvy-local repository-changing work is recorded in `Documentation/Workflow/AGENT_LAST_RUN.md`.
