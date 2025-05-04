---
title: "Stage 2025 : GARDEN ou le profilage énergétique de réseaux programmables"
type: page
date: 2025-02-10
tags: ["Recherche", "Réseau", "Réseaux programmables", "Consommation énergétique"]
---
- Février 2025 - En cours  

|En collaboration avec | Affiliation | Rôle | 
| :------------------ | :----------: | :----------: |
| Jean-Romain Luttringer <a href="https://jroluttringer.github.io/"><img src="/images/rss.svg" alt="Portfolio" width="24px"></a>| Enseignant-chercheur à iCube (CNRS) | Encadrant |
| Julien Montavont <a href="https://clarinet.icube.unistra.fr/~montavont/"><img src="/images/rss.svg" alt="Portfolio" width="24px"></a>| Enseignant-chercheur à iCube (CNRS) | Encadrant | 
 
| Compétences |  et |  technologies |
| :------------------: | :----------: | :----------: |  
| Recherche | [Language P4](https://p4.org/) | Profilage énergétique |  


| Résumé : |
| :------------------ |
| Dans le cadre de mon stage de fin de Master 2, j'étudie la consommation énergétique d'équipements réseau programmables, en particulier les switch programmables de la marque intel : les Tofino 1 et 2. |   

| Détail : |
| :------------------ |

L'équipe de recherche *Réseaux* du laboratoire iCube (CNRS, Université de Strasbourg...) m'a accueili pour participer au projet [GARDEN](http://garden.icube.unistra.fr/) qui vise à réduire la consommation énergétique des réseaux programmables.

Mon rôle dans ce projet est de préparer le terrain, c'est-à-dire trouver un maximum de ressources, en particulier des articles de recherche, des documentations techniques, des rapports etc. qui nous permettront de définir un état de l'art.
Le but étant de créer de nouvelles connaissances dépassant l'existant et donc ne font pas partie de l'état de l'art.

Pour atteindre ce but, je profilerai et modéliserai la consommation énergétique d'un switch programmable afin d'ouvrir la porte à d'autres chercheur.euse.s qui souhaitent étudier d'autres switchs programmables ou définir des applications qui nécessiteraient d'avoir au moins une extimation de la consommation des switchs (protocole, technologie...).

Il me reste plein de paramètres à étudier mais un exemple frappant de l'utilité de cette recherche est que les modélisations passées (dont on peut voir un exemple ci dessous), ne prennent pas en compte la multitude de paramètres que rajoute la programmabilité des switchs.

![ici](/images/modele.png)
Ce modèle illustra la consommation énergétique (**P**) en fonction du débit qui traverse le switch (**D**). On remarque que, selon cette modélisation, la consommation évolue de manière linéairement en fonction du débit par rapport aux paramètres (**E**). 
Mais comme on peut le voir dans la figure plus bas, la consommation énergétique dépend, entre autres, du nombre d'entrées dans les tables de routage et des technologies utilisées pour router.
Ici on compare alpm qui est un algorithme de découpage d'arbre de préfixe et d'optimisation d'allocation dans les cases mémoires avec le lpm naïf. Et l'on remarque qu'alpm performe bien mieux.

![ici](/images/alpm_vs_lpm.png)

Le bilan à mi-parcours de ce stage est disponible [ici](/images/Bilan_à_mi_parcours_Stage_2025-2.pdf)

