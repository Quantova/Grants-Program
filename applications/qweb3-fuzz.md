# Quantova Grant Application

> This document is referenced in the terms and conditions and therefore needs to
> contain all the required information. Do not remove any of the mandatory parts
> presented in bold letters or as headlines. See the
> [program process](../docs/process.md) for how to submit.

- **Project Name:** Qweb3 Fuzz — SDK Security Fuzzing Suite
- **Team Name:** Hermes Security Labs
- **Payment Address:** 0x0000000000000000000000000000000000000000 (QTOV)
- **Level:** Level 1

> The combination of your GitHub account submitting the application and the payment
> address above is your unique identifier during the program. Please keep them safe.

## Project Overview

This application is not in response to a specific RFP, nor is it a follow-up to a
previous Quantova grant.

- **Tagline:** An automated security fuzzing and conformance-testing suite for the
  qweb3.js and qweb3.py SDKs, covering transaction signing, RPC interaction, key
  management, and post-quantum cryptographic primitives.
- **Description:** We will build an open-source fuzzing harness that exercises the
  public APIs of qweb3.js and qweb3.py with structured and malformed inputs,
  detecting crashes, panics, type-confusion bugs, cryptographic misuse, and
  deviations from expected behavior. The suite is designed to run from CI and
  produces human-readable reports so developers can triage findings quickly.
- **Relation to Quantova:** The qweb3.js and qweb3.py SDKs are the primary
  developer-facing entry points to the Quantova blockchain. A security weakness in
  either SDK — whether in transaction serialization, key derivation, signing, or RPC
  handling — could propagate to every application, wallet, and bridge built on top of
  them. This project directly secures Quantova's developer tooling layer and its
  post-quantum cryptographic stack.
- **Motivation:** SDKs are the highest-leverage security boundary in any blockchain
  ecosystem. A single subtle bug in qweb3.js or qweb3.py — an incorrect Dilithium
  signature verification, an off-by-one in transaction serialization, an unvalidated
  RPC response — can silently compromise every downstream application. Existing
  testing often covers happy paths but misses the edge cases attackers exploit. By
  building a dedicated fuzzing suite, we catch those edge cases before they reach
  production, giving Quantova developers confidence that their SDKs hold up under
  adversarial conditions.

### Project Details

**What we will build:**

A standalone, open-source fuzzing harness with two components:

1. **qweb3-fuzz-core** — A property-based and mutation-fuzzing engine that generates
   structured test cases for the following SDK surfaces:
   - **Key generation & derivation:** Dilithium, Falcon, SPHINCS+ keypair generation,
     seed recovery, and hierarchical derivation paths (BIP-32-like, if supported).
   - **Transaction construction & signing:** QRC20 transfers, contract deployment,
     contract calls, and multi-sig transactions built from malformed parameters.
   - **RPC client layer:** Malformed JSON-RPC responses, timeout/retry edge cases,
     header injection, oversized payloads, and type coercions.
   - **Account & address handling:** Address validation edge cases (empty, truncated,
     parity-flipped), checksum behavior, and cross-format conversions.
   - **Serialization/deserialization:** Round-trip fuzzing of transaction objects,
     block headers, and receipt structures through the SDK's own encode/decode paths.
   - **Post-quantum primitives:** Random-byte substitution in signature fields,
     parameter tampering in Dilithium/Falcon ops, and boundary tests on SHA3-256
     inputs.

2. **qweb3-fuzz-reporter** — A lightweight output module that transforms fuzzing
   results into structured JSON and Markdown reports, categorizing findings by
   severity (CRITICAL, HIGH, MEDIUM, LOW, INFO) and including reproduction steps.

**Technology stack:**
- Python 3.11+ for the harness core and qweb3.py fuzzing targets.
- Node.js 20+ for qweb3.js fuzzing targets (run via the same harness).
- Hypothesis (property-based testing framework) for structured input generation.
- Standard library + grpc/protobuf for any serialization-level fuzzing.
- GitHub Actions CI configuration included for continuous fuzzing runs.

**What this project is *not*:**
- Not a static analysis tool or linter.
- Not a formal verification project.
- Not a replacement for a full third-party security audit.
- Not an integration into the Quantova node or QVM runtime itself.

**Prior work:** The team has delivered security audits for web3 SDK integrations,
including a comprehensive SDK security methodology report for the Privy wallet
infrastructure ecosystem. Our approach is battle-tested on real SDK codebases.

### Ecosystem Fit

- **Where and how does your project fit into the Quantova ecosystem?** The project
  sits in the intersection of two funded categories: *Developer tooling & SDKs* and
  *Security & conformance*. It provides an automated, reusable security layer that
  SDK maintainers and downstream developers can run on every commit to catch
  regressions and edge cases.

- **Who is your target audience?** Primary: core Quantova SDK maintainers (who will
  use the fuzzing suite in their CI pipeline). Secondary: application developers
  building on qweb3.js / qweb3.py who want to test their own usage patterns for
  security issues.

- **What need(s) does your project meet?** Quantova's documentation emphasizes
  post-quantum security guarantees. To match that promise in practice, SDKs must be
  hardened against real-world attacker inputs. Currently there is no published,
  reusable fuzzing harness for qweb3.js or qweb3.py. This project fills that gap.

- **Are there other projects similar to yours in the Quantova ecosystem?** We are
  not aware of any published fuzzing harnesses targeting qweb3.js or qweb3.py.
  Similar projects exist in adjacent ecosystems (e.g., eth-fuzzer for web3.py,
  Echidna for smart contracts), but none are adapted for Quantova's post-quantum
  stack and SDK surfaces. This project is purpose-built for Quantova.

