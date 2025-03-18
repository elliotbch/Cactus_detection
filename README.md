# 🌵 Aerial Cactus Identification

Ce projet utilise des techniques de deep learning pour identifier les cactus de type **Neobuxbaumia tetetzo** dans des images aériennes. Grâce à une architecture CNN personnalisée et à des techniques avancées de prétraitement, nous avons obtenu une précision impressionnante de **99%**.

---

## 📋 Table des matières
1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Architecture du Modèle](#architecture-du-modèle)
4. [Résultats](#résultats)
5. [Installation](#installation)
6. [Utilisation](#utilisation)
7. [Contributeurs](#contributeurs)
8. [Références](#références)

---

## 📖 Introduction

La biodiversité est menacée par les activités humaines telles que l'exploitation forestière, l'agriculture et l'extraction minière. Ce projet vise à faciliter la surveillance écologique en utilisant des images aériennes pour détecter la présence de cactus.

Nous avons développé une architecture CNN (Convolutional Neural Network) capable d'identifier efficacement les cactus dans les images aériennes, contribuant ainsi aux efforts de conservation et à la recherche écologique.

---

## 📊 Dataset

Le dataset utilisé provient du projet **VIGIA** et de compétitions Kaggle sur la reconnaissance de cactus dans des images aériennes.

- **Composition** :
  - 21,500 images aériennes (74.9% avec cactus, 25.1% sans cactus).
- **Prétraitement** :
  - Redimensionnement des images à `32x32` pixels.
  - Normalisation des valeurs des pixels entre `0` et `1`.
  - Techniques d'augmentation de données pour équilibrer les classes (rotation, bruit, luminosité, zoom).

---

## 🧠 Architecture du Modèle

### Conception du CNN
L'architecture du modèle est composée de blocs convolutifs comprenant :
- **Convolutional Layers** : Extraction des caractéristiques.
- **MaxPooling** : Réduction dimensionnelle.
- **Batch Normalization** : Stabilisation du processus d'apprentissage.
- **Dropout** : Réduction du surapprentissage.

### Hyperparamètres
- Optimiseur : Adam
- Fonction de perte : Binary Crossentropy
- Taille du batch : 16
- Nombre d'époques : 50

### Résumé du Modèle
| Couche                | Sortie            | Paramètres |
|-----------------------|-------------------|------------|
| Input Layer           | (32, 32, 3)      | 0          |
| Convolution + Pooling | (16, 16, 48)     | 3,648      |
| Convolution + Pooling | (8, 8, 64)       | 76,864     |
| Convolution + Pooling | (4, 4, 128)      | 204,928    |
| Fully Connected       | (1)              | 193        |

---

## 🏆 Résultats

Le modèle a atteint les performances suivantes :
- **Précision** : 99%
- **ROC/AUC Score** : 1.0
- **Perte sur les données de validation** : 0.6%

### Matrice de Confusion
Les performances du modèle sont excellentes :
- Faux positifs : 2
- Faux négatifs : 3

### Courbes ROC/AUC et Perte
![ROC/AUC Curve](https://cdn.mathpix.com/cropped/2025_03_18_97988f ⚙️ Installation

1. Clonez le dépôt GitHub :
   ```bash
   git clone https://github.com/elliotbch/Cactus_detection.git
   cd Cactus_detection
   ```

2. Installez les dépendances nécessaires :
   ```bash
   pip install -r requirements.txt
   ```

3. Préparez le dataset en téléchargeant les données depuis Kaggle ou en utilisant celles fournies dans le dépôt.

---

## 🚀 Utilisation

1. Lancez le script d'entraînement pour entraîner le modèle :
   ```bash
   python train_model.py
   ```

2. Effectuez des prédictions sur le dataset de test :
   ```bash
   python predict.py --input test_images/
   ```

3. Exportez les résultats sous forme de fichier CSV :
   ```bash
   python export_results.py --output predictions.csv
   ```

---

## 🤝 Contributeurs

Ce projet a été réalisé par :
- Elliot Bouchy  
- Victor Mayaud  
- Aymeric Legros  
- Naveen Johnson Vallavanatt  

Sous la supervision du Professeur Pietro Michiardi, EURECOM, France.

---

## 📚 Références

1. VIGIA: Autonomous Surveillance of Biosphere Reserves ([Lien](https://jivg.org/research-projects/vigia/)).
2. Efren López-Jiménez et al., Columnar Cactus Recognition in Aerial Images Using Deep Learning ([DOI](https://doi.org/10.1016/j.ecoinf.2019.05.005)).
3. Kaggle Dataset: Aerial Cactus Identification ([Lien](https://www.kaggle.com/competitions/aerial-cactus-identification)).
