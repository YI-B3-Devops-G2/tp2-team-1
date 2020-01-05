# B3 Devops - Projet 1
## Info

**Team - 2**

**mail:** cedric.lesueur@ynov.com <br>
**github​_username:** cedro23

**mail:** romain.loire@ynov.com <br>
**github​_username:** romL69

## Objectif
Le but du TP est d'avoir une image Docker qui se met à jour automatiquement sur Docker Hub dès lors qu'un push est fait sur ce repo Git.
Pour faire cela on utilise un projet qui contient un reverse proxy géré à l'aide de Nginx qui oriente soit sur la page principale
de Nginx, soit sur la réponse de base d'une API, soit sur une réponse spécifique de la même API.

## Prérequis

- Docker & Docker Compose
- Powershell

## Installation

Pour installer le projet il suffit de lancer la commande suivante via powershell
`docker pull [nom du projet]`

## Routes

`localhost:3000` &rarr; Page de base de Nginx

`localhost:3000/api` &rarr; Page de base de l'API

`localhost:3000/api/status` &rarr; Page spécifique de l'API
