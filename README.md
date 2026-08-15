# Resume & CV (LaTeX Source)

[![Compile & Release Resumes](https://github.com/Adyel/resume-latex/actions/workflows/compile.yml/badge.svg)](https://github.com/Adyel/resume-latex/actions/workflows/compile.yml)
[![Latest Release](https://img.shields.io/github/v/release/Adyel/resume-latex?color=blue&label=latest%20release)](https://github.com/Adyel/resume-latex/releases/latest)

This repository contains the LaTeX source code and automated PDF build pipelines for my Professional Resume and Academic CV.

## 📄 Download Latest PDFs

- **Professional Resume:** [adyel-professional-resume.pdf](https://github.com/Adyel/resume-latex/releases/latest/download/adyel-professional-resume.pdf)
- **Academic CV:** [adyel-academic-resume.pdf](https://github.com/Adyel/resume-latex/releases/latest/download/adyel-academic-resume.pdf)

---

## 📁 Repository Structure

```text
resume-latex/
├── .github/workflows/
│   └── compile.yml                 # Automated PDF compilation & release workflow
├── adyel-professional-resume.tex   # ATS-optimized 1-page professional resume
├── adyel-academic-resume.tex       # Comprehensive multi-page academic curriculum vitae
├── .gitignore
└── README.md
```

---

## 🛠️ Local Compilation

### Option 1: Using `pdflatex` (TeX Live / MacTeX)

```bash
# Compile Professional Resume
pdflatex adyel-professional-resume.tex

# Compile Academic CV
pdflatex adyel-academic-resume.tex
```

### Option 2: Using `tectonic` (Rust-based, zero setup)

```bash
tectonic adyel-professional-resume.tex
tectonic adyel-academic-resume.tex
```

### Option 3: Using Docker

```bash
docker run --rm -v $(pwd):/work -w /work ghcr.io/xu-cheng/texlive-full pdflatex adyel-professional-resume.tex
docker run --rm -v $(pwd):/work -w /work ghcr.io/xu-cheng/texlive-full pdflatex adyel-academic-resume.tex
```

---

## 🤖 Automated CI/CD Pipeline

Every push to `main` triggers a GitHub Action that:
1. Compiles both `.tex` files in a clean TeX Live environment.
2. Uploads the PDFs as build artifacts.
3. Automatically updates the `latest` GitHub Release with the newly compiled PDF binaries.
