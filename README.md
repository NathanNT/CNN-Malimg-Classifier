### Classification de Malware avec CNN (Dataset Malimg)

Ce projet utilise un réseau de CNN basé sur VGG16 pour classifier des images de malwares en niveaux de gris. Le dataset Malimg, comprenant 9339 échantillons de malware, est utilisé pour l'entraînement et la validation.

### Dataset

Le dataset Malimg peut être téléchargé à partir du lien suivant : [MalImg dataset](https://figshare.com/articles/dataset/MalImg_dataset_zip/24189882). Une fois téléchargé, les images doivent être organisées dans des sous-répertoires représentant les différentes classes de malware.

### Méthodologie

- **Chargement des Images :**
  - Les images sont chargées à partir des répertoires de classes, redimensionnées à 32x32 pixels et converties en tableaux numériques.
  
- **Prétraitement :**
  - Les images sont prétraitées avec la fonction `preprocess_input` de VGG16.
  - Les étiquettes sont encodées en One-Hot pour la classification multiclasses.
  
- **Modèle :**
  - Un modèle basé sur VGG16 est utilisé avec les couches de base gelées pour l'extraction de caractéristiques.
  - Le modèle ajoute ensuite des couches denses pour la classification.

- **Entraînement :**
  - Le modèle est entraîné pendant 20 époques avec une taille de batch de 20.
  
- **Évaluation :**
  - Le modèle est évalué sur les données de validation avec une précision finale et une perte affichées.
  - Les courbes de précision et de perte sont tracées pour suivre l'évolution au cours de l'entraînement.

### Exécution

1. **Préparer les données :**
   - Téléchargez et extrayez le dataset Malimg [MalImg dataset](https://figshare.com/articles/dataset/MalImg_dataset_zip/24189882).
   - Organisez les images dans les répertoires de formation et de validation comme suit :
     - `dataset_9010/malimg_dataset/train` pour l'entraînement.
     - `dataset_9010/malimg_dataset/validation` pour la validation.
  
2. **Executer le playbook :**

3. **Résultats :**
   - Le modèle entraîné est sauvegardé sous le nom `malimg_model.h5`.
   - Les résultats finaux sur le jeu de test sont affichés, et les courbes d'entraînement 