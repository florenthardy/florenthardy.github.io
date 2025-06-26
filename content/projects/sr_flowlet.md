---
title: "Stage 2024 : Segment routing 🤝 Flowlet switching"
type: page
date: 2024-07-31
tags: ["Recherche", "Réseau", "Réseaux programmables", "Traffic engineering"]
---


- Juin 2024 - Juillet 2024

|En collaboration avec | Affiliation | Rôle | 
| :------------------ | :----------: | :----------: |
| Jean-Romain Luttringer <a href="https://jroluttringer.github.io/"><img src="/images/rss.svg" alt="Portfolio" width="24px"></a>| Enseignant-chercheur à iCube (CNRS) | Encadrant |
| Pascal Mérindol <a href="https://clarinet.icube.unistra.fr/~merindol/"><img src="/images/rss.svg" alt="Portfolio" width="24px"></a>| Enseignant-chercheur à iCube (CNRS) | Encadrant | 
 
| Compétences |  et |  technologies |
| :------------------: | :----------: | :----------: |  
| Recherche | [Language P4](https://p4.org/) | [Segment Routing](https://www.segment-routing.net/) |  
| [Flowlet switching](https://people.csail.mit.edu/alizadeh/papers/letflow-nsdi17.pdf) | [Mininet](https://mininet.org/) |  |  


| Résumé : |
| :------------------ |
| Dans le cadre de mon stage d'été après mon Master 1, j'ai créé et étudié la performance de la combinaison entre [Segment Routing](https://www.segment-routing.net/) et [Flowlet switching](https://people.csail.mit.edu/alizadeh/papers/letflow-nsdi17.pdf) à l'aide de [Mininet](https://mininet.org/) et du framework [P4Utils](https://github.com/nsg-ethz/p4-utils).|   


| Détail : |
| :------------------ |

Durant ce stage j'ai étudié la performance d'une solution que j'ai créée qui combine Flowlet Switching et Segment Routing, le tout codé à l'aide de P4 et du simulateur Mininet.

Flowlet switching est un protocole d'équilibrage de charge réactif aux fluctuations de latence ce qui lui permet de réduire la congestion.
Il fonctionne en recalculant le port de sortie assigné à un flux si ce dernier a subit des hausses de latence.

Le Segment Routing est une technologie permettant la redéfinition des chemins que doivent suivre les paquets en ajoutant des segments dans les en-têtes.

La combinaison des deux technologies est intéressante pour plein de raisons : le détail de l'analyse de performance est présente dans [ce rapport](/images/Rapport_de_stage_2024_ICube-3.pdf).
