---
title: "Projet POKEMON : Monitoring de liens et routeurs"
type: page
date: 2025-01-11
tags: ["Réseau", "Réseaux programmables", "Traffic engineering"]
---

|En collaboration avec | Affiliation | Rôle | 
| :------------------ | :----------: | :----------: |
| Benjamin Gliech <a href="https://www.linkedin.com/in/benjamin-gliech/"><img src="/images/linkedin.svg" alt="Linkedin" width="24px"></a> <a href="https://github.com/Pinguee"><img src="/images/github.svg" alt="GitHub" width="24px"></a>| Étudiant M2 SIRIS | Binôme |  
 
| Compétences |  et |  technologies |
| :------------------: | :----------: | :----------: |  
| [Language P4](https://p4.org/) | [Mininet](https://mininet.org/) | Python |  


| Résumé : |
| :------------------ |
| Dans le cadre de mon Master 2, nous avons programmé un outil de monitoring de liens et routeurs à l'aide de [P4](https://p4.org/), du framework [P4Utils](https://github.com/nsg-ethz/p4-utils) et [Mininet](https://mininet.org/).| 

| Détail : |
| :------------------ |

Le projet consistait à développer un outil de monitoring de switchs programmables et de réparation automatique des tables de routage, en utilisant un programme P4 au sein d'une simulation Mininet. Le code est présent sur [GitHub](https://github.com/BirdEnthusiast123/p4-monitoring)

Le code P4 permet d'avoir l'état des liens entre switchs voisins et l'état des chemins entre switchs distants.
Un exemple d'affichage se trouve ci dessous : 
![affichage monitoring](/images/pokemon_monitor.png)

L'état du chemin reliant s4, la source, à s2, la destination, affiche en rouge que le chemin n'est pas en bonne santé, et que 0% des sondes n'ont réussi à faire l'aller-retour.
Les switchs 2 et 8 ont été dégradés afin de mettre en évidence l'affichage des pannes et la réactivité des mises à jour des tables de routages.

Lorsqu'un lien est reconnu comme défaillant, son poids, dans l'algorithme de routage, est augmenté, jusqu'à ce qu'il ne soit plus considéré.


