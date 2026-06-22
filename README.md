# SeqXplorer - Plateforme Bioinformatique Clinique

**SeqXplorer** est une suite logicielle d'analyse bioinformatique et de diagnostic automatisé, développée spécifiquement pour le CHU de Liège. Conçue autour d'une interface graphique simple et centralisée, elle permet aux biologistes de traiter des données de séquençage Sanger et de générer des rapports cliniques standardisés, le tout de manière autonome et rapide.

---

## Les 3 Modules d'Analyse (Sanger)

L'application est divisée en trois pipelines cliniques distincts :

1. **Génotypage HCV**
   * ** :** Appairage F/R, Trimming qualité, alignement et consensus.
   * **Base interrogée :** Soumission automatisée via robot (Playwright) à la base experte **Geno2pheno**.
   * **Rendu :** Rapport PDF de typage et sous-typage.

2. **Taxonomie 16S**
   * **Traitement bioinformatique :** Appairage F/R, Trimming qualité, alignement et consensus.
   * **Base interrogée :** Requêtes API (Biopython) sur les bases **NCBI BLASTn** (`16S ribosomal RNA` et `nr/nt`).
   * **Rendu :** Bilan taxonomique avec tableau de traçabilité des 100 meilleurs hits.

3. **Taxonomie Fongique**
   * **Traitement bioinformatique :** Appairage F/R, Trimming qualité, alignement et consensus.
   * **Base interrogée :** Soumission automatisée à la base experte mycologique **Westerdijk (KNAW)**.
   * **Rendu :** Identification fongique avec détection automatisée des taxonomies complexes.

---

## Architecture et Technologies (Stack)

* **Front-End & Interface :** `Streamlit` (Python)
* **Traitement Séquences Sanger :** `Biopython`
* **Automatisation Web (Robots) :** `Playwright`
* **Génération PDF :** `ReportLab` et `pyPDF`

---

## Prérequis Système

Pour faire tourner l'intégralité de SeqXplorer, le PC cible doit simplement disposer de :
* Windows 10 ou Windows 11.
* Python 3.10 ou supérieur installé.
* Une connexion internet active (pour les requêtes API et Playwright).

---

## Installation Initiale

1. Allez dans l'onglet **Releases** à droite de cette page GitHub.
2. Téléchargez la dernière archive `.zip` de l'application.
3. Extrayez le dossier sur votre disque dur (ex: sur le Bureau).
4. Double-cliquez sur `Installation (Ne lancer qu'une fois).bat`. L'application va créer son propre environnement virtuel (venv) isolé et installer ses dépendances de manière autonome.
5. (Optionnel) Lancez `Création du raccourci bureau.bat` pour placer l'icône de l'application sur votre bureau Windows.

**Pour lancer l'application au quotidien :** Double-cliquez simplement sur le raccourci bureau ou sur `SeqXplorer.bat`.

---

## Système de Mise à Jour (Auto-Updater)

L'application est équipée d'un système de mise à jour silencieux et natif.
À chaque lancement de `SeqXplorer.bat`, l'application vérifie ce dépôt GitHub (via le dossier `updates/`) pour voir si un nouveau patch est disponible. 

Si c'est le cas, elle télécharge l'archive, met à jour les scripts en conservant vos rapports cliniques locaux absolument intacts, puis démarre l'interface en quelques secondes. Aucune action n'est requise de la part de l'utilisateur.
