diff --git a/README.md b/README.md
index ebb55e16895e3d95d7839084c74ea09a3ccf3a65..c943153d00653f1b4b3849e0f97332dfe03facd2 100644
--- a/README.md
+++ b/README.md
@@ -1,2 +1,38 @@
 # NLP-
+
 Test de NLP
+
+## Project Overview
+
+**English**
+
+This repository contains experiments exploring Natural Language Processing (NLP) techniques. It aims to demonstrate how to clean, analyze, and visualize textual data using Python tools.
+
+**Français**
+
+Ce dépôt contient des expériences explorant des techniques de Traitement Automatique du Langage Naturel (TALN). Son objectif est de montrer comment nettoyer, analyser et visualiser des données textuelles avec des outils Python.
+
+## Intended NLP Tasks
+
+- Text cleaning and preprocessing
+- Text analysis (statistical and linguistic approaches)
+- Visualization of results such as word clouds or frequency plots
+
+## Requirements
+
+This project relies on Python 3 with several common libraries. The main packages are:
+
+- `pandas`
+- `spacy`
+
+Install them with `pip`:
+
+```bash
+pip install pandas spacy
+```
+
+After installing spaCy, download a language model, for example:
+
+```bash
+python -m spacy download en_core_web_sm
+```
