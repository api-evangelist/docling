# Docling

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Docling is an open-source toolkit for parsing diverse document formats — PDF, DOCX, PPTX, XLSX, HTML, images, audio, LaTeX, plain text — into a unified, lossless DoclingDocument representation that downstream generative AI and RAG systems can consume directly. It pairs IBM Research's DocLayout and TableFormer models with the GraniteDocling visual language model and pluggable OCR engines, runs entirely locally for air-gapped use, and ships as a Python library and CLI, a FastAPI HTTP service (docling-serve), an MCP server (docling-mcp), and a Kubernetes operator. Originally created by IBM Research Zurich; now hosted by the LF AI and Data Foundation under the MIT license.

**Areas:** Documents · Parsing · PDF · OCR · Layout · Tables · RAG · LLM · Open Source · IBM Research · LF AI and Data · MCP

## Docling on APIs.io

Everything profiled for Docling is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/docling/](https://apis.io/providers/docling/)** — or go straight to one of the APIs or properties below.

### APIs (18)

- [Docling MCP Server](https://apis.io/apis/docling/docling-mcp-server/) — Model Context Protocol server that exposes Docling document parsing as MCP tools so Claude, Cursor, Gemini, and other MCP-aware agents can convert PDFs,…
- [Docling Core Types](https://apis.io/apis/docling/docling-core/) — Canonical `DoclingDocument` data model and serialization primitives — text, tables, pictures, layout, hierarchy, bounding boxes, provenance — shared by the…
- [Docling Parse PDF Extractor](https://apis.io/apis/docling/docling-parse/) — Native C++ PDF parsing engine used by Docling to extract text with precise coordinates from programmatic (non-scanned) PDF files. Distributed as a Python…
- [Docling IBM Models](https://apis.io/apis/docling/docling-ibm-models/) — Open-weight IBM Research models that power Docling's understanding pipeline — DocLayout (layout detection and reading order), TableFormer (table structure),…
- [Docling Eval](https://apis.io/apis/docling/docling-eval/) — End-to-end evaluation framework for document parsing models and services. Provides standard datasets and metrics for layout, tables, OCR, and reading-order…
- [Docling Synthetic Data Generation](https://apis.io/apis/docling/docling-sdg/) — Tools for synthesizing labeled document data from real corpora — useful for fine-tuning layout, table, and reading-order models, and for stress-testing…
- [Docling Graph](https://apis.io/apis/docling/docling-graph/) — Transform unstructured documents — once normalized to `DoclingDocument` — into validated, rich, queryable knowledge graphs. Intended for GraphRAG and…
- [Docling Agent](https://apis.io/apis/docling/docling-agent/) — Reference agent that reads, writes, and edits documents using Docling as the IO layer. Demonstrates how Docling output composes with tool-using LLMs to…
- [Docling Kubernetes Operator](https://apis.io/apis/docling/docling-operator/) — Go-based Kubernetes operator that deploys and manages Docling Serve workloads — model cache PVCs, GPU/CPU pools, RQ workers, replica sets with sticky…
- [Docling Java Bindings](https://apis.io/apis/docling/docling-java/) — A Java API for Docling that lets JVM applications call into the Docling pipeline. Complementary to `docling4j`, which targets Java-native document…
- [Docling4j](https://apis.io/apis/docling/docling4j/) — Brings Docling document understanding into Java projects with idiomatic Java APIs over the Docling serialization format.
- [Docling TypeScript](https://apis.io/apis/docling/docling-ts/) — TypeScript/JavaScript types and helpers for consuming Docling output (DoclingDocument JSON, DocTags) in Node.js and browser applications.
- [Docling LangChain Integration](https://apis.io/apis/docling/docling-langchain/) — First-party LangChain document loader and chunker for Docling. Drops Docling output directly into LangChain retrieval pipelines.
- [Docling Jobkit](https://apis.io/apis/docling/docling-jobkit/) — Shared job-runner primitives used by Docling Serve and the Docling Operator to dispatch conversion work across RQ workers and Ray.
- [Docling Async API](https://apis.io/apis/docling/docling-async-api/) — Asynchronous conversion submission.
- [Docling Convert API](https://apis.io/apis/docling/docling-convert-api/) — Document conversion operations.
- [Docling System API](https://apis.io/apis/docling/docling-system-api/) — Health and metadata.
- [Docling Tasks API](https://apis.io/apis/docling/docling-tasks-api/) — Task status, results, and streaming.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Docling Agentic Access](https://apis.io/agentic-access/docling/docling-agentic-access/)

#### JSON Schema (2)

The data models the API reads and writes.

- [DoclingConvertRequest](https://apis.io/schemas/docling/docling-convert-request/)
- [DoclingDocument](https://apis.io/schemas/docling/docling-document/)

#### JSON Structure (1)

Data models expressed in JSON Structure.

- [Docling Document Structure](https://apis.io/json-structure/docling/docling-document-structure/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Docling Context](https://apis.io/jsonld/docling/docling-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Docling Vocabulary](https://apis.io/vocabularies/docling/docling-vocabulary/)

#### Examples (3)

Example requests and responses.

- [Docling Cli Convert Example](https://apis.io/examples/docling/docling-cli-convert-example/)
- [Docling Serve Convert Source Async Example](https://apis.io/examples/docling/docling-serve-convert-source-async-example/)
- [Docling Serve Convert Source Example](https://apis.io/examples/docling/docling-serve-convert-source-example/)

#### Collections (6)

Postman and Open Collection request collections.

- [Docling CLI as REST Async API](https://apis.io/collections/docling/open-docling-async-api/)
- [Docling CLI as REST](https://apis.io/collections/docling/open-docling-cli/)
- [Docling CLI as REST Async Convert API](https://apis.io/collections/docling/open-docling-convert-api/)
- [Docling Serve REST API](https://apis.io/collections/docling/open-docling-serve/)
- [Docling CLI as REST Async System API](https://apis.io/collections/docling/open-docling-system-api/)
- [Docling CLI as REST Async Tasks API](https://apis.io/collections/docling/open-docling-tasks-api/)

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [Docling — jsonschema rules](https://apis.io/rules/docling/docling-jsonschema-spectral-rules/)
- [Docling API Rules](https://apis.io/rules/docling/docling-rules/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://docling-project.github.io)
- [Documentation](https://docling-project.github.io/docling/)
- [Getting started](https://docling-project.github.io/docling/getting_started/quickstart/)
- [Changelog](https://github.com/docling-project/docling/blob/main/CHANGELOG.md)
- [Blog](https://research.ibm.com/blog/docling-generative-AI)
- [GitHub](https://github.com/docling-project)

## API Evangelist rating

**Kin Score 38.0** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 57.1 |
| Contract quality | 54.3 |
| Contract governance | 13.6 |
| Operational transparency | 28.9 |
| Developer ergonomics | 61.9 |
| Access clarity | 0.0 |

**Agent readiness 23.0** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | — |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 10.0** — AI & Biometrics

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/docling/](https://apis.io/providers/docling/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Docling: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/docling/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
