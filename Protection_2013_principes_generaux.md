**Contenu**

[I. Contexte et objet [3](#contexte-et-objet)](#contexte-et-objet)

[Contexte [3](#contexte)](#contexte)

[Objet [3](#objet)](#objet)

[II. Type de protection [3](#type-de-protection)](#type-de-protection)

[III. Glossaire [4](#glossaire)](#glossaire)

[Application technique
[4](#application-technique)](#application-technique)

[Client [4](#client)](#client)

[Domaine [4](#domaine)](#domaine)

[Licence [5](#licence)](#licence)

[Modules fonctionnels [5](#modules-fonctionnels)](#modules-fonctionnels)

[Modules commerciaux [6](#modules-commerciaux)](#modules-commerciaux)

[Solutions commerciales
[6](#solutions-commerciales)](#solutions-commerciales)

[Solutions client [6](#solutions-client)](#solutions-client)

[Volumétries [6](#volumétries)](#volumétries)

[Typologie client [6](#typologie-client)](#typologie-client)

[Activité(s) [7](#activités)](#activités)

[Pays et langue [7](#pays-et-langue)](#pays-et-langue)

[Produit blanc [7](#produit-blanc)](#produit-blanc)

[Date de fin de validité
[7](#date-de-fin-de-validité)](#date-de-fin-de-validité)

[IV. Dépendance par rapport à la machine
[8](#dépendance-par-rapport-à-la-machine)](#dépendance-par-rapport-à-la-machine)

[Principe [8](#principe)](#principe)

[Installation identifiée
[8](#installation-identifiée)](#installation-identifiée)

[Installation versus activation
[8](#installation-versus-activation)](#installation-versus-activation)

[Tolérance [8](#tolérance)](#tolérance)

[Licences non liées à la machine
[9](#licences-non-liées-à-la-machine)](#licences-non-liées-à-la-machine)

[Module commercial [9](#_Toc41320387)](#_Toc41320387)

[Solution commerciale [9](#solution-commerciale)](#solution-commerciale)

[Solution client [10](#solution-client)](#solution-client)

[V. Les diverses applications impliquées dans la protection 2013
[11](#les-diverses-applications-impliquées-dans-la-protection-2013)](#les-diverses-applications-impliquées-dans-la-protection-2013)

[IsaGISA [11](#isagisa)](#isagisa)

[IsaBOSC [11](#isabosc)](#isabosc)

[IsaGestLic [11](#isagestlic)](#isagestlic)

[IsaGenLic [11](#isagenlic)](#isagenlic)

[IsAdminFAH [12](#isadminfah)](#isadminfah)

[Licence registration
[12](#licence-registration)](#licence-registration)

[Jeton interne [12](#jeton-interne)](#jeton-interne)

[VI. Environnements et connexion
[12](#environnements-et-connexion)](#environnements-et-connexion)

[VII. Historique [13](#historique)](#historique)

# Contexte et objet

## Contexte {#contexte .unnumbered}

La protection a pour objectif de contrôler que nos clients utilisent
leur logiciel conformément à ce qu'ils ont acheté.  La réécriture des
applications Isagri a nécessité une réécriture complète du système de
protection « Protection 2013 »). Sa mise en œuvre est complexe et fait
intervenir de nombreuses équipes (Dev outils, DRI « GISA » et « GRC »,
MktM, MktPr, Dev Progiciel, CQL Progiciel, ADV -- Clientèle, SL, IAH,
\... France et export).

Ce document fait partie d'une série de documentations expliquant le
fonctionnement et la mise en œuvre de la protection 2013 dans les
applications Convergence. Pour une vision générale des documentations
disponibles, cf.
[ici](http://projectsrv2010/sites/Coordination/SystemeDocumentaire/_layouts/DocIdRedir.aspx?ID=R6RHQAPNUWS3-52-255).

## Objet {#objet .unnumbered}

Ce document présente les grands principes relatifs à la protection 2013
(concepts mis en œuvre, applications concernées dans l'administration
des licences, ...). Il est un préambule indispensable à la compréhension
des autres documents

# Type de protection

La nouvelle génération du système de protection des applications Isagri
(« Protection 2013 ») est une **protection de type logiciel** et non pas
une protection physique (clé USB, ...).

**Une version qui reconnaît la protection « 2013 » ne reconnaît plus que
celle-ci. La compatibilité avec les protections antérieures (protection
2007, code CPVN, clés IKey, ...) est supprimée. Et cela quelle que soit
la situation** : France / export ; poste connecté ou non à Internet ;
client connu d'Isagri ou non ; client individuel ou prestataire ; ...

# Glossaire

## Application technique {#application-technique .unnumbered}

Il s\'agit du logiciel au sens de la protection (et pas forcément au
sens commercial).

Ainsi, du point de vue de la protection,

-   IsaRevise et IsaCotis ne sont pas des applications techniques (mais
    des modules d'IsaCompta)

-   IsaFact et IsaVigne sont une seul et même application technique

-   IsaCompta indiv et IsaCompta prestataire sont 2 applications
    techniques différentes

## Client {#client .unnumbered}

Le client de la licence est la structure juridique qui a acquis le droit
d'**utiliser** le logiciel (qui peut être distincte de la structure
juridique facturée ou livrée des maj).

## Domaine {#domaine .unnumbered}

Le domaine une entité transversale aux divers logiciels que possède le
client, contenant une ou plusieurs entreprises **d'un même client**,
entreprises qui partage(nt) des données au sein d'un même logiciel
Isagri (ex : les mêmes matériels en PV, les mêmes articles en GC, ...)
ou entre logiciels (ex : le plan comptable entre IsaCompta et IsaPaye).

Pour que les partages de données entre logiciels fonctionnent de manière
automatique (par appels de services et non pas par export puis import),
les données correspondantes doivent être gérées dans le même domaine
dans les différents logiciels possédés par le client : l'entreprise X ne
peut être gérée dans le domaine 1 dans IsaCompta et dans le domaine 2
dans Geofolia, sous peine de ne pouvoir partager des données communes
aux 2 logiciels pour cette entreprise.

**En règle générale, un client a un seul domaine et y gère toutes ses
entreprises.** Cette règle générale est appliquée par défaut lors de
l'achat d'un 2ème logiciel (si le client possède déjà un domaine pour un
logiciel X, par défaut, on lui rattache le même domaine si il achète le
logiciel Y).

En pratique toutefois, un même client peut avoir besoin de plusieurs
domaines dans les cas suivants :

-   Il souhaite gérer certaines de ses entreprises de manière
    complètement séparée des autres. Par ex, un client a 2
    exploitations, distinctes géographiquement, qui ne partagent aucun
    facteur de production -\> il doit gérer 2 domaines (et donc disposer
    de 2 licences) Geofolia

-   Il existe une contrainte technique qui empêche de partager des
    données entre une BDD installée en local et une BDD installée en
    FAH. Cette contrainte oblige un client à gérer des domaines
    différents entre 2 applications dont l'une est installée en FAH (ex
    Geofolia) et l'autre en local (ex : IsaGC, qui ne gèrera le FAH
    qu'en fin de réécriture)

    -   16/01/2020 : cette contrainte technique est en train d\'être
        levée ; une fois qu\'elle le sera, un même domaine pourra
        accueillir des données en local pour un logiciel et en FAH pour
        un autre

Pour un prestataire, les données de ses propres clients (dossiers
comptables en IsaCompta, entreprises en Paye, exploitations en Geofolia)
sont gérées dans le(s) domaine(s) du prestataire (le prestataire n'a pas
un domaine pour chacun de ses clients). Il en va de même pour celles des
agriculteurs en mode partenaire dans Geofolia ou des entreprises
utilisatrices d\'Isacompta collaboratif

Pour + de détails, cf. la [documentation spécialisée sur le
sujet](http://projectsrv2010/sites/Coordination/SystemeDocumentaire/_layouts/DocIdRedir.aspx?ID=R6RHQAPNUWS3-52-271)

## Licence  {#licence .unnumbered}

Une licence définit les droits à utilisation pour **un logiciel, sur un
domaine, pour un client utilisateur** de ce domaine, en fonction de ce
qu'a acheté le client.

Un client dispose **d'une et d'une seule licence** pour un même logiciel
et un même domaine, même s'il a effectué plusieurs achats successifs
(ex en Geofolia, il a acheté un « Geofolia bureau sans carto ni
fumure » puis l'option « Fumure », il dispose d'une seule licence
Geofolia qui lui donne le droit d'utiliser les fonctionnalités de
« Geofolia bureau » avec la fumure)

Outre l\'application technique, le domaine, le client, la licence porte
diverses informations qui vont permettre à l'application de contrôler
ses droits effectifs. Ce sont :

-   Les modules fonctionnels autorisés (cf. [Modules
    fonctionnels](#modules-fonctionnels))

-   Les volumétries autorisées (cf. [Volumétries](#modules-commerciaux))

-   La « typologie » du client (cf. [Typologie
    client](#typologie-client))

-   La ou les activités (cf. [Activité(s)](#activités))

-   Le pays et langue (cf. [Pays et langue](#pays-et-langue))

-   Le nom du produit blanc (cf. [Produit blanc](#produit-blanc))

-   Une éventuelle date de fin de validité (cf. [Date de fin de
    validité](#date-de-fin-de-validité))

-   Le nombre d'installations autorisées (cf. [Dépendance par rapport à
    la machine](#dépendance-par-rapport-à-la-machine))

## Modules fonctionnels {#modules-fonctionnels .unnumbered}

Les modules fonctionnels correspondent aux différentes fonctionnalités
disponibles dans l'application.

Ex de modules fonctionnels :

-   Fumure, carto, liaison ISA360, ... en Geofolia

-   Charges engagées, échéances techniques, analyse de groupe, ... en
    IsaG.I.

-   Emprunts, stocks, ... en compta

Ils sont définis par l\'équipe de développement et doivent être pensés
pour être **stables dans le temps** : une fonctionnalité du produit ne
devrait pas changer de module fonctionnel en fonction de l'évolution de
la politique commerciale. Par contre, on peut bien entendu ajouter de
nouveaux modules fonctionnels au fur et à mesure de la disponibilité de
nouvelles fonctionnalités dans les nouvelles versions du logiciel. Le
respect de cette préconisation permet de faire évoluer la politique
commerciale sans nécessiter de développements dans l'application (et
donc sans renvoyer de versions aux clients existants).

La licence indique pour chaque module fonctionnel si le client y a droit
ou pas.

## Modules commerciaux {#modules-commerciaux .unnumbered}

Cf.
[Definition_des_solutions_commerciales](file:///C:\Temp\Protection_2013_definition_des_solutions_commerciales.docm#Module_commercial)

## Solutions commerciales {#solutions-commerciales .unnumbered}

Cf.
[Definition_des_solutions_commerciales](file:///C:\Temp\Protection_2013_definition_des_solutions_commerciales.docm#Solution_commerciale)

## Solutions client {#solutions-client .unnumbered}

Cf.
[Definition_des_solutions_commerciales](file:///C:\Temp\Protection_2013_definition_des_solutions_commerciales.docm#Solution_client)

## Volumétries {#volumétries .unnumbered}

La politique commerciale peut prévoir des tarifs différents selon la
volumétrie gérée par le client pour certains concepts. Exemples :

-   Nombre de vaches en Troup\'O, de truies en Pig\'up

-   Nombre d\'e-mails envoyés par an depuis la GC

-   Nombre d\'utilisateurs dans différents logiciels

Pour chacune de ces natures de volumétries, un plafond est défini en
fonction de ce qu\'a acheté le client. La licence contrôle que ce
plafond n\'est pas dépassé

Les volumétries achetées par le client et les natures de volumétries
correspondantes sont véhiculées par la licence (à charge de
l'application de calculer où on en est).

Les limites de volumétries sont définies pour le domaine. En cas
d'installation de plusieurs BDD, les limites définies sont valables pour
chacune des BDD (il n'y a pas de cumul entre les diverses BDD).

Les volumétries achetées peuvent être définies par activité

> Ex : dans le cas de Troup\'O, pour la nature de volumétrie « Nombre de
> vaches »; on peut renseigner, pour un même domaine, un nombre pour
> l'activité « Bovin lait » (il s\'agit de vaches laitières) et un autre
> nombre pour l'activité « Bovin viande » (il s\'agit de vaches
> allaitantes)

Le nombre d'**utilisateurs** est une des natures de volumétrie gérées.
Il s'agit d'un nombre **d'utilisateurs déclarés** (càd. définis dans
l'application et autorisés à utiliser celle-ci). Il n'y a pas de
contrôle possible d'un nombre **d'utilisateurs simultanés.**

Le nombre d'installations autorisé n'est pas une nature de volumétrie
mais est contrôlé par un autre mécanisme (cf. [Dépendance par rapport à
la machine](#dépendance-par-rapport-à-la-machine)).

## Typologie client {#typologie-client .unnumbered}

La licence définit également la typologie du client. Il en existe 4,
communes à toutes les applis

-   Individuel

-   Organisme (= prestataire)

-   Ecole

-   Isagri (typologie utilisée pour les licences internes destinées à
    gérer les référentiels)

Une licence porte 1 et 1 seule typologie client

Cela permet à l'application d'adapter son fonctionnel (ex :
fonctionnement particulier pour les écoles)

## Activité(s) {#activités .unnumbered}

La licence porte également la notion d'activité du client (le marché).
Les activités sont spécifiques à l\'application technique

> Ex :

-   En Geofolia, on a les activités Grand cultures, Elevage,
    Viticulture ;

-   En Ruminants, on a les activités Bovin lait, Bovin viande, Ovin
    lait, Ovin viande, Caprins, ...

Une licence peut porter de 0 à n activités.

Cela permet à l'application d'adapter son vocabulaire ou son fonctionnel
en fonction de la ou des activités du domaine (ex : parler d'agnelage ou
de vêlage en ruminants selon que l'activité est Bovin ou Ovin ; adapter
le nom du logiciel, ...)

## Pays et langue {#pays-et-langue .unnumbered}

La licence définit la culture (pays et langue) **de fonctionnement de
l'application** (qui conditionne l'activation de tel fonctionnement
spécifique au pays, le référentiel utilisé, ...). Ils peuvent être
différents du pays de résidence du client ou de la langue d'affichage de
l'IHM.

> Ex : on vend Geofolia à un client français pour une exploitation qu'il
> possède en Roumanie. La licence doit être générée pour la Roumanie /
> le Roumain pour que les spécificité Roumaines soient gérées. Mais le
> client peut utiliser l'application avec l'IHM en Français

## Produit blanc {#produit-blanc .unnumbered}

Un produit blanc est un produit vendu par un distributeur sous sa propre
marque.

> Ex : Weelogic pour Isacompta

L'application doit être « customisée » (iconographie, nom du logiciel,
fonctionnalités accessibles...).

La licence contient le code du produit blanc correspondant. Elle peut
ainsi se baser sur cette information pour adapter son fonctionnement.
Pour le produit standard Isagri, ce code n'est pas renseigné.

## Date de fin de validité {#date-de-fin-de-validité .unnumbered}

La licence peut porter une date de fin de validité pour gérer les
licences à durée limitée : contrats essais, \...

# Dépendance par rapport à la machine

## Principe {#principe .unnumbered}

Pour empêcher un client de diffuser sa licence, on limite le nombre
d\'installations autorisées pour une même licence, selon ce qu\'a acheté
le client (« nombre de licences » dans IsagestLic).

> Plutôt que de « nombre de licences » dans IsaGestLic, il vaudrait
> mieux parler de « Nombre d'installations principales autorisées »

## Installation identifiée {#installation-identifiée .unnumbered}

On identifie l'instance de **SQL Server** (le moteur de base de données)
et non pas les postes \"clients\".

Cela a pour conséquence, qu\'avec une seule \"installation\", un client
en FAH (ou en réseau local) peut accéder à son application depuis autant
de postes qu\'il le souhaite (puisqu\'il utilise toujours la même
instance de SQL server). En règle générale (y compris les prestataires
en multi-sites ou avec des collaborateurs en mobilité ainsi que les
\"saisies décentralisées\" en GC, grâce à la notion de licence
secondaire), **un client n\'a donc besoin que d\'une seule
installation.**

L\'instance SQL server est identifiée via une clé générée aléatoirement
lors de l'installation de SQL server. Il n'y a pas de lien avec les
composants physiques de la machine (carte réseau, carte mère, ...). Un
changement de carte réseau par exemple ne modifiera pas l'identifiant de
la machine. Par contre, un formatage du serveur de BDD entraînera la
génération d'une nouvelle clé lors de la réinstallation de SQL server et
on considèrera donc qu'il s'agit d'une nouvelle machine.

## Installation versus activation {#installation-versus-activation .unnumbered}

On distingue l'installation de licence et l'activation de celle-ci.

L'**installation** consiste à **installer la licence dans la BDD SQL
Server**.

> L'installation est obligatoire pour que le client puisse commencer à
> utiliser le logiciel (sans licence installée, le logiciel est
> inutilisable puisqu'il ne connaît pas le domaine, les modules
> autorisés ou non, ...). Une fois la licence installée, le client peut
> utiliser l'application pendant une durée limitée (14 j). Il doit
> activer sa licence pour pouvoir continuer à utiliser son logiciel
> au-delà.

L'**activation** permet de **lier la licence à la machine sur laquelle
elle est installée**.

> Pour cela, le client doit récupérer auprès d'Isagri une clé
> d'activation dépendante de l\'instance SQL Server utilisée.
>
> Une fois la licence activée pour l\'instance SQL Server, l'application
> peut être utilisée (jusqu'à la version majeure suivante - qui
> nécessitera une réactivation - ou jusqu'à la date de fin de validité
> de la licence si elle en a une)
>
> L\'activation est complètement transparente pour le client dans le cas
> d'un poste connecté à Internet.

## Tolérance {#tolérance .unnumbered}

Comme pour la protection 2007, on n'a pas prévu de désactivation de la
licence en cas de changement de machine (en effet un tel système
impliquerait une manipulation sur la machine obsolète mais celle-ci peut
ne plus fonctionner ou ne plus être disponible). En conséquence, un
système de **tolérance** a été mis en place : le client peut
temporairement (jusqu'à la version suivante) utiliser son application
sur une machine de plus que ce qu'il a acheté. Au-delà de la tolérance
(tentative d'activation sur plus d'une machine excédentaire ou même
machine excédentaire utilisée pour 2 versions), le client est bloqué (ne
peut activer).

Ex :

> Le client a droit à 2 installations ;
>
> Il active la version 10.00 pour le poste A et le poste B ;
>
> Il remplace sa machine B par une nouvelle machine C :

-   Il peut activer la version 10.00 sur cette machine C grâce à la
    tolérance

-   On l'avertit qu'il dépasse son quota d'installations autorisées mais
    ce message ne bloque pas l'installation sur la machine C.

-   Techniquement, rien ne l'empêche de continuer à utiliser la version
    10.00 sur la machine B.

> Il installe la version 11.00 (soit une nouvelle version majeure
> nécessitant une réactivation) :

-   Il peut l'activer uniquement sur 2 postes parmi A, B et C (...ce qui
    est cohérent car il n\'est plus censé utiliser B).

-   Il pourra toutefois bénéficier d'une nouvelle tolérance sur une
    machine D (mais sera à nouveau bloqué à 2+1 machines avec la version
    12.00).

En résumé :

-   Ce client sera toujours limité à 2+1=3 activations par version
    majeure associée à cette licence ;

-   Un message d'avertissement non-bloquant devra l'informer du
    dépassement de quota lors d'une troisième activation ;

-   Une quatrième activation sera impossible.

## Licences non liées à la machine {#licences-non-liées-à-la-machine .unnumbered}

La majorité des licences sont liées à la machine.

Il est toutefois possible de définir des licences non liées à la
machine, qui peuvent donc être installées sur autant de machines que
l'on veut. C'est par exemple le cas des licences de démo, des licences
écoles, \... Dans ce cas, l\'ADV va renseigner une validité limitée dans
le temps pour limiter le risque de piratage.

Une licence non liée à la machine n'est pas à activer. L'installation de
celle-ci suffira pour utiliser le logiciel le temps de sa validité (sur
autant de serveurs de BDD que l'on veut donc). Pour des raisons de
sécurité, de telles licences doivent toujours avoir une date de fin de
validité

## Module commercial {#module-commercial .unnumbered}

Cf.
[Protection_2013_definition_des_solutions_commerciales.docm](http://projectsrv2010/sites/Coordination/SystemeDocumentaire/DocOfficielsSansValidation/Protection_2013_definition_des_solutions_commerciales.docm)

## Solution commerciale {#solution-commerciale .unnumbered}

Cf.
[Protection_2013_definition_des_solutions_commerciales.docm](http://projectsrv2010/sites/Coordination/SystemeDocumentaire/DocOfficielsSansValidation/Protection_2013_definition_des_solutions_commerciales.docm)

## Solution client {#solution-client .unnumbered}

Cf.
[Protection_2013_definition_des_solutions_commerciales.docm](http://projectsrv2010/sites/Coordination/SystemeDocumentaire/DocOfficielsSansValidation/Protection_2013_definition_des_solutions_commerciales.docm)

# Les diverses applications impliquées dans la protection 2013

Diverses applications sont impliquées dans la diffusion des licences et
le contrôle de la conformité entre ce que le client utilise et ce qu'il
a acheté.

Initialisation du domaine Installation de la licence

Utilisation

Création du client

IsaGISA

IsaBOSC

Création du domaine Configuration de la licence

IsaGenLic

IsaGestLic

Activation

IsaGestic

Progiciel Isagri

Jeton interne

IsAdminFAH

Progiciel Isagri

Licence

Autre logiciel de facturation

Licence registration

Liste clients

Liste clients

## IsaGISA {#isagisa .unnumbered}

IsaGISA est l'application qui est utilisée pour la gestion et la
facturation des clients. C'est une application de type client lourd,
elle est principalement utilisée par l'équipe Administration Des Ventes
et par certaines filiales à l'export (Italie, Espagne, etc.). Elle est
gérée par l'équipe DRI-GISA.

## IsaBOSC {#isabosc .unnumbered}

IsaBOSC (Isa BackOffice Service Clients) est une application web qui
permet, comme son nom l'indique, d'administrer certains éléments liés au
service client. À ce jour elle dispose de deux grandes fonctionnalités :
la gestion de l'updater, service utilisé pour envoyer des mises à jour
aux clients via le web, et l'intégration des clients de l'export et des
filiales qui n'utilisent pas IsaGISA dans la base Isagri. Cette
application est également gérée par l'équipe DRI-GRC.

## IsaGestLic {#isagestlic .unnumbered}

IsaGestLic est une application web qui permet de créer les licences
clients selon ce qu'ils ont acheté. Elle gère également la création des
domaines dans le SI Isagri (attribution d'un n° unique, rattachement au
client). Elle est utilisée par le marketing marché pour mettre en place
tous les paramétrages nécessaires à la génération des licences et par
l'ADV pour y créer les domaines et licences sur base des bons de
commandes des clients (et cela par Isagri France mais aussi par les
filiales à l'export et par les autres distributeurs). L'application est
développée et maintenue par l'équipe DRI-GRC.

## IsaGenLic {#isagenlic .unnumbered}

IsaGenLic est un utilitaire qui permet de générer des licences
« internes » destinées à être utilisées par les collaborateurs Isagri
(Support, CIM, AET) pour effectuer des tests. Cela permet de ne pas
avoir à gérer des clients / des licences dans les outils de production
(IsaGISA et IsaGestLic). Cet utilitaire est géré par l'équipe Outils.

## IsAdminFAH {#isadminfah .unnumbered}

IsAdminFAH est une application gérée par la DRI qui permet d'administrer
les BDD **en FAH**. En particulier, elle automatise la création de
nouvelles BDD, l'initialisation des domaines dans ces BDD,
l'installation de la licence dans chaque domaine.

En mode local, ces fonctionnalités sont prises en charge par le
progiciel Isagri

## Licence registration {#licence-registration .unnumbered}

Licence registration est une application web qui permet aux clients
utilisant leur progiciel Isagri sur un poste non connecté à Internet
d'activer leurs licences en ligne (depuis un autre poste). Pour les
clients qui utilisent leur progiciel Isagri sur un poste connecté à
Internet, cette activation est transparente. Dans les 2 cas, les données
sont stockées dans IsaGestLic, de manière à contrôler le nombre
d'installations de l'application sur des PC différents.. Cette
application est gérée par l'équipe DRI-GRC

## Jeton interne {#jeton-interne .unnumbered}

Cet utilitaire développé par l'équipe Outils permet d'être authentifié
en tant que collaborateur Isagri et de pouvoir utiliser des licences
internes générées avec IsaGenLic ou d'utiliser la licence d'un client
sans l'activer.

# Environnements et connexion

La protection 2013 étant complexe, un environnement de démonstration a
été mis en place afin que les utilisateurs puissent effectuer différents
tests avant de réaliser les opérations directement en production. Les
versions de démonstration permettent également aux utilisateurs et aux
testeurs de tester les nouvelles fonctionnalités développées avant leur
passage en production.

Tous les utilisateurs ayant accès à la version de production d'une
application disposent également d'un accès sur la version de
démonstration (l'inverse n'est pas vrai).

Voici les adresses des différentes applications gérées par l'équipe
DRI-GRC (pour les autres applications renseignez-vous auprès des équipes
concernées).

  -----------------------------------------------------------------------------------------------------
                   **Démonstration**                           **Production**
  ---------------- ------------------------------------------- ----------------------------------------
  **IsaBOSC**      <http://demo.isabosc.groupeisagri.com/>     <http://isabosc.groupeisagri.com/>

  **IsaGestLic**   <http://demo.isagestlic.groupeisagri.fr/>   <http://isagestlic.groupeisagri.fr/>

  **Licence        <http://demo.isalicence.isagri.fr/>         <http://www.licence-registration.com/>
  registration**                                               
  -----------------------------------------------------------------------------------------------------

#  Historique

+------------+---------------------------------------------------------+
| > Date et  | > Détail des modifications apportées                    |
| > auteur   |                                                         |
| > des      |                                                         |
| > mod      |                                                         |
| ifications |                                                         |
+============+=========================================================+
| > 1        | > Corrections mineures                                  |
| 6/01/2020\ |                                                         |
| > D. Lemal |                                                         |
+------------+---------------------------------------------------------+
| > 0        | > Corrections de mise en forme                          |
| 3/07/2019\ |                                                         |
| > D. Lemal |                                                         |
+------------+---------------------------------------------------------+
| > 2        | > Correction mineure                                    |
| 0/06/2016\ |                                                         |
| > D. Lemal |                                                         |
+------------+---------------------------------------------------------+
| > 2        | > Ajout de la notion de produit blanc / de la langue    |
| 7/05/2016\ |                                                         |
| > D. Lemal |                                                         |
+------------+---------------------------------------------------------+
| > 1        | > Mise en forme pour publication dans le système        |
| 6/03/2016\ | > documentaire production                               |
| > D. Lemal |                                                         |
+------------+---------------------------------------------------------+
| > 2        | > Création                                              |
| 2/10/2015\ |                                                         |
| > D. Lemal |                                                         |
+------------+---------------------------------------------------------+
