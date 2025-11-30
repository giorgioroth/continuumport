ContinuumPort — CP-Core v1.0 (Public Release)

Version: CP-Core v1.0
Status: Final (Public Release)

ContinuumPort is an open semantic portability layer designed to preserve and transfer non-sensitive conversational context across AI sessions, models, platforms, and devices.

This repository contains the open-source, forever-free components of ContinuumPort under an MIT License.
The proprietary ContinuumPort-Regen Engine is not included here.

Why CP-Core Matters

Modern AI systems lack persistent, portable context. A context created in one model, session, device, or platform cannot be safely transferred to another.

CP-Core introduces a minimal, model-agnostic semantic container engineered for:

cross-model interoperability

cross-session continuity

vendor-neutral AI context transfer

safe portability without personal or sensitive data

bridging local and cloud AI ecosystems

This compact public core forms the foundation of a broader continuity standard.

Open-Source Components (MIT License — forever free)

This repository provides the complete CP-Core v1.0 specification and minimal reference implementations:

JavaScript → impl/js/encode-decode.js

Python → impl/python/encode_decode.py

Rust → impl/rust/src/lib.rs

These implementations contain only Base64 serialization logic — no regeneration, no inference, no prompt reconstruction.

Proprietary Component (closed-source)
ContinuumPort-Regen Engine

The private component capable of reconstructing a rich, faithful prompt from a CP-Core token, achieving 97%+ semantic fidelity across models such as Grok, Claude, Llama-3.1, Gemini, Mistral, Qwen, and others.

Available via licensed API or on-premise installation

Commercial inquiries: continuumport@gmail.com

The Regen Engine is not included in this repository.

Quick Start (public components only)
import { encodeCP } from "./impl/js/encode-decode.js";

const token = encodeCP({
  v: 1,
  lang: "en",
  summary: "We want continuity between local and cloud AI models.",
  entities: ["Ollama", "Grok", "Claude"],
  progress: "Discussion about token format and IP protection.",
  memoryHints: { taskStage: 5 }
});

console.log(token);
// → CP1:eyJ2IjoxLCJsYW5nIjoiZW4iLCJzdW1tYXJ5IjoiV2Ugd2FudCBj...

Folder Structure
impl/
  js/encode-decode.js
  python/encode_decode.py
  rust/src/lib.rs

examples/
  quickstart_js.md

Each file is a minimal, readable reference to the CP-Core format.

Status

CP-Core v1.0: finalized
Regen Engine: private, in active development
Licensing: open for enterprise early access

MIT License © 2025
