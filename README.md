# Docling (docling)

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

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/docling/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/docling/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** Open Source

## Tags

- Documents
- Parsing
- PDF
- OCR
- Layout
- Tables
- RAG
- LLM
- Open Source
- IBM Research
- LF AI and Data
- MCP
- Knowledge Graph
- Generative AI

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### Docling Python Library

The core Docling Python library and `docling` CLI. Parses PDFs, DOCX, PPTX, XLSX, HTML, images (PNG/TIFF/JPEG), audio (WAV/MP3), WebVTT, LaTeX, and plain text into a unified `DoclingDocument` representation that can be exported to Markdown, HTML, lossless JSON, DocTags, and WebVTT. Implements advanced PDF understanding — page layout, reading order, table structure (TableFormer), code and formula recognition, picture classification — plus OCR (EasyOCR, Tesseract, RapidOCR, Mac OCR) and the GraniteDocling visual language model pipeline. Runs locally for air-gapped and sensitive-data use.

- **Human URL:** [https://docling-project.github.io/docling/](https://docling-project.github.io/docling/)

#### Tags

- Documents
- Parsing
- Python
- SDK
- PDF
- OCR
- LLM
- RAG

#### Properties

- [Documentation](https://docling-project.github.io/docling/)
- [Getting Started](https://docling-project.github.io/docling/getting_started/quickstart/)
- [Source Code](https://github.com/docling-project/docling)
- [SDK](https://pypi.org/project/docling/)
- [OpenAPI](openapi/docling-cli-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling Serve REST API

Docling Serve exposes the Docling pipeline as an HTTP service. Synchronous endpoints `POST /v1/convert/source` and `POST /v1/convert/file` accept URL- or upload-sourced documents and return converted JSON, Markdown, HTML, or a zipped bundle. Asynchronous variants (`/v1/convert/source/async`, `/v1/convert/file/async`) return a task handle that can be polled at `/v1/status/poll/{task_id}`, streamed via WebSocket `/v1/status/ws/{task_id}`, and retrieved at `/v1/result/{task_id}`. Container images ship CPU, CUDA 12.8/13.0, and AMD ROCm 6.3 variants; Kubernetes deployment is supported via the Docling Operator.

- **Human URL:** [https://github.com/docling-project/docling-serve](https://github.com/docling-project/docling-serve)

#### Tags

- Documents
- Parsing
- REST
- PDF
- OCR
- Async
- WebSocket

#### Properties

- [Documentation](https://github.com/docling-project/docling-serve)
- [Documentation](https://raw.githubusercontent.com/docling-project/docling-serve/main/docs/usage.md)
- [Source Code](https://github.com/docling-project/docling-serve)
- [OpenAPI](openapi/docling-serve-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/docling-document-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/docling-convert-request-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/docling-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Docling MCP Server

Model Context Protocol server that exposes Docling document parsing as MCP tools so Claude, Cursor, Gemini, and other MCP-aware agents can convert PDFs, Office files, and images into structured `DoclingDocument` output without bespoke integration code.

- **Human URL:** [https://github.com/docling-project/docling-mcp](https://github.com/docling-project/docling-mcp)

#### Tags

- MCP
- Agents
- Documents
- Parsing

#### Properties

- [Documentation](https://github.com/docling-project/docling-mcp)
- [Source Code](https://github.com/docling-project/docling-mcp)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling Core Types

Canonical `DoclingDocument` data model and serialization primitives — text, tables, pictures, layout, hierarchy, bounding boxes, provenance — shared by the Docling library, Docling Serve, the Java port, and the TypeScript bindings.

- **Human URL:** [https://github.com/docling-project/docling-core](https://github.com/docling-project/docling-core)

#### Tags

- Documents
- Schema
- Python
- SDK

#### Properties

- [Documentation](https://github.com/docling-project/docling-core)
- [Source Code](https://github.com/docling-project/docling-core)
- [SDK](https://pypi.org/project/docling-core/)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling Parse PDF Extractor

Native C++ PDF parsing engine used by Docling to extract text with precise coordinates from programmatic (non-scanned) PDF files. Distributed as a Python extension.

- **Human URL:** [https://github.com/docling-project/docling-parse](https://github.com/docling-project/docling-parse)

#### Tags

- PDF
- Parsing
- C++

#### Properties

- [Documentation](https://github.com/docling-project/docling-parse)
- [Source Code](https://github.com/docling-project/docling-parse)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling IBM Models

Open-weight IBM Research models that power Docling's understanding pipeline — DocLayout (layout detection and reading order), TableFormer (table structure), code- and formula-recognition heads, picture classifier, and GraniteDocling-258M VLM. Distributed through Hugging Face.

- **Human URL:** [https://github.com/docling-project/docling-ibm-models](https://github.com/docling-project/docling-ibm-models)

#### Tags

- AI
- Documents
- Layout
- TableFormer
- VLM

#### Properties

- [Documentation](https://github.com/docling-project/docling-ibm-models)
- [Source Code](https://github.com/docling-project/docling-ibm-models)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling Eval

End-to-end evaluation framework for document parsing models and services. Provides standard datasets and metrics for layout, tables, OCR, and reading-order quality so teams can benchmark Docling — and competing parsers — apples to apples.

- **Human URL:** [https://github.com/docling-project/docling-eval](https://github.com/docling-project/docling-eval)

#### Tags

- Evaluation
- Documents
- Benchmarks

#### Properties

- [Documentation](https://github.com/docling-project/docling-eval)
- [Source Code](https://github.com/docling-project/docling-eval)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling Synthetic Data Generation

Tools for synthesizing labeled document data from real corpora — useful for fine-tuning layout, table, and reading-order models, and for stress-testing downstream RAG pipelines.

- **Human URL:** [https://github.com/docling-project/docling-sdg](https://github.com/docling-project/docling-sdg)

#### Tags

- Synthetic Data
- Training
- Documents

#### Properties

- [Documentation](https://github.com/docling-project/docling-sdg)
- [Source Code](https://github.com/docling-project/docling-sdg)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling Graph

Transform unstructured documents — once normalized to `DoclingDocument` — into validated, rich, queryable knowledge graphs. Intended for GraphRAG and entity-extraction workflows on top of Docling output.

- **Human URL:** [https://github.com/docling-project/docling-graph](https://github.com/docling-project/docling-graph)

#### Tags

- Knowledge Graph
- RAG
- Documents

#### Properties

- [Documentation](https://github.com/docling-project/docling-graph)
- [Source Code](https://github.com/docling-project/docling-graph)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling Agent

Reference agent that reads, writes, and edits documents using Docling as the IO layer. Demonstrates how Docling output composes with tool-using LLMs to produce structured edits.

- **Human URL:** [https://github.com/docling-project/docling-agent](https://github.com/docling-project/docling-agent)

#### Tags

- Agents
- Documents
- LLM

#### Properties

- [Documentation](https://github.com/docling-project/docling-agent)
- [Source Code](https://github.com/docling-project/docling-agent)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling Kubernetes Operator

Go-based Kubernetes operator that deploys and manages Docling Serve workloads — model cache PVCs, GPU/CPU pools, RQ workers, replica sets with sticky sessions, OAuth — from a single CR.

- **Human URL:** [https://github.com/docling-project/docling-operator](https://github.com/docling-project/docling-operator)

#### Tags

- Kubernetes
- Operator
- Documents

#### Properties

- [Documentation](https://github.com/docling-project/docling-operator)
- [Source Code](https://github.com/docling-project/docling-operator)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling Java Bindings

A Java API for Docling that lets JVM applications call into the Docling pipeline. Complementary to `docling4j`, which targets Java-native document understanding integrations.

- **Human URL:** [https://github.com/docling-project/docling-java](https://github.com/docling-project/docling-java)

#### Tags

- Java
- SDK

#### Properties

- [Documentation](https://github.com/docling-project/docling-java)
- [Source Code](https://github.com/docling-project/docling-java)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling4j

Brings Docling document understanding into Java projects with idiomatic Java APIs over the Docling serialization format.

- **Human URL:** [https://github.com/docling-project/docling4j](https://github.com/docling-project/docling4j)

#### Tags

- Java
- SDK

#### Properties

- [Documentation](https://github.com/docling-project/docling4j)
- [Source Code](https://github.com/docling-project/docling4j)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling TypeScript

TypeScript/JavaScript types and helpers for consuming Docling output (DoclingDocument JSON, DocTags) in Node.js and browser applications.

- **Human URL:** [https://github.com/docling-project/docling-ts](https://github.com/docling-project/docling-ts)

#### Tags

- TypeScript
- JavaScript
- SDK

#### Properties

- [Documentation](https://github.com/docling-project/docling-ts)
- [Source Code](https://github.com/docling-project/docling-ts)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling LangChain Integration

First-party LangChain document loader and chunker for Docling. Drops Docling output directly into LangChain retrieval pipelines.

- **Human URL:** [https://github.com/docling-project/docling-langchain](https://github.com/docling-project/docling-langchain)

#### Tags

- LangChain
- RAG
- Documents

#### Properties

- [Documentation](https://github.com/docling-project/docling-langchain)
- [Source Code](https://github.com/docling-project/docling-langchain)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Docling Jobkit

Shared job-runner primitives used by Docling Serve and the Docling Operator to dispatch conversion work across RQ workers and Ray.

- **Human URL:** [https://github.com/docling-project/docling-jobkit](https://github.com/docling-project/docling-jobkit)

#### Tags

- Jobs
- Async
- Documents

#### Properties

- [Documentation](https://github.com/docling-project/docling-jobkit)
- [Source Code](https://github.com/docling-project/docling-jobkit)
- [Postman Collection](collections/docling-cli.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-cli.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/docling-serve.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/docling-serve.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://docling-project.github.io/docling/)
- [Documentation](https://docling-project.github.io/docling/)
- [Getting Started](https://docling-project.github.io/docling/getting_started/quickstart/)
- [Source Code](https://github.com/docling-project/docling)
- [GitHub Organization](https://github.com/docling-project)
- [License](https://github.com/docling-project/docling/blob/main/LICENSE)
- [SDK](https://pypi.org/project/docling/)
- [SDK](https://pypi.org/project/docling-core/)
- [SDK](https://pypi.org/project/docling-serve/)
- [SDK](https://github.com/docling-project/docling-java)
- [SDK](https://github.com/docling-project/docling4j)
- [SDK](https://github.com/docling-project/docling-ts)
- [C L I](https://docling-project.github.io/docling/reference/cli/)
- [Release Notes](https://github.com/docling-project/docling/releases)
- [Changelog](https://github.com/docling-project/docling/blob/main/CHANGELOG.md)
- [Issues](https://github.com/docling-project/docling/issues)
- [Discussions](https://github.com/docling-project/docling/discussions)
- [Contribution Guide](https://github.com/docling-project/docling/blob/main/CONTRIBUTING.md)
- [Code Of Conduct](https://github.com/docling-project/docling/blob/main/CODE_OF_CONDUCT.md)
- [Governance](https://lfaidata.foundation/projects/docling/)
- [Foundation](https://lfaidata.foundation/)
- [Models](https://huggingface.co/ds4sd)
- [Models](https://huggingface.co/ibm-granite/granite-docling-258M)
- [Blog](https://research.ibm.com/blog/docling-generative-AI)
- [Academic Paper](https://arxiv.org/abs/2408.09869)
- [Integration](https://docling-project.github.io/docling/integrations/langchain/)
- [Integration](https://docling-project.github.io/docling/integrations/llamaindex/)
- [Integration](https://docling-project.github.io/docling/integrations/haystack/)
- [Integration](https://docling-project.github.io/docling/integrations/crewai/)
- [Integration](https://docling-project.github.io/docling/integrations/txtai/)
- [Integration](https://docling-project.github.io/docling/integrations/spacy/)
- [Integration](https://docling-project.github.io/docling/integrations/apify/)
- [Integration](https://docling-project.github.io/docling/integrations/nvidia/)
- [Integration](https://docling-project.github.io/docling/integrations/instructlab/)
- [Integration](https://docling-project.github.io/docling/integrations/bee/)
- [Integration](https://docling-project.github.io/docling/integrations/weaviate/)
- [Integration](https://docling-project.github.io/docling/integrations/qdrant/)
- [Integration](https://docling-project.github.io/docling/integrations/milvus/)
- [Integration](https://docling-project.github.io/docling/integrations/opensearch/)
- [Container Image](https://quay.io/repository/docling-project/docling-serve)
- [Container Image](https://github.com/docling-project/docling-serve/pkgs/container/docling-serve)
- [Kubernetes Operator](https://github.com/docling-project/docling-operator)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
