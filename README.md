# 📄 Résumeur Intelligent de Documents Business PDF avec Transformers (Fine-tuning BART)

## 🎯 Objectif du projet

Ce projet a pour but de concevoir un système de **résumé automatique de documents PDF** à l’aide de modèles Transformers. Il s'adresse à plusieurs cas d’usage professionnels :

- Lecture rapide de **rapports d’entreprise**, **comptes rendus**, **études sectorielles**
- Synthèse de documents volumineux pour **gagner du temps**
- Intégration dans des outils de **veille, d’archivage ou de documentation interne**

Ce projet a été réalisé à des fins pédagogiques et techniques pour démontrer :

- La maîtrise des bibliothèques NLP modernes : `transformers`, `pdfplumber`, etc.
- La compréhension du résumé génératif avec des modèles comme **BART** ou **T5**
- La capacité à construire un **pipeline complet** de traitement de documents

---

## 🧠 Contexte technique

Le format PDF, standard dans le monde professionnel, est difficile à traiter automatiquement en raison de :

- La complexité de l’**extraction de texte brut** (mise en page, tableaux, sauts de ligne)
- La **limitation de longueur des séquences** dans les modèles Transformers
- La nécessité de générer un **résumé fluide, cohérent et fidèle**

Le projet s’appuie sur les outils suivants :

- [`pdfplumber`](https://github.com/jsvine/pdfplumber) pour extraire le texte des fichiers PDF
- [`transformers`](https://huggingface.co/docs/transformers/) de Hugging Face avec le modèle `facebook/bart-large-cnn`
- Une logique de **découpage intelligent** (chunking) des textes pour traiter les longs documents

---

## 📦 Pipeline global

```text
PDF 
 └──▶ Extraction de texte (pdfplumber)
       └──▶ Prétraitement (nettoyage, )
             └──▶ Découpage en segments (chunks) (si besoin)
                   └──▶ Résumé automatique (BART fine-tuné)
                         └──▶ Agrégation finale du résumé
