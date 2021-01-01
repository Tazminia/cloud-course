# La conteneurisation

<!-- .slide: class="page-title" -->



## Table des matières

<!-- .slide: class="toc" -->

- [Présentation du cours"](#/1)
- [Terminologie](#/2)
- [Le contexte cloud](#/3)
- [Les services cloud](#/4)
- [Organisation des ressources](#/5)
- [Gestion d'identité et d'accès](#/6)
- **[La conteneurisation](#/7)**
- [L'infrastructure as code](#/6)



## Contenu du chapitre

<!-- .slide: class="toc" -->

- [Modèle de déploiement classique](#/old-deployment)
- [Limites du modèle classique](#/old-deployment-limits)
- [La conteneurisation](#/containers)



## Modèle de déploiement classique

<!-- .slide: id="old-deployment" -->

Les composants d'un déploiement sont comme suit:

| Elément                                                  | Commentaires                                                                                                                      |
| -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Le système d'exploitation                                | Dans le cas de .NET classique, on doit être sur du windows par exemple.                                                           |
| L'environnement d'exécution<br>(runtime)                 | Dans le cas d'une application java, ça va être la JRE dans la version adéquate.                                                   |
| Les dépendances<br>(dependencies)                        | Les packages système et les librairies nécessaires à l'exécution de l'application.                                                |
| Les scripts de lancement<br>(startup scripts/entrypoint) | Des script utilitaire permettant de lancer/arrêter ou relancer une application.                                                   |
| La configuration<br>(configuration)                      | Les fichiers permettant de modifier le comportement de l'application, par exemple selon l'environnement, dev, preprod, prod, etc. |
| L'exécutable<br>(binary)                                 | Dans le cas d'une application java, ça va être un jar. Pour une application python, c'est le code source lui même.                |



## Une machine par OS

Une approche de déploiement serait de déployer plusieurs applications sur une seule grosse machine.

<figure>
    <img src="ressources/one-host-n-apps.png" alt="one-host-n-apps" width="40%"/>
</figure>

- Que faire si deux applications on besoin de versions différentes de la runtime ?
- Que faire si deux applications on besoin de versions différentes d'un package (dépendance) ?
- Que faire si une application bug et cause une pénurie de ressources ? (noisy neighbour)
- Que faire si une application comprend une vulnérabilité ?
- Que faire si une mise à jour de l'OS cause une regréssion sur une seule application ?
- Comment assurer un même comportement entre les différents environnements (dev, preprod,...) ?



## Une machine par application

Une approche de déploiement serait de déployer une application par machine.

<figure>
    <img src="ressources/one-host-one-app.png" alt="one-host-one-app" width="35%"/>
</figure>

- Qui gère les mise à jour d'OS ?
- Qui gère la correction de vulnérabilité de dépendances ?
- Qui a les droits d'accès aux serveurs ?
- Que faire si l'application a des cycles idles et d'autres où il y a un pic de consommation de ressources ?

<figure>
    <img src="ressources/sysops-meme.jpeg" alt="sysops-meme" width="25%"/>
</figure>



## Limites du modèle classique

<!-- .slide: id="old-deployment-limits" -->

Les limites des modèles de déploiement classiques sont principalement:

- Dans le modèle 1 à N:
  - Manque d'`isloation`
  - Manque de `determinisme` (reproductibilité entre environnement): dans le cas où les applications "voisines" ne sont pas les même en dev, preprod, etc.
- Dans le modèle 1 à 1:
  - `Mauvaise utilisation` des ressources
  - Manque de `determinisme` (reproductibilité entre environnement): dans le cas d'une gestion manuelle des serveurs.



## La conteneurisation (1/3)

<!-- .slide: id="containers" -->

Un conteneur (container) correspond à une `encapsulation` d'une application, capable d'utiliser les fonctionnalité du `kernel` d'une machine afin de s'exécuter dans un environnement `isolé` grâce à un environnement d'exécution de conteneur (`container runtime`).

Les environnement d'exécutions de conteneurs les plus connus sont:

- docker
- containerd

Pour schématiser le contenu d'un conteneur, voir schéma ci-dessous:

Ceci veut dire qu'un conteneur comporte les éléments suivants:

<figure>
    <img src="ressources/container.png" alt="container" width="45%"/>
</figure>



## La conteneurisation (2/3)

Les caractéristiques principale des conteneurs sont les suivants:

TODO: Explain !
- isolé
- volatile
- léger



## La conteneurisation (3/3)

L'isolation au niveau du conteneur permet de déployer, sur une même et seule machine hôte:

- des environnements d'une même application sur une seule machine hôte.
- des versions d'une application même.
- des applications qui utilisent une même dépendance mais exigents des versions différentes.


TODO: Image ici pour illustrer tout ça