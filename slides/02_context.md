# Le contexte cloud

<!-- .slide: class="page-title" -->



## Table des matières

<!-- .slide: class="toc" -->

- [Présentation du cours](#/1)
- **[Le contexte cloud](#/2)**
- [Les services cloud](#/3)
- [Organisation des ressources](#/4)
- [Gestion d'identité et d'accès](#/5)
- [La conteneurisation](#/6)
- [L'infrastructure as code](#/7)



## Contenu du chapitre

<!-- .slide: class="toc" -->

- [Terminologie](#/terminologie)
- [Modlèle OpEx CapEx](#/opex-capex)
- [Agilité](#/agility)



## Terminologie

<!-- .slide: id="terminologie" -->

- Disponibilité (availability): probabilité qu’un système fonctionne correctement à un instant donné
- Scalabilité (scalability): Capacité du système à s’adapter au dimensionnement vers des tailles inférieures ou supérieure
  - Horizontale: Concerne la duplication. Capacité à modifier le nombre d’instances (+: scale out/-: scale in)
  - Verticale: Concerne la taille des ressources (+: scale up/-: scale down)
- Tolérance aux pannes (fault tolerance): Capacité du système à continuer de fonctionner (même en dégradé) suite à une panne au niveau d’un composant
- Reprise d'activité (Disaster Recovery): Capacité du système à reprendre un fonctionnement normal suite à une panne générale



## Modlèle OpEx CapEx

<!-- .slide: id="opex-capex" -->

- Capital Expenditure (CapEx): dépenses d'investissement. Ce type de dépense est souvent lié à l'achat. Dans le cas du modèle on premise on a des dépenses importantes liées à:
  - Prix d'achat du matériel
  - Location des datacenter (batiments dans lesquels on installe le matériel)
  - Prix des équipements annexes (ventilation, sécurité du batiment, etc)
  - Salaire des personnes qui s'occupent de maintenir le matériel en situation opérationnelle
  - Prix des licenses
- Operational Expenditure (OpEx): dépenses d'exploitation. Ce type de dépense concerne plutôt les frais lié à l'exploitation ou la location. Dans le cas du modèle cloud les dépenses se réduisent à:
  - Prix d'utilisation des services cloud



## Agilité

<!-- .slide: id="agility" -->

- Agilité business: capacité à répondre rapidement à une demande business.
  - Dans le contexte on premise on a deux choix:
    - Favoriser la productivité: Prévoir des machines en avance et accepter qu'on puissent avoir des machines non utilisées prêtes à l'emploi en cas de nouveau besoin.
    - Favoriser le coût: Prévoir le juste besoin actuel ou à court terme et accepter qu'on doivent attendre le passage de commande et l'installation de matériel en cas de nouveau beson.
  - Cloud: Montée en charges facile via allocation quasi instantanée de nouvelles ressources.
- Pay as you go: La facturation à l’utilisation permet une meilleure maîtrise des coûts.
