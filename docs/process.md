# Grant Program Process

This document describes how the Quantova Grants Program works end to end: the grant
levels, how to apply, how applications are reviewed, and how milestones are paid.

You can apply on the website at **https://quantova.org/grants/** or via a pull
request to this repository. Questions: **Grants@quantova.org**.

## Grant levels

The program is tiered so that small, fast grants and larger efforts each have an
appropriate process.

| Level | Typical size (in QTOV) | Review | Best for |
|---|---|---|---|
| **Level 1** | up to ~10,000 USD-equivalent | Light-touch, fastest | Small tools, fixes, docs, experiments |
| **Level 2** | up to ~30,000 USD-equivalent | Standard committee review | Most projects: libraries, integrations, apps |
| **Level 3** | larger / multi-milestone | Full committee review | Substantial infrastructure or research |

Amounts are paid in QTOV (or its USD-equivalent in QTOV). The figures above are
guidelines; the committee may adjust scope and amount during review.

## Step 1 — Prepare your application

Read the [application template](../applications/application-template.md) and fill in
all the mandatory sections, especially a clear **relation to Quantova** and a
**milestone-based roadmap** (roughly 1 milestone ≈ 1 month). A well-specified
roadmap with testable deliverables is the single biggest factor in a smooth review.

## Step 2 — Submit

Choose one:

- **Website:** submit at https://quantova.org/grants/.
- **GitHub pull request:** fork this repo, copy
  `applications/application-template.md` to `applications/your_project_name.md`,
  fill it out, and open a PR. Do not modify the template file directly.

The combination of your submitting GitHub account (or website submission) and your
QTOV payment address is your unique identifier in the program.

## Step 3 — Review

A grants committee — individuals who understand the funding priorities of the
Quantova ecosystem — evaluates each application for technical merit, ecosystem fit,
feasibility, and the team's ability to deliver and maintain the work. The committee
may:

- ask questions or request changes in the PR or by email,
- request a niche expert review where useful,
- adjust scope, milestones, or amount,
- accept or decline the application.

Decisions and feedback are shared with you directly. Accepted applications are
merged (for PRs) and listed in [applications/README.md](../applications/README.md).

## Step 4 — Agreement

Before work begins, the applicant and Quantova agree on the final terms (scope,
milestones, amounts, and the grant agreement). The application document is referenced
by the agreement, which is why its mandatory sections must be complete and accurate.

## Step 5 — Build and deliver milestones

Work is delivered milestone by milestone. Submit each completed milestone for
evaluation following [milestone-delivery.md](milestone-delivery.md). The committee
reviews the deliverables against the specification in your application.

## Step 6 — Payment

Grants are paid in **QTOV** after delivery and approval of each milestone, to the
payment address in your application. An initial milestone may be structured as a
smaller deliverable so both sides can validate the working relationship early.

## Amendments

The application can be amended at any time, but this requires re-evaluation by the
committee. If, during development, your project significantly deviates from the
original specification, open a new pull request that modifies the existing
application (or contact Grants@quantova.org).

## Code of conduct

All participants are expected to follow the
[Code of Conduct](../CODE_OF_CONDUCT.md). The committee may block users for
violations.
