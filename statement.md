# Project Statement & Scope: SmartDoc Vision

## 1. Problem Statement
In daily academic and professional workflows, users frequently receive document photos, lecture slides, or paper assignments directly on their laptops via email, messaging platforms, or cloud storage. However, existing document scanning and flattening applications are predominantly mobile-first. This forces users into an inefficient transfer loop: downloading the raw image on a PC, transferring it to a mobile phone to run through a scanning app, and then sending the cleaned file back to the laptop for submission. SmartDoc Vision eliminates this back-and-forth friction by offering a native desktop Computer Vision application built with Streamlit and OpenCV. It allows users to process, correct, enhance, and compile document images directly on their laptops with automatic boundary detection, custom coordinate tuning, and high-contrast filtering.

## 2. Project Vision & Objectives
SmartDoc Vision bridges automated feature extraction with fine-grained user overrides in a clean desktop interface:

* **Automated Boundary Detection**: Implement morphological operations and contour analysis using OpenCV to locate document edges automatically with safe fallback boundaries.
* **Fine-Tuned Interactive Controls**: Provide a custom directional joystick UI in Streamlit to allow users to make sub-pixel and multi-pixel $2\text{D}$ coordinate adjustments ($\pm1\text{px}$, $\pm5\text{px}$) to refine document corners on a laptop screen.
* **Perspective Correction**: Apply 4-point homography transformations to re-project tilted or skewed document boundaries into flat, top-down rectangular digital outputs.
* **Image Enhancement Pipeline**: Integrate contrast enhancement (CLAHE) and adaptive binarization to clean up shadows, improve legibility, and convert raw photos into document-grade outputs.
* **Multi-Page Compilation**: Manage session state to stash individual processed pages during a study session and export them into a unified PDF file.

## 3. Scope & Target Platform
* **Platform Target**: Optimized specifically for PC and laptop desktop browsers running Streamlit.
* **Input Specifications**: Single-page image files (`.jpg`, `.jpeg`, `.png`) uploaded directly through the user interface.
* **Output Specifications**: Processed high-contrast document images and multi-page concatenated PDF files.

## 4. Architectural Limitations
* **Camera Capture**: The application processes pre-captured uploaded images; it does not connect directly to real-time flatbed hardware scanners or live mobile video streams.
* **Complex Backgrounds**: Auto-detection depends on contrast between the document and its surrounding surface. Highly textured or visually noisy backgrounds may require manual joystick adjustment.
* **OCR Integration**: The current scope focuses exclusively on image processing, geometric transformation, and document enhancement; Optical Character Recognition (OCR) text extraction is reserved for future iterations.