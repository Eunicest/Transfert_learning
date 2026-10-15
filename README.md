# 🐝 Fourmis vs. Abeilles : Apprentissage par Transfert (Vision par Ordinateur)

> **Source :** ce projet reprend et commente le [tutoriel officiel PyTorch sur l'apprentissage par transfert](https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html). Les parties qui me sont propres sont indiquées ci-dessous.

## 🎯 Résultats

Jeu de données : environ 120 images d'entraînement et 75 de validation par classe (fourmis / abeilles). Modèle : ResNet18 pré-entraîné sur ImageNet.

| Approche | Accuracy (validation) | Remarques |
| :--- | :---: | :--- |
| Fine-tuning (tout le réseau réentraîné) | 0.9215 | [temps d'entraînement= 3min39s, nombre d'époques=25] |
| Extracteur de caractéristiques (couches gelées, dernière couche entraînée) | 0.9803 | [temps d'entraînement = 1m44s, nombre d'époques = 25] |



**Ce que j'ai observé :** Dans notre cas, l'accuracy des  deux approches semblent être du même ordre de grandeur. Mais, la best accuracy de feature extraction (méthode de la question 1) est meilleure que la best accuracy de fine tuning.
De plus, la méthode feature extraction est plus rapide que la la méthode fine tuning dans notre cas.
Cela peut peut-être s'expliquer par le fait que le fine tuning réajuste tous les paramètres du modèle.

---

## 📝 Contexte et concepts

- **Peu de données :** entraîner un réseau profond demande beaucoup d'images. Ici, un modèle pré-entraîné (ResNet18) permet de travailler avec quelques centaines d'images.
- **Deux approches comparées :** le *fine-tuning* (tous les poids sont réentraînés) et l'*extracteur de caractéristiques* (poids gelés, seule la dernière couche est remplacée et entraînée).
- **Augmentation de données :** recadrage aléatoire et retournement horizontal pour limiter le surapprentissage.


### 🛠️ Outils et technologies
- **Environnement :** Python, Jupyter Notebook / Colab
- **Méthodes :** transfer learning, réseaux de neurones convolutifs (CNN), data augmentation
- **Packages clés :** `torch`, `torchvision`, `matplotlib`, `numpy`

### 📂 Contenu du dépôt
- 📓 `Fourmis_vs_Abeilles_Transfert.ipynb` : notebook principal (préparation des données, modélisation, entraînement, évaluation, visualisation des prédictions).

> ⚠️ **Données :** le jeu de données (`hymenoptera_data`) n'est pas inclus. Il se télécharge via [le lien indiqué dans le tutoriel PyTorch]. Il doit être placé dans `data/hymenoptera_data/` (sous-dossiers `train` et `val`).

---

## ⚠️ Limites et pistes d'amélioration

**Limites**
- Jeu de données très petit : les résultats varient selon le découpage et la graine aléatoire.
- Résultats obtenus sur une seule exécution

**Pistes d'amélioration** : répéter les entraînements avec plusieurs graines, tester une autre architecture


---

<details>
<summary>🇬🇧 <b>English version</b></summary>

# 🐝 Ants vs. Bees: Transfer Learning for Computer Vision

> **Source:** this project reproduces and comments on the [official PyTorch transfer learning tutorial](https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html) . My own contributions are listed below.

## 🎯 Results

Dataset: about 120 training and 75 validation images per class (ants / bees). Model: ResNet18 pre-trained on ImageNet.

| Approach | Validation accuracy | Notes |
| :--- | :---: | :--- |
| Fine-tuning (whole network retrained) | 0.9215 | [training time = 3min39, number of epochs = 25] |
| Fixed feature extractor (frozen layers, last layer trained) | 0.9803 | [training time= 1min44, number of epochs = 25] |

**What I observed:** In our case, the accuracy of both approaches seems to be of the same order of magnitude. But the best feature extraction accuracy (method of question 1) is better than the best fine tuning accuracy.
Moreover, the feature extraction method is faster than the fine tuning method in our case.
This can perhaps be explained by the fact that fine tuning readjusts all the model parameters.

## 📝 Context and concepts

- **Small data:** training a deep network usually needs a lot of images; a pre-trained model (ResNet18) makes a few hundred images enough.
- **Two approaches compared:** fine-tuning (all weights retrained) and fixed feature extractor (frozen weights, only the last layer replaced and trained).
- **Data augmentation:** random cropping and horizontal flipping to limit overfitting.


### 🛠️ Tools
- **Environment:** Python, Jupyter Notebook / Colab
- **Methods:** transfer learning, convolutional neural networks (CNN), data augmentation
- **Key packages:** `torch`, `torchvision`, `matplotlib`, `numpy`

### 📂 Repository content
- 📓 `Fourmis_vs_Abeilles_Transfert.ipynb`: main notebook (data preparation, modeling, training, evaluation, prediction visualization).

> ⚠️ **Data:** the dataset (`hymenoptera_data`) is not included. Download it from [the link given in the PyTorch tutorial] and place it in `data/hymenoptera_data/` (`train` and `val` subfolders).

## ⚠️ Limitations and improvements

**Limitations**
- Very small dataset: results vary with the split and the random seed.
- Results from a single run

**Possible improvements**: repeat training with several seeds, try another architecture



</details>
