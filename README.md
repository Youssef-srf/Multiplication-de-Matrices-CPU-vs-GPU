# Énoncé de Travaux Pratiques : Benchmark Haute Performance

**Multiplication de Matrices CPU vs GPU (Comparaison NumPy vs CuPy sur Google Colab)**

---

### 📌 Fiche d'identité du TP
* **Module :** Systèmes Répartis et Programmation Parallèle / IA
* **Niveau :** Master d'Excellence en Intelligence Artificielle — FSBM
* **Encadrante :** Mme Oumaima Guendoul
* **Groupe présentateur :** Youssef Sarraf & Sifeddine Legnioui
* **Durée estimée :** 45 à 60 minutes
* **Matériel requis :** Un compte Google (Colab) — aucune installation locale

---

## 1. Objectifs pédagogiques
À l'issue de ce TP, vous serez capable de :
* Configurer un environnement de calcul accéléré par GPU sur Google Colab.
* Mettre en œuvre une même opération (multiplication matricielle) sur CPU avec NumPy et sur GPU avec CuPy.
* Mesurer et comparer des temps d'exécution de façon rigoureuse (avec une phase de préchauffage / « warmup »).
* Interpréter un résultat de benchmark et identifier les limites d'une accélération matérielle.

## 2. Prérequis
* Un compte Google (pour accéder à Google Colab).
* Des bases en Python (variables, boucles, fonctions).
* Avoir suivi la présentation du groupe sur le benchmark CPU vs GPU (les notions de CPU, GPU, VRAM et de complexité O(N³) y sont expliquées).

---

## 3. Mise en place de l'environnement Colab
* **Étape 1 :** Ouvrez [Google Colab](https://colab.research.google.com) et connectez-vous avec votre compte Google.
* **Étape 2 :** Créez un nouveau notebook via `Fichier > Nouveau notebook`.
* **Étape 3 :** Activez l'accélérateur GPU en naviguant dans `Exécution > Modifier le type d'exécution > Accélérateur matériel > GPU` (le profil **T4** convient parfaitement), puis cliquez sur `Enregistrer`.
* **Étape 4 :** Vérifiez que le GPU est bien attribué en exécutant cette commande dans la première cellule de code :
  ```bash
  !nvidia-smi
