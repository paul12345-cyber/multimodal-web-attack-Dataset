# MWAD: A Multimodal Web Attack Dataset for AI-Driven SQL Injection Detection

## Overview

The **Multimodal Web Attack Dataset (MWAD)** is a novel labelled cybersecurity dataset developed as part of the author's doctoral research in cybersecurity at **La Trobe University, Australia**.

The dataset generation methodology, design, and description are presented in the peer-reviewed journal article:

> **Yeboah, P. N., et al. (2026).** *SQL injection detection using self-supervised pre-training and multimodal techniques*. **Intelligent Systems with Applications**, **31**, 200702.  
> https://doi.org/10.1016/j.iswa.2026.200702

Unlike traditional web attack datasets that typically contain only **HTTP requests** or **network traffic**, MWAD integrates **application-layer HTTP request data** with **network flow features**, providing a multimodal representation of web attacks.

MWAD is designed to support the development and evaluation of **artificial intelligence (AI)** and **machine learning (ML)** models for web attack detection, with a particular focus on **SQL injection (SQLi)**. By combining complementary data modalities, the dataset enables researchers to investigate multimodal learning approaches that improve the accuracy and robustness of AI-driven web attack detection.


Each MWAD sample combines two complementary data modalities:

1. **HTTP request data**, representing the content and structure of web requests.
2. **Network-flow features**, representing the behavioural characteristics of the corresponding network traffic.

---

## Dataset Generation Pipeline

The dataset was generated in a controlled private-network environment using a vulnerable web server hosted on a **Metasploitable virtual machine**.

SQL injection attacks were executed using **SQLMap** and SQL injection payloads. The resulting traffic was collected and processed using the following tools:

- **Wireshark** for HTTP request logging
- **Tcpdump** for packet capture
- **NFStream** for network-flow feature extraction

The HTTP request data and corresponding flow-level features were subsequently labelled and combined to produce the final multimodal dataset.

<p align="center">
  <img src="images/datasetgeneration.png"
       alt="MWAD multimodal dataset generation pipeline"
       width="900">
</p>

<p align="center">
  <em>Figure 1. MWAD generation pipeline showing SQL injection execution, HTTP request collection, packet capture, flow-feature extraction and multimodal data integration.</em>
</p>

---

## Dataset Composition

| Class | Number of samples | Description |
|---|---:|---|
| Benign | 500 | Legitimate web requests and their corresponding network-flow features |
| SQL injection attack | 500 | SQL injection requests and their corresponding network-flow features |
| **Total** | **1,000** | Labelled multimodal web-traffic samples |

The balanced class distribution supports controlled evaluation of binary SQL injection detection models.

---

## Data Modalities

### HTTP Request Modality

The HTTP modality contains request-level information generated during interactions with the vulnerable web application.

This modality can support:

- textual analysis of HTTP requests
- malicious payload detection
- token-based machine learning
- deep learning and transformer-based modelling
- self-supervised representation learning

### Network-Flow Modality

The network-flow modality contains statistical and behavioural features extracted from captured traffic using NFStream.

This modality can support:

- traffic-flow classification
- anomaly detection
- behavioural attack analysis
- conventional machine learning
- multimodal fusion with HTTP request representations

---

## Key Features

- Publicly available multimodal cybersecurity dataset
- Contains paired HTTP-request and network-flow information
- Includes clearly labelled benign and SQL injection traffic
- Balanced dataset containing 500 samples in each class
- Generated through controlled SQL injection experiments
- Supports reproducible cybersecurity research
- Suitable for unimodal and multimodal model evaluation
- Applicable to machine learning, deep learning and self-supervised learning

---

## Dataset Novelty

Many web-attack datasets provide either application-layer request information or network-level traffic features separately.

MWAD was developed to provide **paired application-layer and network-flow representations of the same web interactions**. This enables researchers to examine whether combining the two modalities improves SQL injection detection compared with relying on either modality independently.

The dataset therefore provides a reusable research resource for investigating multimodal learning and data-fusion strategies in web-attack detection.

---

## Associated Publication

This dataset underpins research accepted for publication in:

> **Intelligent Systems with Applications**, Elsevier.

```text
Yeboah, Paul Ntim, A. S. M. Kayes, Wenny Rahayu, Eric Pardede, and Syed Mahbub. "SQL injection detection using self-supervised pre-training and multimodal techniques." Intelligent Systems with Applications (2026): 200702.
