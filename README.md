# Docling (docling)

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
