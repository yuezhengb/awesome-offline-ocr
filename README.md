# Awesome Offline OCR

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> A curated list of **offline / local-first OCR**, document parsing, bank-statement digitization, and privacy-first PDF tools.
>
> 精选：**离线 / 本地优先 OCR**、文档解析、银行流水数字化，以及尽量不把敏感文档默认上传云端的工具。

**Why this list / 为什么做这个列表**

Bank statements, invoices, and IDs are high-sensitivity. Many teams need OCR that runs on a laptop or private server — not only a black-box upload API. This list focuses on projects with a real local path (CPU/GPU on your machine or self-hosted).

银行流水、发票、证件等材料敏感。很多场景需要在本机或私有环境跑 OCR。本列表优先收录有真实本地/可自托管路径的项目。

> Entries are curated with short honest descriptions. Star counts change; check each repo for the latest. Do **not** commit real customer statements here.

## Contents

- [Bank statement & finance docs](#bank-statement--finance-docs)
- [Desktop offline OCR apps](#desktop-offline-ocr-apps)
- [Document parsing (PDF → Markdown/JSON)](#document-parsing-pdf--markdownjson)
- [General OCR toolkits](#general-ocr-toolkits)
- [Lightweight / mobile / edge OCR](#lightweight--mobile--edge-ocr)
- [Math, LaTeX & specialized OCR](#math-latex--specialized-ocr)
- [PDF utilities for OCR pipelines](#pdf-utilities-for-ocr-pipelines)
- [Inference runtimes & preprocessing](#inference-runtimes--preprocessing)
- [Datasets, papers & resource lists](#datasets-papers--resource-lists)
- [Related awesome lists](#related-awesome-lists)
- [Contributing](#contributing)

## Bank statement & finance docs

Tools aimed at statements, ledgers, or financial PDFs → structured data (tables, Excel, review workflows).

- [BankOCR](https://github.com/yuezhengb/bankocr) - Offline bank-statement PDF → structured Excel, searchable/comparison PDFs, and a human review queue. CPU-first; designed not to upload statements. 离线银行流水 PDF 数字化（本列表维护者项目）。
- [statement-synth](https://github.com/yuezhengb/statement-synth) - Generate **synthetic** bank-statement PDFs for OCR testing (clearly labeled fake data, no real PII). 假流水 PDF 生成器，方便模板贡献与 CI。
- [banksheet](https://github.com/tio-ze-rj/banksheet) - Parse supported bank and credit-card statement PDFs locally into CSV, Excel, or JSON; no external APIs or cloud. Currently includes Brazilian, Canadian, and US card parsers.
- [Camelot](https://github.com/camelot-dev/camelot) - Extract tables from PDFs into pandas/CSV; useful when statements are text-based PDFs (not a neural OCR engine by itself).
- [tabula-java](https://github.com/tabulapdf/tabula-java) - Classic PDF table extraction; often paired with a GUI ([Tabula](https://github.com/tabulapdf/tabula)).
- [Excalibur](https://github.com/camelot-dev/excalibur) - Web UI for Camelot table extraction — helpful for iterating on statement layouts locally.

## Desktop offline OCR apps

End-user apps that emphasize offline recognition (screenshots, batches, PDFs).

- [Umi-OCR](https://github.com/hiroi-sora/Umi-OCR) - Popular free offline OCR desktop app (batch images/PDF, watermark/header filters, multi-language). 开源免费离线 OCR 软件。
- [eSearch](https://github.com/xushengfeng/eSearch) - Cross-platform screenshot + offline OCR + search/translate utilities (Windows/Linux/macOS).
- [tr (myhub/tr)](https://github.com/myhub/tr) - Offline Chinese text detection + recognition SDK oriented to local use.

## Document parsing (PDF → Markdown/JSON)

Layout-aware parsers for complex PDFs (papers, reports, multi-column docs). Many support local inference; check each project’s GPU/CPU notes and whether any cloud call is optional.

- [MinerU](https://github.com/opendatalab/MinerU) - PDF/Office → LLM-ready Markdown/JSON with layout analysis; widely used for local document pipelines.
- [Docling](https://github.com/docling-project/docling) - Document conversion toolkit (PDF and office formats) aimed at local/gen-AI prep workflows.
- [Surya](https://github.com/datalab-to/surya) - OCR + layout + reading order + tables across many languages; local model inference.
- [Chandra](https://github.com/datalab-to/chandra) - OCR focused on complex tables, forms, and handwriting with layout (from the Surya team).
- [GOT-OCR2.0](https://github.com/Ucas-HaoranWei/GOT-OCR2.0) - End-to-end “OCR 2.0” research/code for unified document OCR.
- [dots.ocr](https://github.com/studio-dots-ai/dots.ocr) - Multilingual document layout parsing with a vision-language model approach.
- [DeepSeek-OCR](https://github.com/deepseek-ai/DeepSeek-OCR) - Open OCR / optical compression research codebase from DeepSeek (self-host / local research use).
- [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR) - Full OCR + document structure toolkit (PP-OCR / PP-Structure); strong local Chinese/English support and PDF pipelines.

## General OCR toolkits

Libraries you embed in your own pipeline.

- [Tesseract](https://github.com/tesseract-ocr/tesseract) - Classic open-source OCR engine; the default offline baseline for many systems.
- [EasyOCR](https://github.com/JaidedAI/EasyOCR) - Ready-to-use multi-language OCR with local model download + inference.
- [RapidOCR](https://github.com/RapidAI/RapidOCR) - Multi-backend OCR toolkit centered on ONNX Runtime / OpenVINO / etc., friendly for CPU deployment.
- [OCRmyPDF](https://github.com/ocrmypdf/OCRmyPDF) - Add a searchable OCR text layer to scanned PDFs locally (commonly with Tesseract).
- [chineseocr_lite](https://github.com/DayBreak-u/chineseocr_lite) - Ultra-light Chinese OCR (~4.7M models) with ncnn/MNN/TNN options for edge devices.

## Lightweight / mobile / edge OCR

- [cnocr](https://github.com/breezedeus/cnocr) - Practical Chinese OCR Python package for local use.
- [NCNN](https://github.com/Tencent/ncnn) - High-performance neural net inference framework for mobile/edge (often paired with lite OCR models).
- [MNN](https://github.com/alibaba/MNN) - Alibaba’s on-device inference engine; used by several lite OCR deployments.
- [react-native-executorch](https://github.com/software-mansion/react-native-executorch) - On-device AI for React Native (includes OCR-related demos/capabilities via ExecuTorch).

## Math, LaTeX & specialized OCR

- [LaTeX-OCR (pix2tex)](https://github.com/lukas-blecher/LaTeX-OCR) - Convert images of equations to LaTeX.
- [MixTeX-Latex-OCR](https://github.com/RQLuo/MixTeX-Latex-OCR) - Multimodal LaTeX / Zh-En / table OCR with local CPU-oriented Windows offline inference.
- [ddddocr](https://github.com/sml2h3/ddddocr) - Lightweight captcha-oriented OCR (specialized; not for bank statements).

## PDF utilities for OCR pipelines

Building blocks frequently used before/after OCR.

- [PyMuPDF](https://github.com/pymupdf/PyMuPDF) - Fast PDF render/extract; common in statement digitization pipelines.
- [pdf2image](https://github.com/Belval/pdf2image) - PDF pages → images for OCR.
- [img2table](https://github.com/xavctn/img2table) - Table extraction from images/PDFs after preprocessing.
- [pdfplumber](https://github.com/jsvine/pdfplumber) - Detailed PDF text/table inspection for native (non-scan) PDFs.
- [pypdf](https://github.com/py-pdf/pypdf) - Pure-Python PDF toolkit for merge/split/metadata in pipelines.

## Inference runtimes & preprocessing

- [ONNX Runtime](https://github.com/microsoft/onnxruntime) - Cross-platform inference; common for CPU-first OCR deployments.
- [OpenCV](https://github.com/opencv/opencv) - Deskew, denoise, thresholding, and other preprocessing for OCR.
- [OpenVINO](https://github.com/openvinotoolkit/openvino) - Intel-oriented optimized inference; used by some RapidOCR backends.

## Datasets, papers & resource lists

- Prefer carefully licensed public datasets. **Never** publish real customer bank statements or account numbers.
- [statement-synth](https://github.com/yuezhengb/statement-synth) - Synthetic statement PDFs when you need shareable fixtures without PII.
- [image-text-localization-recognition](https://github.com/whitelok/image-text-localization-recognition) - Paper/resource collection for scene text detection & recognition (archived upstream; still a useful bibliography).
- Contributions with license notes welcome via PR.

## Related awesome lists

- [awesome-ocr](https://github.com/kba/awesome-ocr) - Broader OCR resources.
- [sindresorhus/awesome](https://github.com/sindresorhus/awesome) - Awesome list guidelines.
- [funNLP](https://github.com/fighting41love/funNLP) - Large Chinese NLP resource dump (includes OCR-related pointers among many topics).

## How to use this list with BankOCR

1. Generate a fake statement with [statement-synth](https://github.com/yuezhengb/statement-synth) (no real PII).
2. Pick an engine (e.g. RapidOCR / PaddleOCR / Tesseract) for raw text.
3. Use PDF tools (PyMuPDF, OCRmyPDF) for render / searchable PDF.
4. For **bank statements specifically**, see [BankOCR](https://github.com/yuezhengb/bankocr) for validation, Excel export, and review UX — and contribute templates via [good first issues](https://github.com/yuezhengb/bankocr/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Prefer PRs that:

- Link a public source repo
- State the offline / self-hosted path clearly
- Avoid upload-only SaaS as the only option
- Keep one honest line of description (no fake benchmarks)

Starter issue: [Add a project to the list](https://github.com/yuezhengb/awesome-offline-ocr/issues/1)

## License

[MIT](LICENSE) — list contents; linked projects keep their own licenses.

---

Maintained alongside [BankOCR](https://github.com/yuezhengb/bankocr) and [statement-synth](https://github.com/yuezhengb/statement-synth).  
**Last reviewed:** 2026-09-21 — added statement-synth to the finance and fixtures sections.
