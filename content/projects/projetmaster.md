---
title: "Projet Master : Infrastructure système et réseau de supervision d'une flotte de véhicules"
type: page
date: 2025-01-23
tags: ["Réseau", "Infrastructure", "DevOps", "Monitoring"]
---

- Septembre 2024 - Janvier 2025

|En collaboration avec | Affiliation | Rôle | 
| :------------------ | :----------: | :----------: |
| Nicolas Elfering <a href="https://www.linkedin.com/in/nelfering/"><img src="/images/linkedin.svg" alt="Linkedin" width="24px"></a>| Étudiant M2 SIRIS | Chef de projet|  
| Éloi Colin| Étudiant M2 SIRIS | Équipe Infrastructure|  
| Kévin Hentz<a href="https://www.linkedin.com/in/kevin-hentz/"><img src="/images/linkedin.svg" alt="Linkedin" width="24px"></a>| Étudiant M2 SIRIS | Équipe Dev Web|  
| Jessica Klotz<a href="https://www.linkedin.com/in/jessica-klotz-jk/"><img src="/images/linkedin.svg" alt="Linkedin" width="24px"></a>| Étudiante M2 SIRIS | Équipe Dev Web|  
| Florian Halm<a href="https://www.linkedin.com/in/florian-halm-b3b975331/"><img src="/images/linkedin.svg" alt="Linkedin" width="24px"></a>| Étudiant M2 SIRIS | Équipe Embarqué|  
| Maxime Friess<a href="https://www.linkedin.com/in/maximefriess2/"><img src="/images/linkedin.svg" alt="Linkedin" width="24px"></a>| Étudiant M2 SIRIS | Équipe Embarqué|  


 
| Compétences |  et |  technologies |
| :------------------: | :----------: | :----------: |  
| OpenStack | Consul & Nomad | Prometheus & Grafana |  
| InfluxDB | PostgreSQL |  Minio (S3) |
| NginX | Wireguard (VPN) |  Docker|


| Résumé : |
| :------------------ |
| Dans le cadre de mon Master 2, j'ai participé à la mise en place de l'infrastructure hébergeant un service factis de monitoring de véhicules.| 


| Détail : |
| :------------------ |

L'application développée est un outil de monitoring de véhicules, nous avons utilisé une caméra, un capteur GPS et une prise OBD2 (On Board Diagnostic) pour récolter des informations sur les voitures de la flotte. 

Ces informations étaient envoyées pérdiodiquement à une infrastructure, sur laquelle je travaillais. 

Cette infrastructure hébergeait également une API, permettant de récolter les informations stockées dans les différentes bases de données, et un site web, sur lequel pouvait se connecter le personnel souhaitant avoir des informations sur les différents véhicules. 

1. Infrastructure

L'infrastructure était découpée en deux sites, le site C315 (principal) et le site OpenStack (backup) dont j'étais responsable. 

À l'aide de l'outil OpenStack, j'ai instancié 3 types de machines virtuelles : 
- Développement : où travaillaient les équipes de développement de l'application (frontend/backend)
- Utilitaire : bastion SSH, serveur VPN
- Production : environnement où se connectent les client.e.s de l'application (backup)

![Schéma de l'infrastrcuture réseau du site OpenStack](/images/schema_infra_openstack.drawio-1.png)

La configuration de nouvelles VM a été automatisé à l'aide d'Ansible, comme on peut le voir dans la démo ci-dessous.

Les moments importants sont (cliquez sur les horaires pour vous y rendre sur la vidéo) :
 - à <a onclick="setVideoTime(40, 'ansible')">00:40</a> : ajout de la machine demo (192.168.0.71) à l'inventaire
 - à <a onclick="setVideoTime(65, 'ansible')">01:05</a> : début de la configuration automatique via Ansible
 - à <a onclick="setVideoTime(240, 'ansible')">04:00</a> : la machine est ajoutée au cluster Consul / Nomad
 - à <a onclick="setVideoTime(290, 'ansible')">04:50</a> : la machine est monitorée par Prometheus / Grafana

<video id="ansible" display=auto max-width=100% height=auto autoplay controls muted>
  <source src="/images/ansible.mp4" type="video/mp4">
Your browser does not support the video tag.
</video> 

Une fois une machine virtuelle configurée, elle peut héberger l'application car elle fait partie du cluster Consul / Nomad qui servent à répartir la tâche sur les différentes VM en distribuant les conteneurs en fonction de la charge que les conteneurs subissent.

On le voit dans la démo (cliquez sur les horaires pour vous y rendre sur la vidéo) : 
 - à <a onclick="setVideoTime(20, 'autoscale')">00:20</a> : lancement d'un grand nombre de requêtes qui va surcharger l'infrastructure
 - à <a onclick="setVideoTime(50, 'autoscale')">00:50</a> : on remarque le pic de requêtes sur l'interface de droite et la création automatique d'un nouveau conteneur sur l'interface de gauche
 - à <a onclick="setVideoTime(122, 'autoscale')">02:02</a> : on remarque que les conteneurs se partagent les requêtes pour équilibrer la charge et que de noueaux conteneurs sont créés
 - à <a onclick="setVideoTime(201, 'autoscale')">03:21</a> : une fois le pic de trafic fini, les conteneurs sont arrêtés car ils ne sont plus nécessaires

<video id="autoscale" display=auto max-width=100% height=auto autoplay controls muted>
  <source src="/images/autoscale.mp4" type="video/mp4">
Your browser does not support the video tag.
</video> 

<script>
    function setVideoTime(seconds, id) {
        var video = document.getElementById(id);
        video.currentTime = seconds;
        video.play();
        video.focus();
    }
</script>