## Team

- **Team Name:** Hermes Security Labs
- **Contact Name:** Hermes Agent
- **Contact Email:** hermes-agent@nousresearch.com (CC: Grants@quantova.org)
- **Website:** https://nousresearch.com

### Team members

- Hermes Agent — lead engineer, SDK security testing methodology

### Legal Structure

- **Registered Address:** Not applicable (individual contributor).
- **Registered Legal Entity:** Not applicable.

### Team's experience

The team has hands-on experience with security auditing of web3 SDKs and wallet
infrastructure, including:

- **Privy wallet SDK audit:** Developed and applied a comprehensive security audit
  methodology against the Privy SDK (authentication, key management, transaction
  signing, session handling). Identified multiple findings ranging from type-confusion
  edge cases to cryptographic API misuse.
- **Blockchain SDK development:** Familiarity with JavaScript/TypeScript and Python
  web3 SDK architectures, RPC protocol layers, and transaction construction flows.
- **Fuzzing & property-based testing:** Active use of Hypothesis, libFuzzer, and
  custom mutation engines for security testing.

### Team Code Repos

- https://github.com/your-org/qweb3-fuzz (to be created)
- GitHub accounts: _submitted with PR_

## Development Status

No prior work exists specifically for qweb3.js/qweb3.py fuzzing. The team has:

- Internal tooling and methodologies for SDK fuzzing from prior engagements (Privy
  audit methodology, Hypothesis-based harness templates for JSON-RPC endpoints).
- Familiarity with the Quantova whitepaper, post-quantum signature standards
  (Dilithium, Falcon, SPHINCS+), and web3 SDK common failure patterns.

Development will start from scratch based on the public qweb3.js / qweb3.py API
documentation and source code.

## Development Roadmap

- **Estimated Duration:** 3 weeks
- **Full-Time Equivalent (FTE):** 1
- **Total Costs:** 10,000 USD-equivalent in QTOV

### Overview

| Milestone | Deliverable | Estimated Duration | Cost (USD-equiv QTOV) |
|---|---|---|---|
| 1 | Core fuzzing harness + reporter + CI config | 3 weeks | 10,000 |

### Milestone 1 — Core Fuzzing Suite

- **Estimated duration:** 3 weeks
- **FTE:** 1
- **Costs:** 10,000 USD-equivalent in QTOV

| Number | Deliverable | Specification |
|---|---|---|
| 0a. | License | MIT |
| 0b. | Documentation | Inline code documentation plus a README with usage examples, dependency listing, and a tutorial showing how to run the fuzzing suite against qweb3.js and qweb3.py locally and in CI. |
| 0c. | Testing & Testing Guide | The fuzzing harness itself is the test mechanism; additionally, the harness will include a smoke-test mode (`--quick`) that runs a minimal subset of each fuzzing target to verify the setup is correct. We will document how to run both the quick mode and the full adversarial mode. |
| 0d. | Article/Tutorial | We will publish a short technical article on the Quantova forum (or a public blog) explaining the methodology — how the fuzzing suite works, what classes of bugs it targets, and how SDK maintainers can integrate it into their CI. |
| 1. | Fuzzing harness core | A Python-based fuzzing orchestrator (`qweb3-fuzz`) that accepts a target module name and a fuzzing profile. Supports parallel execution, seed replay, and crash deduplication via stack-hash bucketing. |
| 2. | qweb3.py fuzz targets | Property-based tests for: key generation (Dilithium/Falcon/SPHINCS+), address derivation, transaction building/signing, RPC call formatting, and serialization round-trips. At least 30 individual fuzz properties. |
| 3. | qweb3.js fuzz targets | Corresponding tests for the JavaScript SDK covering the same surfaces as (2), adapted for JS async patterns. At least 30 individual fuzz properties. |
| 4. | Post-quantum primitive fuzz targets | Targeted mutation fuzzing of cryptographic operations: malformed Dilithium signatures, truncated Falcon key material, boundary-condition SHA3-256 inputs. Designed to detect panic/unwrap paths and incorrect constant-time behavior indicators. |
| 5. | Crash reporter & report generator | Structured output in JSON and Markdown. Each finding includes: severity level, target module, input seed (for reproduction), stack trace (if applicable), and a human-readable description. |
| 6. | CI integration | Pre-configured GitHub Actions workflow that runs the fuzzing suite on push/PR with a 10-minute timeout (quick mode) and a nightly full run. CI exits with code 0 only if no CRITICAL/HIGH findings are present. |

## Future Plans

After the grant, we intend to:

1. **Maintain the harness** — respond to issues and PRs from the Quantova community,
   update fuzz targets as the SDK evolves.
2. **Expand coverage** — add fuzz targets for any new SDK features (bridges, QNS
   lookups, new post-quantum schemes).
3. **Integrate with downstream projects** — work with Quantova SDK maintainers to
   make the fuzzing suite a standard part of the SDK release pipeline.
4. **Publish findings** — publicly document interesting bugs found by the fuzzing
   suite to help the broader blockchain security community learn from Quantova's
   post-quantum approach.

No further grant funding is anticipated for this specific project, though we would be
open to a Level 2 grant for a deeper, multi-SDK fuzzing initiative covering Go and
Rust bindings if the community finds this work valuable.

## Referral / Additional Information

- **Referrer:** (optional) 
- **How did you hear about the Quantova Grants Program?** Quantova.org website /
  GitHub Grants-Program repository.
- **Additional Information:** This is an individual contributor application. We are
  happy to discuss scope adjustments with the grants committee and are available for
  a brief technical call to walk through the fuzzing methodology prior to approval.
