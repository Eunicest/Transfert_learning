# 🐝 Fourmis vs. Abeilles : Apprentissage par Transfert (Vision par Ordinateur)

## 🎯 Concepts et Résultats Clés
*(Pour le détail de l'implémentation, consultez le notebook principal du projet).*

- **Lutter contre le manque de données :** Habituellement, entraîner un réseau de neurones profonds nécessite énormément de données. Ici, le défi est relevé avec un très petit jeu de données (environ 120 images d'entraînement et 75 de validation par classe) grâce à l'utilisation d'un modèle pré-entraîné (**ResNet18**, initialement entraîné sur ImageNet).
- **Deux approches d'Apprentissage par Transfert :** Le projet démontre deux méthodes distinctes pour adapter l'IA :
  - *Le réglage fin (Finetuning) :* Le réseau est initialisé avec les poids pré-entraînés, puis l'ensemble du réseau est réentraîné sur nos images de fourmis et d'abeilles.
  - *L'extracteur de caractéristiques (Feature Extractor) :* Les poids de la quasi-totalité du réseau sont "gelés". Seule la dernière couche est remplacée et entraînée pour effectuer le choix final entre les 2 catégories.
- **Augmentation des données (Data Augmentation) :** Utilisation de transformations (recadrage aléatoire, retournement horizontal) pour diversifier artificiellement les images d'entraînement et limiter le risque de surapprentissage (overfitting).

---

## 📝 Contexte du projet
Ce projet est un tutoriel d'intelligence artificielle dédié à la vision par ordinateur (classification d'images). 
L'objectif est d'entraîner un modèle informatique à faire la différence visuelle entre des **abeilles** et des **fourmis**, en illustrant l'efficacité du Transfer Learning lorsque les données sont limitées.

Le projet s'articule autour de :
1. **La préparation des données :** Chargement, normalisation et augmentation des images d'entraînement.
2. **La modélisation :** Importation du modèle ResNet18 et modification de sa couche finale (Fully Connected layer).
3. **L'entraînement et l'évaluation :** Création de fonctions pour entraîner le modèle, calculer la précision et visualiser concrètement les prédictions sur un lot d'images.

### 🛠️ Outils et Technologies
- **Environnement :** Python, Jupyter Notebook / Colab
- **Méthodes :** Transfer Learning, Réseaux de Neurones Convolutifs (CNN), Data Augmentation
- **Packages clés :** `torch` (PyTorch), `torchvision`, `matplotlib`, `numpy`, `os`, `time`

### 📂 Structure du dépôt
- 📓 `transfer_learning_tutorial.ipynb` : Notebook interactif contenant l'ensemble du code, de l'exploration à l'évaluation.
- 📁 `data/hymenoptera_data/` : Dossier prévu pour héberger le jeu de données (sous-dossiers `train` et `val` pour les classes `ants` et `bees`).

> ⚠️ **Note sur l'exécution :** Le code prépare les fonctions d'entraînement et de visualisation, mais vous devez exécuter les cellules du notebook dans votre propre environnement pour lancer l'entraînement effectif et obtenir la précision (accuracy) finale.

---
<br>

<details>
<summary>🇬🇧 <b>English version (Click to expand)</b></summary>

# 🐝 Ants vs. Bees: Transfer Learning for Computer Vision

## 🎯 Key Concepts & Takeaways
*(For implementation details, please refer to the main project notebook).*

- **Overcoming Data Scarcity:** Training a deep neural network usually requires massive amounts of data. This project tackles a very small dataset (approx. 120 training images and 75 validation images per class) by using a pre-trained model (**ResNet18**, originally trained on ImageNet).
- **Two Transfer Learning Approaches:** The project demonstrates two distinct methods to adapt the AI:
  - *Finetuning the ConvNet:* The network is initialized with pre-trained weights, and then the entire network is trained on our new ants/bees dataset.
  - *ConvNet as Fixed Feature Extractor:* The weights of almost the entire network are "frozen". Only the final fully connected layer is replaced and trained to output our 2 specific classes.
- **Data Augmentation:** Application of techniques like random cropping and horizontal flipping to artificially increase the diversity of the training set and prevent overfitting.

---

## 📝 Project Context
This project is a computer vision tutorial focused on image classification. 
The objective is to train a machine learning model to visually distinguish between **bees** and **ants**, showcasing the power of Transfer Learning when working with limited data.

The project is structured around:
1. **Data Preparation:** Loading, normalizing, and augmenting the training images.
2. **Modeling:** Importing the ResNet18 model and modifying its final layer.
3. **Training & Evaluation:** Building functions to train the model, calculate accuracy, and visualize predictions on a batch of test images.

### 🛠️ Tools and Technologies
- **Environment:** Python, Jupyter Notebook / Colab
- **Methods:** Transfer Learning, Convolutional Neural Networks (CNN), Data Augmentation
- **Core Packages:** `torch` (PyTorch), `torchvision`, `matplotlib`, `numpy`, `os`, `time`

### 📂 Repository Structure
- 📓 `transfer_learning_tutorial.ipynb`: Interactive notebook containing all code, from data loading to evaluation.
- 📁 `data/hymenoptera_data/`: Directory intended to host the dataset (with `train` and `val` subfolders for `ants` and `bees`).

> ⚠️ **Note on execution:** The notebook sets up the training and visualization functions, but you will need to run the cells in your own environment to actually train the model and see the final accuracy metrics.
</details>