# Quantova Grants Program

<div align="center">

Funding open-source software and research that strengthens the Quantova ecosystem.

[How to apply](#how-to-apply) · [Apply on the website](https://quantova.org/grants/) · [Grants@quantova.org](mailto:Grants@quantova.org)

</div>

---

The Quantova Grants Program funds teams and individuals building public goods for
Quantova — the post-quantum Layer-1 blockchain. We support work across developer
tooling, core infrastructure, post-quantum cryptography and research, the Quantova
Virtual Machine (QVM), wallets, education, and community resources.

Grants are non-dilutive: we fund open-source work as a public good, not equity.
Applications and milestone deliveries are tracked transparently here on GitHub, so
the ecosystem can see what is being built and how it progresses.

There are two ways to apply: open a pull request in this repository (the public,
transparent path described below), or submit through the website at
[quantova.org/grants](https://quantova.org/grants/). For private or sensitive
proposals, email [Grants@quantova.org](mailto:Grants@quantova.org).

## Table of contents

- [What we fund](#what-we-fund)
- [What we do not fund](#what-we-do-not-fund)
- [Grant levels](#grant-levels)
- [How to apply](#how-to-apply)
- [Application process](#application-process)
- [Evaluation criteria](#evaluation-criteria)
- [Milestone delivery](#milestone-delivery)
- [Requests for Proposals (RFPs)](#requests-for-proposals)
- [Repository structure](#repository-structure)
- [Help and contact](#help-and-contact)

## What we fund

We fund free and open-source work that benefits the Quantova ecosystem, with a
particular focus on builders rather than end users. Priority domains:

- **Post-quantum cryptography & research** — implementations, audits, benchmarks,
  and research advancing Quantova's NIST post-quantum signature stack (Dilithium,
  Falcon, SPHINCS+) and SHA3-256 hashing.
- **Core infrastructure** — node tooling, indexers, explorers, RPC/gateway
  infrastructure, monitoring, and reliability tooling.
- **Developer tooling & SDKs** — libraries, frameworks, and integrations built on
  qweb3.js / qweb3.py and the QVM.
- **Quantova Virtual Machine (QVM)** — Solidity/QVM tooling, contract libraries,
  testing frameworks, and developer experience.
- **Wallets & key management** — wallet integrations and post-quantum key-handling
  tooling (for example, around QMask).
- **Bridges & interoperability** — cross-chain tooling and security/conformance
  testing.
- **Security & conformance** — test suites, fuzzing, audits, and verification
  tooling for the protocol, runtime, bridge, governance, and QNS.
- **Education & community** — documentation, tutorials, courses, workshops, and
  ecosystem resources.

See [docs/categories.md](docs/categories.md) for detail and examples in each domain,
and [rfps/](rfps) for specific things we are actively looking to fund.

## What we do not fund

- Token launches, fundraising, trading, betting, or speculative financial products.
- Closed-source work, or work that will not be openly available to the community.
- Networks or forks that compete with the canonical Quantova network.
- Marketing-only proposals with no open-source deliverable.
- Work that is illegal, or that creates meaningful security or safety risk.

For-profit teams are welcome to apply, but the grant-funded work itself must be
open-source and freely available.

## Grant levels

Grants are paid in QTOV (or a stablecoin equivalent where appropriate) against
delivered milestones. Levels are guidelines, not hard caps.

| Level | Indicative funding | Typical scope | Reviews required |
|---|---|---|---|
| **Level 1** | up to $10,000 equivalent | A small, well-scoped tool, fix, or research note | 2 committee approvals |
| **Level 2** | up to $30,000 equivalent | A substantial library, integration, or research deliverable | 3 committee approvals |
| **Level 3** | $30,000+ equivalent | A large, multi-milestone project of clear ecosystem value | Full committee review |

Funding is disbursed **per milestone**, after each milestone is delivered and
accepted. The first milestone may be partially funded up front at the committee's
discretion.

## How to apply

You can apply either on GitHub (transparent, public) or via the website.

### Apply on GitHub

1. **Read** the [category guidelines](docs/categories.md), the
   [process](docs/process.md), and the
   [Terms & Conditions](docs/terms-and-conditions.md).
2. **Fork** this repository.
3. In your fork, **copy** the application template
   ([applications/application-template.md](applications/application-template.md)) to
   a new file named after your project, e.g. `applications/my-project.md`. Do
   **not** modify the template file itself.
4. **Fill out** the template with as much detail as possible. The more complete and
   specific your application, the faster the review.
5. **Open a pull request** into this repository. The PR should contain **one new
   file** — your application. See [applications/README.md](applications/README.md).

A grant evaluator will review your PR, ask questions in the comments, and request
changes if needed. Your application is **accepted when it receives the required
number of approvals** (see [Grant levels](#grant-levels)) and the PR is merged.

### Apply on the website

Prefer a form, or applying privately? Submit at
[quantova.org/grants](https://quantova.org/grants/). Website applications follow the
same evaluation criteria; sensitive proposals can also be sent directly to
[Grants@quantova.org](mailto:Grants@quantova.org).

## Application process

```
Read guidelines  ->  Fork & copy template  ->  Open PR (one file)
       ->  Evaluator review & discussion  ->  Required approvals
       ->  PR merged (grant approved)  ->  Deliver milestones  ->  Payment per milestone
```

The full process, including amendments and timelines, is in
[docs/process.md](docs/process.md). Accepted applications can be amended later, but
material changes require re-evaluation — open a new PR that modifies your existing
application file.

## Evaluation criteria

Applications are assessed on:

- **Ecosystem impact** — how much the work benefits Quantova builders and users, and
  its alignment with ecosystem priorities and [RFPs](rfps).
- **Technical approach** — soundness, feasibility, and clarity of the plan and the
  team's ability to deliver.
- **Open source** — all outputs must be open-source or otherwise freely available,
  under a recognized license.
- **Budget** — cost-effectiveness and a sensible allocation of funds across
  milestones.
- **Maintenance** — whether the work will be usable and maintainable after the
  grant ends.

## Milestone delivery

Once your grant is approved, you deliver the work in the milestones defined in your
application, and each accepted milestone is paid. The full delivery and review
process is in [docs/milestone-delivery.md](docs/milestone-delivery.md). All funded
outputs must be open-source or freely accessible.

## Requests for Proposals

In addition to open applications, we publish **RFPs** — specific projects we are
actively seeking builders for. If you want to work on something the ecosystem needs,
start with [rfps/](rfps). You can also **suggest an RFP** for tooling or research you
believe Quantova needs, using the process in [rfps/README.md](rfps/README.md).

## Repository structure

```
Grants-Program/
  applications/      submitted applications (one Markdown file each) + the template
  rfps/              Requests for Proposals + how to suggest one
  docs/              categories, process, milestone delivery, FAQ, Terms & Conditions
  .github/           issue & pull-request templates
  CODE_OF_CONDUCT.md
  CONTRIBUTING.md
  LICENSE
  LICENSE-OVERVIEW.md
  README.md
```

## Help and contact

- **Questions about an application:** open an issue in this repository, or comment
  on your PR.
- **General / private / website enquiries:** [Grants@quantova.org](mailto:Grants@quantova.org)
- **Apply via the website:** [quantova.org/grants](https://quantova.org/grants/)

Please follow our [Code of Conduct](CODE_OF_CONDUCT.md) in all interactions.

## License

Content in this repository is licensed under the Business Source License 1.1
(BUSL-1.1), © 2026 Quantova Inc. See [LICENSE](LICENSE) and
[LICENSE-OVERVIEW.md](LICENSE-OVERVIEW.md). Grant-funded deliverables are licensed
under their own open-source licenses as agreed in each grant.
