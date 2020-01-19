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

## Fonctionnement de circleCI

###Job build 

`docker-compose -f ./docker-compose.dev.yaml build --compress --force-rm --no-cache --pull --parallel` &rarr; Build de l'image

`docker save -o ./${PROJECT_NAME}_nodejs.tar project_nodejs` &rarr; Archivage de l'image

###Job upload

`docker load -i /tmp/workspace/${PROJECT_NAME}_nodejs.tar` &rarr; Chargement de l'image docker

`docker tag project_nodejs ced23/${PROJECT_NAME}_node:latest` &rarr; Renomage de l'image

`echo $PSW | base64 --decode | docker login -u $USER --password-stdin
            docker push ced23/${PROJECT_NAME}_node:latest` &rarr; Publication de l'image sur Dockerhub
