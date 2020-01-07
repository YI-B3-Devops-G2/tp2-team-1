# B3 Devops - Projet 1
## Info

**Team - 2**

**mail:** cedric.lesueur@ynov.com <br>
**github​_username:** cedro23

**mail:** romain.loire@ynov.com <br>
**github​_username:** romL69

## Objectif
Le but du TP est d'avoir une image Docker qui se met à jour automatiquement sur Docker Hub dès lors qu'un push est fait sur ce repo Git. <br>
L'image contient une API avec une route de base et une route avec un retour spécifique.

## Prérequis

- Docker & Docker Compose
- Powershell

## Installation

Pour installer le projet il suffit de lancer la commande suivante via powershell, <br>
`docker pull ced23/devops-team-1_node`

Pour le lancer l'API seule il faut utiliser la commande, <br>
`docker run -p 4040:4040 ced23/devops-team-1_node`

Sinon, <br>
`docker run ced23/devops-team-1_node`
## Routes

##### API seule
`localhost:4040/` &rarr; Page de base de l'API

`localhost:4040/status` &rarr; Page spécifique de l'API

##### API + Nginx

`localhost:[port_nginx]/[route_api]` &rarr; Page de base de l'API

`localhost:[port_nginx]/[route_api]/status` &rarr; Page spécifique de l'API