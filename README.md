# Awesome Offline OCR

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> A curated list of **offline / local-first OCR**, bank-statement digitization, and privacy-first document tools.
>
> 精选：**离线 / 本地优先 OCR**、银行流水数字化、以及尽量不把敏感文档上传云端的工具。

**Why this list exists / 为什么做这个列表**

Bank statements, invoices, and IDs are high-sensitivity documents. Many teams want OCR that runs on a laptop or private server — not a black-box upload API. This list tracks projects that help with that workflow.

银行流水、发票、证件等材料敏感。很多场景需要在本机或私有环境跑 OCR，而不是默认上传到第三方。本列表收集这类工具与相关资源。

## Contents

- [Bank statement & finance docs](#bank-statement--finance-docs)
- [General offline / on-device OCR](#general-offline--on-device-ocr)
- [PDF & document pipelines](#pdf--document-pipelines)
- [Models & engines](#models--engines)
- [Datasets & evaluation](#datasets--evaluation)
- [Related awesome lists](#related-awesome-lists)
- [Contributing](#contributing)

## Bank statement & finance docs

Tools aimed at statements, ledgers, or financial PDFs → structured data.

- [BankOCR](https://github.com/yuezhengb/bankocr) - Offline bank-statement PDF → structured Excel, searchable/comparison PDFs, and a human review queue. CPU-first; no cloud upload. 离线银行流水 PDF 数字化。

## General offline / on-device OCR

Engines and apps that can run locally (may still optionally call cloud features — prefer projects with a real offline path).

- [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR) - Widely used OCR toolkit with on-device / local inference options.
- [RapidOCR](https://github.com/RapidAI/RapidOCR) - Lightweight OCR wrappers commonly used with ONNX Runtime on CPU.
- [EasyOCR](https://github.com/JaidedAI/EasyOCR) - Ready-to-use OCR with local model download and inference.
- [Tesseract](https://github.com/tesseract-ocr/tesseract) - Classic open-source OCR engine; strong offline baseline.
- [ocrmypdf](https://github.com/ocrmypdf/OCRmyPDF) - Add an OCR text layer to PDFs locally (often paired with Tesseract).

## PDF & document pipelines

- [PyMuPDF](https://github.com/pymupdf/PyMuPDF) - Fast PDF rendering/extraction; common building block for statement pipelines.
- [pdf2image](https://github.com/Belval/pdf2image) - PDF page → image conversion helper for OCR pipelines.
- [img2table](https://github.com/xavctn/img2table) - Table extraction from images/PDFs; useful after OCR preprocessing.

## Models & engines

- [ONNX Runtime](https://github.com/microsoft/onnxruntime) - Cross-platform inference runtime; common for CPU-first OCR deployments.
- [OpenCV](https://github.com/opencv/opencv) - Image preprocessing (deskew, denoise, thresholding) for OCR pipelines.

## Datasets & evaluation

- Add carefully licensed public datasets here. Do **not** publish real customer bank statements.

_Contributions welcome — open a PR with license notes._

## Related awesome lists

- [awesome-ocr](https://github.com/kba/awesome-ocr) - Broader OCR resource list.
- [sindresorhus/awesome](https://github.com/sindresorhus/awesome) - The Awesome manifesto and guidelines.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). PRs that add a clear offline/local path and a one-line honest description are preferred.

## License

[MIT](LICENSE)

---

Maintained alongside [BankOCR](https://github.com/yuezhengb/bankocr). Last starter publish: 2026-09-21.
