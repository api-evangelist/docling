# Docling (docling)

Docling is an open-source toolkit for parsing diverse document formats — PDF, DOCX, PPTX, XLSX, HTML, images, audio, LaTeX, plain text — into a unified, lossless `DoclingDocument` representation that downstream generative AI and RAG systems can consume directly. It pairs IBM Research's DocLayout and TableFormer models with the GraniteDocling visual language model and pluggable OCR engines, runs entirely locally for air-gapped use, and ships as a Python library and CLI, a FastAPI HTTP service (`docling-serve`), an MCP server (`docling-mcp`), and a Kubernetes operator. Originally created by IBM Research Zurich; now hosted by the LF AI & Data Foundation under the MIT license.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/docling/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=opensource-api-evangelist&utm_content=repo)

## Tags

- Documents, Parsing, PDF, OCR, Layout, Tables, RAG, LLM, Open Source, IBM Research, LF AI and Data, MCP, Knowledge Graph, Generative AI

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## At a Glance

| Item | Value |
|---|---|
| License | MIT |
| Foundation | LF AI & Data Foundation |
| Origin | IBM Research Zurich — AI for Knowledge team |
| GitHub Org | [docling-project](https://github.com/docling-project) |
| Primary repo | [docling-project/docling](https://github.com/docling-project/docling) (~60k stars) |
| Python | `pip install docling` (Python 3.10+) |
| CLI | `docling <source> [flags]` |
| HTTP service | [docling-serve](https://github.com/docling-project/docling-serve) — sync, async, WebSocket |
| MCP server | [docling-mcp](https://github.com/docling-project/docling-mcp) |
| Kubernetes | [docling-operator](https://github.com/docling-project/docling-operator) |
| Bindings | Python, Java (`docling-java`, `docling4j`), TypeScript (`docling-ts`), Swift (`docling-snap`) |
| Default VLM | [GraniteDocling-258M](https://huggingface.co/ibm-granite/granite-docling-258M) |

## APIs

### Docling Python Library
Core Python library and `docling` CLI. Converts PDFs, Office docs, HTML, images, audio, LaTeX, and plain text into `DoclingDocument`; exports to Markdown, HTML, lossless JSON, DocTags, and WebVTT. Implements page layout, reading order, TableFormer table structure, code/formula recognition, picture classification, OCR, and the GraniteDocling VLM pipeline. Runs locally for air-gapped use.

**Docs:** [docling-project.github.io/docling](https://docling-project.github.io/docling/) — [Source](https://github.com/docling-project/docling) — [PyPI](https://pypi.org/project/docling/)

- [OpenAPI — CLI](openapi/docling-cli-openapi.yml)
- [Naftiko Capability — CLI Convert](capabilities/docling-cli-convert.yaml)

### Docling Serve REST API
HTTP service exposing the Docling pipeline. `POST /v1/convert/source` and `POST /v1/convert/file` are synchronous; `/v1/convert/source/async` and `/v1/convert/file/async` queue work and return a `task_id` that can be polled at `/v1/status/poll/{task_id}`, streamed via WebSocket `/v1/status/ws/{task_id}`, and retrieved at `/v1/result/{task_id}`. CPU, CUDA 12.8/13.0, and AMD ROCm 6.3 container variants ship out of the box.

**Docs:** [docling-serve usage](https://github.com/docling-project/docling-serve/blob/main/docs/usage.md) — [Source](https://github.com/docling-project/docling-serve)

- [OpenAPI](openapi/docling-serve-openapi.yml)
- [JSON Schema — DoclingDocument](json-schema/docling-document-schema.json)
- [JSON Schema — Convert Request](json-schema/docling-convert-request-schema.json)
- [JSON-LD Context](json-ld/docling-context.jsonld)
- [Naftiko Capability — Convert](capabilities/docling-serve-convert.yaml)
- [Naftiko Capability — Tasks](capabilities/docling-serve-tasks.yaml)

### Docling MCP Server
MCP server (`docling-mcp`) that exposes Docling parsing as agent tools for Claude, Cursor, Gemini, and any MCP-aware client. Lets agents convert PDFs, Office files, and images into `DoclingDocument` without bespoke integration code.

**Docs / Source:** [docling-project/docling-mcp](https://github.com/docling-project/docling-mcp)

### Docling Core Types
Canonical `DoclingDocument` data model and serialization primitives shared by the Docling library, Docling Serve, and all language bindings.

**Source:** [docling-project/docling-core](https://github.com/docling-project/docling-core) — [PyPI](https://pypi.org/project/docling-core/)

### Docling Parse PDF Extractor
Native C++ engine that extracts text with precise coordinates from programmatic PDFs. Distributed as a Python extension.

**Source:** [docling-project/docling-parse](https://github.com/docling-project/docling-parse)

### Docling IBM Models
Open-weight IBM Research models that power Docling: DocLayout, TableFormer, code/formula heads, picture classifier, and GraniteDocling-258M. Distributed through Hugging Face.

**Source:** [docling-project/docling-ibm-models](https://github.com/docling-project/docling-ibm-models)

### Docling Eval
End-to-end evaluation framework for document parsing models and services. Standard datasets and metrics for layout, tables, OCR, and reading order.

**Source:** [docling-project/docling-eval](https://github.com/docling-project/docling-eval)

### Docling Synthetic Data Generation
Tools for generating synthetic labeled document data from real corpora for fine-tuning and RAG stress-testing.

**Source:** [docling-project/docling-sdg](https://github.com/docling-project/docling-sdg)

### Docling Graph
Convert unstructured documents (via Docling) into validated, queryable knowledge graphs for GraphRAG.

**Source:** [docling-project/docling-graph](https://github.com/docling-project/docling-graph)

### Docling Agent
Reference agent that reads, writes, and edits documents using Docling as the IO layer.

**Source:** [docling-project/docling-agent](https://github.com/docling-project/docling-agent)

### Docling Kubernetes Operator
Go-based operator that deploys and manages Docling Serve workloads — model-cache PVCs, RQ workers, GPU pools, OAuth, sticky sessions.

**Source:** [docling-project/docling-operator](https://github.com/docling-project/docling-operator)

### Docling Java Bindings
JVM API for Docling.

**Source:** [docling-project/docling-java](https://github.com/docling-project/docling-java)

### Docling4j
Java-native document understanding integrations over Docling.

**Source:** [docling-project/docling4j](https://github.com/docling-project/docling4j)

### Docling TypeScript
TypeScript/JavaScript types and helpers for consuming DoclingDocument JSON and DocTags.

**Source:** [docling-project/docling-ts](https://github.com/docling-project/docling-ts)

### Docling LangChain Integration
First-party LangChain document loader and chunker.

**Source:** [docling-project/docling-langchain](https://github.com/docling-project/docling-langchain)

### Docling Jobkit
Shared job-runner primitives used by Docling Serve and the operator (RQ workers, Ray).

**Source:** [docling-project/docling-jobkit](https://github.com/docling-project/docling-jobkit)

## Common Properties

- [Portal — docling-project.github.io](https://docling-project.github.io/docling/)
- [Documentation](https://docling-project.github.io/docling/)
- [GettingStarted — Quickstart](https://docling-project.github.io/docling/getting_started/quickstart/)
- [SourceCode — Main repo](https://github.com/docling-project/docling)
- [GitHubOrganization — docling-project](https://github.com/docling-project)
- [License — MIT](https://github.com/docling-project/docling/blob/main/LICENSE)
- [SDK — docling (PyPI)](https://pypi.org/project/docling/)
- [SDK — docling-core (PyPI)](https://pypi.org/project/docling-core/)
- [SDK — docling-serve (PyPI)](https://pypi.org/project/docling-serve/)
- [SDK — Java bindings](https://github.com/docling-project/docling-java)
- [SDK — Docling4j](https://github.com/docling-project/docling4j)
- [SDK — TypeScript / JavaScript](https://github.com/docling-project/docling-ts)
- [CLI](https://docling-project.github.io/docling/reference/cli/)
- [ReleaseNotes](https://github.com/docling-project/docling/releases)
- [ChangeLog](https://github.com/docling-project/docling/blob/main/CHANGELOG.md)
- [Issues](https://github.com/docling-project/docling/issues)
- [Discussions](https://github.com/docling-project/docling/discussions)
- [ContributionGuide](https://github.com/docling-project/docling/blob/main/CONTRIBUTING.md)
- [CodeOfConduct](https://github.com/docling-project/docling/blob/main/CODE_OF_CONDUCT.md)
- [Governance — LF AI & Data project page](https://lfaidata.foundation/projects/docling/)
- [Foundation — LF AI & Data](https://lfaidata.foundation/)
- [Models — IBM DS4SD on Hugging Face](https://huggingface.co/ds4sd)
- [Models — GraniteDocling-258M](https://huggingface.co/ibm-granite/granite-docling-258M)
- [Blog — IBM Research](https://research.ibm.com/blog/docling-generative-AI)
- [AcademicPaper — Docling Technical Report (arXiv)](https://arxiv.org/abs/2408.09869)
- [ContainerImage — docling-serve (Quay)](https://quay.io/repository/docling-project/docling-serve)
- [ContainerImage — docling-serve (GHCR)](https://github.com/docling-project/docling-serve/pkgs/container/docling-serve)
- [KubernetesOperator](https://github.com/docling-project/docling-operator)

## Integrations

LangChain, LlamaIndex, Haystack, Crew AI, txtai, spaCy, Apify, NVIDIA NIM / NeMo Retriever, InstructLab, Bee Agent Framework, Weaviate, Qdrant, Milvus, OpenSearch.

## Artifacts

Machine-readable specifications organized by format.

### OpenAPI

- [Docling Serve REST API](openapi/docling-serve-openapi.yml)
- [Docling CLI](openapi/docling-cli-openapi.yml)

### JSON Schema

- [DoclingDocument](json-schema/docling-document-schema.json)
- [Convert Request](json-schema/docling-convert-request-schema.json)

### JSON Structure

- [DoclingDocument Structure](json-structure/docling-document-structure.json)

### JSON-LD

- [Docling Context](json-ld/docling-context.jsonld)

### Capabilities (Naftiko)

- [Docling Serve — Convert](capabilities/docling-serve-convert.yaml)
- [Docling Serve — Tasks](capabilities/docling-serve-tasks.yaml)
- [Docling CLI — Convert](capabilities/docling-cli-convert.yaml)

### Examples

- [docling-serve POST /v1/convert/source](examples/docling-serve-convert-source-example.json)
- [docling-serve async submit → poll → result](examples/docling-serve-convert-source-async-example.json)
- [docling CLI convert](examples/docling-cli-convert-example.json)

### Spectral Rules

- [docling-rules.yml](rules/docling-rules.yml)

### Vocabulary

- [docling-vocabulary.yml](vocabulary/docling-vocabulary.yml)

## Maintainers

**FN:** Kin Lane

**Email:** info@apievangelist.com
