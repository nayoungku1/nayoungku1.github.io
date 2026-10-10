---
title: "Language-Model-Based RNA-seq Data ETL Workflow for Ovarian Cancer Classification Model"
collection: publications
category: thesis
type: "Bachelor's thesis"
permalink: /publication/2025-06-30-under-thesis
excerpt: "Advisor: Prof. Taejin Ahn. A pipeline that tokenizes RNA-seq reads at the gene level, embeds them with a pretrained protein language model (ProtBERT), and classifies samples with a Bi-LSTM (test AUC 0.71)."
date: 2025-06-30
venue: 'Handong Global University'
paperurl: '/files/language.pdf'
citation:
---

This is my bachelor's thesis, advised by Prof. Taejin Ahn. Early and accurate diagnosis of ovarian cancer is hindered by the lack of reliable biomarkers and by the complexity of transcriptomic data. To address this, I developed an RNA-seq ETL pipeline that treats raw sequencing data as a biological language: nucleotide sequences are tokenized at the gene level, translated into amino acid sequences, embedded with a pretrained transformer (ProtBERT), and classified with a Bi-LSTM to distinguish cancerous from non-cancerous samples.

The model achieved a test AUC of 0.71, suggesting that contextual embeddings can capture disease-related signal. Beyond classification, the embeddings themselves offer a view into the data, pointing to the potential of language-model and natural language processing techniques for sequencing data analysis.

<img src='/images/research-overview-1.png'>
