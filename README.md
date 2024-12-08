---
# Ingénierie des panneaux photovoltaïques
---

## Informations du document

| **Notions Systèmes**    | Analyse et conception de systèmes |
| ----------------------- | --------------------------------- |
| **Version du document** | 1.4                               |
| **Professeur**          | Illyas Harti                      |
| **Étudiant**            | Sami Boufassa                     |
| **Date**                | 11 Novembre 2024                  |

## Table des matières

- [Angles d'analyse du système cible](#angles-danalyse-du-système-cible)
  - [Contexte](#contexte)
  - [Système d'intérêt](#système-dintérêt)
- [Identification du périmètre systèmique](#identification-du-périmètre-systèmique)
  - [Milieu extérieur et parties prenantes](#milieu-extérieur-et-parties-prenantes)
  - [Diagramme de contexte](#diagramme-de-contexte)
- [Analyse et modélisation opérationnelle](#analyse-et-modélisation-opérationnelle)
  - [Expression des besoins](#expression-des-besoins)
  - [Diagramme de scénario opérationnel](#diagramme-de-scénario-opérationnel)
- [Analyse et modélisation fonctionnelle](#analyse-et-modélisation-fonctionnelle)
  - [Exigences fonctionnelles](#exigences-fonctionnelles)
  - [Diagramme d'états](#diagramme-détats)
  - [Diagramme de scénario fonctionnel](#diagramme-de-scénario-fonctionnel)
- [Analyse et modélisation organique](#analyse-et-modélisation-organique)
  - [Exigences organiques](#exigences-organiques)
  - [Diagramme de scénario organique](#diagramme-de-scénario-organique)

---

# Angles d'analyse du système cible

## Contexte

La transition énergétique mondiale, marquée par une demande croissante
d'énergies renouvelables, soulève des défis majeurs concernant la
réduction de la dépendance aux énergies fossiles. Parmi les solutions
les plus prometteuses, les systèmes photovoltaïques (PV), qui
convertissent l'énergie solaire en électricité, jouent un rôle essentiel
dans cette transformation énergétique. Cependant, bien que les
technologies photovoltaïques aient fait des progrès considérables ces
dernières décennies, plusieurs enjeux techniques, économiques et
environnementaux demeurent pour permettre leur déploiement à grande
échelle de manière efficace et durable.

Les systèmes photovoltaïques, comprenant principalement des panneaux
solaires, sont désormais utilisés dans une large gamme d'applications,
allant des installations domestiques aux grandes centrales solaires
industrielles. Ces systèmes trouvent leur place dans des secteurs aussi
variés que l'habitat, l'industrie, les transports, ou encore les
infrastructures publiques, tels que les écoles et les hôpitaux. Ils se
déclinent sous diverses formes : centrales solaires, chauffe-eaux
solaires, lampadaires photovoltaïques, et bien sûr, les panneaux
solaires installés sur des toitures ou des terrains.

La société X spécialisée dans la gestion de data center hébergeant des
ordinateurs / serveurs dédiés pour d'autres clients, souhaite installer
des systèmes photovoltaïques afin de réduire son empreinte et taxe
carbones. Dans ce contexte, l'ingénierie des systèmes photovoltaïques
est cruciale pour répondre aux défis de conception, de performance, de
coût, et d'intégration dans les réseaux électriques. L'optimisation de
ces systèmes nécessite une compréhension approfondie des paramètres
techniques et des contraintes environnementales, tout en prenant en
compte les aspects économiques et la viabilité à long terme des
installations. Cette analyse s'intéresse particulièrement aux panneaux
photovoltaïques, leur conception, leur efficacité et leur déploiement
dans un réseau de distribution.

## Système d'intérêt

Ce système des panneaux photovoltaïques est principalement conçu pour
fonctionner dans un environnement industriel, avec une application
particulière dans la production d'électricité à partir de l'énergie
solaire. Le périmètre du système est clairement défini : il inclut tous
les composants physiques nécessaires pour capturer l'énergie solaire et
la convertir en électricité. Cela comprend les cellules photovoltaïques,
les modules solaires, ainsi que les connexions électriques internes qui
permettent la distribution de l'énergie produite. Les panneaux
photovoltaïques, bien qu'ils fonctionnent de manière autonome, ne sont
pas isolés. Ils doivent être intégrés dans un réseau de distribution
d'électricité, ce qui implique des interactions avec d'autres systèmes
externes. L'ingénierie de ce système doit donc non seulement modéliser
ses constituants, les liaisons entre ses constituants, mais aussi les
relations avec les éléments du milieu extérieur qui définit ses limites.
Pour ce faire, après modélisation du périmètre systèmique,
l'architecture \"trois angles / visions\" sera utilisée, comprenant dans
un premier temps l'analyse opérationnelle, suivie de l'analyse
fonctionnelle, et enfin, de l'analyse organique. Cette démarche d'étude
conduit logiqument a un ordonnancement des diagrammes suivants :
Diagramme de contexte, diagramme d'états, diagramme de scénario
opérationnel, diagramme de scénario fonctionnel, diagramme de scénario
organique.

# Identification du périmètre systèmique

## Milieu extérieur et parties prenantes

Le système s'insère dans un réseau industriel HTA. En l'occurrence, les
panneaux sont utilisés dans des installations de type data center ou
bâtiments commerciaux, où l'efficacité énergétique et la réduction des
coûts liés à la consommation d'électricité sont des enjeux majeurs.
L'optimisation de leur production d'énergie dépend de facteurs externes
comme la disponibilité du soleil, la température et l'orientation des
panneaux, mais aussi des interactions avec le réseau électrique.
L'efficacité du système se trouve ainsi conditionnée par des éléments
extérieurs difficilement maîtrisables. Afin d'identifier les systèmes et
acteurs externes qui interagissent avec le système cible, il est
pertinent d'utiliser la méthode des 6W en se posant les questions
suivantes :

- **Who ?** : Quelles sont les parties prenantes physiques (humaines
  ou organisationnelles) qui ont une interaction avec le système ? Les
  acteurs principaux sont les fabricants, les installateurs ou
  techniciens, les ingénieurs systèmes ou project managers, les
  gestionnaires de data center, les autorités réglementaires, les
  utilisateurs finaux autrement dit les fournisseurs d'électricité et
  les data center, et organismes de certification.

- **What ?** : Quels sont les systèmes externes qui ont une influence
  sur le système cible? L'ensemble des composants du système
  photovoltaïques incluant les onduleurs, les batteries, les
  régulateurs de charge, les trackers solaires/montures, les
  compteurs, les transformateurs, les isolateurs et les dispositifs de
  protection (fusibles, disjoncteurs, parafoudres,
  refroidisseurs\...).

- **Where ?** : Quelles sont les localisations des systèmes externes
  qui ont une influence sur le comportement du système ? Les lieux où
  les panneaux photovoltaïques sont installés pour alimenter des
  systèmes informatiques ou des installations industrielles. Ces
  centres peuvent être situés dans des zones stratégiques proches de
  grandes infrastructures électriques.

- **When ?** : Quels sont les systèmes externes qui interagissent tout
  le temps avec le système ou à certaines périodes seulement ?
  L'énergie solaire et les conditions météorologiques (température,
  humidité et corrosion) influencent la performance des panneaux
  photovoltaïques en temps réel, avec des variations saisonnières.

- **Why ?** : Quels sont les systèmes externes qui ont une influence
  sur la mission ou la raison d'être du système ? Les data center qui
  utilisent cette énergie pour alimenter leur serveur et les
  fournisseurs d'électricité qui peuvent racheter l'énergie produite.

- **How ?** : Quels sont les systèmes externes qui ont une influence
  sur les composants du système cible ? L'énergie solaire détermine en
  grande partie quel type de semi-conducteur sera utilisé dans la
  conception des cellules photovoltaïques également affectés par les
  conditions météorologiques. Le logiciel de monitoring embarqué
  permettant un suivi en temps réel et l'optimisation de la production
  d'énergie peut être influencé par les exigences spécifiques du
  réseau électrique.

Chacune de ces parties prenantes a des intérêts et des contraintes
spécifiques qui doivent être pris en compte dans la conception et
l'exploitation des systèmes photovoltaïques.

Il est à noter que de nouvelles parties prenantes peuvent intervenir au
cours du cycle de vie du système selon les évolutions technologiques,
réglementaires ou économiques.

## Diagramme de contexte

Le diagramme de contexte permet de visualiser les interactions entre le
système et son environnement, en identifiant les éléments extérieurs qui
influent sur le système ou qui sont influencés par lui. Il permet de
délimiter le périmètre du système et de définir les interfaces avec les
éléments extérieurs. Ici, il a été organisé de manière à positionner
respectivement les parties prenantes et systèmes externes, dans les
quatre quadrants du diagramme :

- **À gauche** : les entrées du système;

- **À droite** : les sorties du système;

- **En haut** : les principales contraintes ;

- **En bas** : les principales ressources.

![Diagramme de contexte du système des panneaux
photovoltaïques](diagramme_de_contexte.png)

Le système transforme l'entrée énergie solaire en sortie pour les
fournisseurs d'électricité et les data center autrement dit en énergie
électrique consommable, à l'aide de l'équilibre du systeme (Balance of
System BOS), des fabricants, techniciens et ingénieurs systèmes tout en
tenant compte des contraintes environnementales, exigences du réseau et
des normes.

# Analyse et modélisation opérationnelle

## Expression des besoins

Les besoins (ou exigences opérationnelles) du système sont définis par
les fonctions qu'il doit remplir pour satisfaire les attentes des
parties prenantes. Ces besoins ne s'expriment pas dans le langage du
système cible lui-même mais dans le langage du milieu exterieur en
l'occurence le réseau de distribution et l'environnement. Dans ce
projet, les besoins opérationnels du système des panneaux
photovoltaïques peuvent être enoncés de la manière suivante :

- L'énergie solaire doit pouvoir être captée et convertie en
  électricité

- Les serveurs des data center doivent être alimentés en électricité
  de manière fiable et continue y compris la nuit et les jours nuageux

- Les utilisateurs finaux doivent pouvoir disposer de leurs serveurs
  dédiés en tout temps sans interruption

- Le système global doit être capable de résister aux intempéries et
  aux conditions environnementales spécifiques

- L'onduleur doit recevoir de l'énergie en courant continu

- L'équilibre du système doit être capable de s'intégrer dans le
  réseau de distribution existant

- Les ingénieurs systèmes doivent être capable de suivre la production
  d'énergie des panneaux photovoltaïques

- Les fournisseurs d'électricité doivent être capable de racheter
  l'énergie produite par les panneaux photovoltaïques

- Le réseau électrique doit être capable de supporter l'injection
  d'énergie produite par les panneaux photovoltaïques (Courant
  alternatif, tension\...)

## Diagramme de scénario opérationnel

Ci-dessous, le diagramme de scénario opérationnel permet de visualiser
les interactions entre les parties prenantes et le système, en
identifiant les actions et les échanges d'informations qui se produisent
lors de l'utilisation du système. Il permet de décrire de manière
synthétique le fonctionnement du système dans son environnement pour
l'opération de production d'énergie électrique à partir de l'énergie
solaire.

![Diagramme de scénario opérationnel du système des panneaux
photovoltaïques](diagramme_de_scenario_operationnel.png)

# Analyse et modélisation fonctionnelle

## Exigences fonctionnelles

Les exigences fonctionnelles sont les propriétés et les comportements
attendus du système. Elles sont exprimées dans le langage fonctionnel du
système sous la forme : \"Le système cible doit faire quelque chose avec
une certaine performance (en terme de fonctionnalités) durant un
fonctionnement donné\". Les exigences fonctionnelles du système des
panneaux photovoltaïques sont les suivantes :

- Le panneau photovoltaïque doit produire une puissance de 300 W crête
  (Wp)

- Le panneau photovoltaïque doit être capable de fonctionner à une
  température de -40°C à 85°C

- Le panneau photovoltaïque doit être capable de résister à des vents
  de 240 km/h

- Le panneau photovoltaïque doit être capable de résister à une charge
  de neige de 5400 Pa

- Le panneau doit être conçu pour résister à l'humidité et aux
  intempéries, avec une protection contre les infiltrations d'eau
  selon le standard IP65.

- Le système de monitoring embarqué doit être capable de suivre la
  production d'énergie en temps réel avec une précision de 1

- Le système de monitoring embarqué doit mettre à jour les
  informations toutes les 5 minutes.

- Le système de monitoring embarqué doit indiquer si la performance
  tombe sous 80

- Les panneaux doivent garantir une durée de vie d'au moins 25 ans
  avec une perte de rendement inférieure à 0,5

- Les connecteurs MC4 du panneau doivent être capables de supporter
  une tension de 1000 V et un courant de 30 A.

- Les connecteurs MC4 doivent avoir une capacité de
  connexion/déconnexion de 1000 cycles.

## Diagramme d'états

Un diagramme d'états est une représentation dynamique du comportement
d'un système, montrant les différents états dans lesquels un objet peut
se trouver et les transitions entre ces états. Le diagramme ci-dessous
représente les états possibles du système des panneaux photovoltaïques,
en fonction de son mode de fonctionnement :

![Diagramme d'états du système des panneaux
photovoltaïques](diagramme_etat.png)

## Diagramme de scénario fonctionnel

Un diagramme de scénario fonctionnel associé au système cible est une
représentation dynamique des interactions qui ont lieu entre les
fonctions du système, et éventuellement l'environnement, pendant un
certain mode de fonctionnement. Le diagramme ci dessous est associé avec
le mode de fonctionnement \"actif\" des panneaux photovoltaïques.

![Diagramme de scénario fonctionnel du système des panneaux
photovoltaïques](diagramme_de_scenario_fonctionnel.png)

# Analyse et modélisation organique

## Exigences organiques

Les exigences organiques définissent les caractéristiques techniques et
les contraintes de conception du système. Elles sont liées aux
composants physiques du système et aux interactions entre ces
composants. Les exigences organiques du système des panneaux
photovoltaïques sont les suivantes :

- Les panneaux doivent être constitués de cellules photovoltaïques en
  silicium monocristallin pour une efficacité maximale.

- Les panneaux doivent être montés sur des structures fixes

- Les panneaux doivent être orientés de manière à maximiser
  l'exposition au soleil

- Les panneaux doivent être fabriqués avec un cadre en aluminium
  anodisé, verre trempé et boîtier étanche IP65 pour la résistance aux
  intempéries.

- Les panneaux doivent être équipés de diodes de dérivation pour
  minimiser les pertes d'énergie.

- Les panneaux doivent être équipés d'un système de monitoring
  embarqué pour suivre la production d'énergie en temps réel.

- Les panneaux doivent être équipés de connecteurs MC4 pour faciliter
  l'installation.

## Diagramme de scénario organique

Ce diagramme permet de visualiser les interactions entre les composants
du panneau photovoltaïque et éventuellement l'environnement, lors de
l'opération du système. Il decrit de manière synthétique et concrète le
fonctionnement interne du système pour la production d'énergie
électrique à partir de l'énergie solaire qui est comme suit :

1.  **Environnement $\rightarrow$ Cellules photovoltaïques** : L'énergie
    solaire (lumière) est reçue par les cellules photovoltaïques.

2.  **Cellules photovoltaïques $\rightarrow$ Cellules photovoltaïques**
    : Les cellules photovoltaïques convertissent l'énergie solaire en
    courant continu (DC).

3.  **Cellules photovoltaïques $\rightarrow$ Cadre** : Les cellules sont
    montées sur un cadre, qui récupère et maintient l'énergie générée
    par les cellules.

4.  **Cellules photovoltaïques $\rightarrow$ Boîtier IP65** : Le boîtier
    protège les cellules contre les intempéries et assure l'étanchéité
    du système.

5.  **Boîtier IP65 $\rightarrow$ Cellules photovoltaïques** : Le boîtier
    assure une protection contre les conditions environnementales (eau,
    poussière, etc.).

6.  **Cellules photovoltaïques $\rightarrow$ Cablage** : Le câblage
    interne transporte l'énergie produite par les cellules vers les
    connecteurs.

7.  **Cablage $\rightarrow$ Connecteurs MC4** : Les câbles sont
    connectés aux connecteurs MC4, qui transmettent le courant continu
    vers le système de monitoring ou d'autres composants externes.

8.  **Connecteurs MC4 $\rightarrow$ Système de monitoring embarqué** :
    Le système de monitoring reçoit des informations sur les
    performances du panneau (tension, courant).

9.  **Système de monitoring embarqué $\rightarrow$ Connecteurs MC4** :
    Le système de monitoring analyse la performance des connecteurs et
    surveille leur bon fonctionnement.

![Diagramme de scénario organique du système des panneaux
photovoltaïques](diagramme_de_scenario_organique.png)
