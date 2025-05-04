---
title: "Réseau de neurones : catégorisation d'organites cellulaires"
type: page
date: 2025-01-15
tags: ["Réseau de neurones", "Machine learning", "Intelligence artificielle"]
---


|En collaboration avec | Affiliation | Rôle | 
| :------------------ | :----------: | :----------: |
| Nicolas Elfering <a href="https://www.linkedin.com/in/nelfering/"><img src="/images/linkedin.svg" alt="Linkedin" width="24px"></a>| Étudiant M2 SIRIS | Binôme |  
 
| Compétences |  et |  technologies |
| :------------------: | :----------: | :----------: |  
| Python | [TensorFlow](https://www.tensorflow.org/) | |  


| Résumé : |
| :------------------ |
| Dans le cadre de mon Master 2, nous avons développé une intelligence artificielle de catégorisation d'organelles à partir d'images à l'aide de TensorFlow.| 

| Détail : |
| :------------------ |

Le rapport est disponible [ici](/images/rapport_API.pdf), le Jupyter notebook [ici](/images/api.ipynb). 

Le projet était une compétition [Kaggle](https://www.kaggle.com/competitions/2024-competion-asi-i-3-d/overview) où il était question d'entraîner un réseau de neurones classifiant des images d'organelles.
Le résultat obtenu est une IA qui catégorise correctement, dans 95% des cas, l'organelle.

L'IA a été entrainée à l'aide de méthodes comme le transfer learning et l'augmentation d'images.

Le transfer learning correspond à réutiliser un réseau de neurones pré-entraîné, dans notre cas nous avons choisi EfficientNet.
L'augmentation d'images correspond à modifier une image de l'ensemble d'entraînement pour agrandir cet ensemble et rentre le réseau plus précis, un exemple de rotation et zoom se trouve ci dessous. A partir d'une image de base on peut en créer 4 autres qui alimenteront la base d'apprentissage.

![exemple d'augmentation d'images](/images/api_augment.png)

Les résultats obtenus sont de 95% de précision. Dès la première des 5 passes, le réseau était déjà excellent : 

![graphique representant l'augmentation de la precision du modele](/images/api_evolution.png)