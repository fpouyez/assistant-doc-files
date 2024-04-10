**Contenu**

[I. Contexte et objet [2](#contexte-et-objet)](#contexte-et-objet)

[Contexte [2](#contexte)](#contexte)

[Objet [2](#objet)](#objet)

[II. Prerequis [2](#prerequis)](#prerequis)

[III. Licences de tests [3](#licences-de-tests)](#licences-de-tests)

[IV. Postes internes [5](#postes-internes)](#postes-internes)

[V. Historique [9](#historique)](#historique)

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
[ici](http://projectsrv2010/sites/Coordination/SystemeDocumentaire/_layouts/DocIdRedir.aspx?ID=R6RHQAPNUWS3-52-255)

## Objet {#objet .unnumbered}

Ce document décrit les utilitaires qui existent pour tester la
protection 2013. Il s'adresse aux salariés (dev, test, SL), CIMs,
partenaires qui doivent tester le bon fonctionnement de la protection
2013.

Ce document est un document interne qui ne doit pas être diffusé à
l'extérieur de l'entreprise.

# Prerequis

Pour comprendre le présent document, il faut avoir lu le document
« [Protection 2013 : principes
généraux](http://projectsrv2010/sites/Coordination/SystemeDocumentaire/_layouts/DocIdRedir.aspx?ID=R6RHQAPNUWS3-52-256) »

# Licences de tests

Les développeurs, testeurs, formateurs ... ont besoin de licences « sur
mesure » pour pouvoir tester le bon fonctionnement de la protection (par
exemple pour vérifier la désactivation de tel bouton, menu, zone de
saisie, ... selon les modules fonctionnels présents dans la licence). Il
s'agit de licences de tests.

Elles ne sont pas gérées dans le SI Isagri (serait trop lourd de devoir
créer un client, un domaine, les solutions commerciales adéquates, ... )
mais sont construites sur mesure par le développeur, testeur, formateur,
... en fonction de ses besoins grâce à une application ad'hoc. Cette
application (IP.Licence.GenLic.Application.exe ou **IsaGenLic** en
abrégé pour « Application **Isa**gri de **gén**ération de **lic**ences)
est développée par l'équipe « Développement progiciel Outils » et est
disponible sur P:\\Outils\\Utilitaires\\IsaGenLic.

Elle offre 2 fonctionnalités : [Voir doc
d'utilisation](http://projectsrv2010/sites/Coordination/_layouts/DocIdRedir.aspx?ID=R6RHQAPNUWS3-23-884)

-   La possibilité de générer une licence de tests pour un domaine
    existant, en saisissant l'application concernées, les modules
    fonctionnels autorisés, les volumétries autorisées, le pays de
    fonctionnement, etc ... Ces licences de tests ne requièrent pas
    activation mais ne sont utilisables que sur des [postes
    internes](http://projectsrv2010/sites/Coordination/SystemeDocumentaire/DocOfficielsSansValidation/Protection_2013_fonctionnement_salarie.docm#_Postes_internes)
    (pour éviter leur diffusion à l'extérieur).

![](media/image1.png){width="6.663888888888889in"
height="4.504166666666666in"}

-   La possibilité de visualiser le contenu d'une licence existante

![](media/image2.png){width="6.504166666666666in"
height="4.408333333333333in"}

# Postes internes

### De quoi s'agit-il ? {#de-quoi-sagit-il .unnumbered}

Les développeurs, testeurs, CTL, CIMs, ... doivent pouvoir effectuer des
tests, maintenances, ... sur des jeux de données de clients. De ce fait,
le comportement des licences doit être particulier sur leur poste (par
exemple, il ne faut pas que l'utilisation d'un jeu de données de client
requière activation de la licence du client pour le poste du salarié en
« consommant » une installation au détriment du client).

Les postes en question sont identifiés comme « postes internes ».

Il peut s'agir de poste de salariés Isagri (du siège ou terrain), de
CIMs, de salariés de filiales, de salariés de partenaires (distributeurs
qui font du support), ...

### Comment un poste est-il reconnu comme poste interne ?  {#comment-un-poste-est-il-reconnu-comme-poste-interne .unnumbered}

Un jeton à jour doit être installé sur le poste concerné. Ce jeton est
spécifique au poste (ne peut donc être copié d'un poste à l'autre) et a
une durée de vie limitée à 2 mois.

2 étapes sont nécessaires

#### Identification du poste comme « potentiellement interne » {#identification-du-poste-comme-potentiellement-interne .unnumbered}

Pour automatiser la recherche de jeton, l'utilisateur doit lancer sur
son poste l'application « InternalProtectionDeployment.exe »
(application disponible sur T:\\Installations des applications
communes\\InternalProtection2013). A noter que cette application est
lancée par la DRI à l'initialisation de tout nouveau poste salarié
(équipes du siège ou distantes). Cela a pour effet de «  marquer » le
poste comme « potentiellement interne »

C'est le poste où s'exécute la couche « IHM » qui est identifié comme
interne ou non

InternalProtectionDeployment.exe /U « démarque » le poste comme
« potentiellement interne ». La recherche de jeton poste interne n'est
plus faite.

**ATTENTION** : merci d'utiliser la dernière version
d'InternalProtectionDeployment avant d'utiliser l'option /U  car les
versions précédentes de /u provoquent des effets de bord conduisant
indirectement à l'invalidation des licences déjà activées en plus de la
désinstallation du jeton interne.

La dernière version date de Janvier 2017 : version 6.46.0 de l'exe (clic
droit Propriétés/Détails dans l'explorateur), qui déploie la version
1.0.5 de la dll JetonInterne2013.dll (T:\\Installations des applications
communes\\InternalProtection2013\\).

Le traitement qui provoquait cet effet de bord fait maintenant l'objet
d'une commande distincte : /ResetIdMachine, qui ne devrait qu'être
rarement utilisée sans un avis préalable de la RCP Protection.

#### Rapatriement du jeton {#rapatriement-du-jeton .unnumbered}

Sur un poste marqué comme « Potentiellement interne », on déclenche
automatiquement, lors de l'entrée dans une application Isagri protégée
par la protection 2013, le rapatriement sur le poste d'un nouveau jeton
si nécessaire (absence de jeton ou jeton présent mais expiré ou dont la
date d'expiration est proche : \<= 30 jours). Un poste d'un client
n'étant pas marqué comme « potentiellement interne », on ne cherche donc
pas à y rapatrier un jeton interne.

Le rapatriement du jeton est complètement transparent si le poste est
connecté au réseau interne Isagri au moment de la recherche.

Si ce n'est pas le cas (poste de commerciaux, de CIMs, de salariés de
filiales), l'utilisateur est invité à s'authentifier (login et mots de
passe Active Directory) pour pouvoir récupérer un jeton valide.

![jeton_nouvelle_version](media/image3.png){width="3.0319444444444446in"
height="1.5597222222222222in"}

Tous les utilisateurs de postes internes (y compris CIMs, salariés de
filiales) doivent donc être connus de l'AD et rattachés au groupe
adéquat par la DRI

Une fois obtenu, le jeton est valable 2 mois (même si le poste n'est pas
connecté au réseau Isagri ou à Internet : poste de formateur qui part en
clientèle, ...) pour le poste en question. En cas de changement de
poste, un nouveau jeton est requis.

La recherche de jeton est exécutée 1 fois par mois au maximum.

Ce fonctionnement permet de bloquer au bout de 2 mois maximum les
salariés, CIMs, distributeurs, ... qui ont quitté l'entreprise ou rompu
leur contrat.

26/04/2018 :

Pour éviter de devoir gérer dans notre AD des comptes pour des
utilisateurs externes à l'entreprise qui auraient besoin d'un jeton
interne (c'est le cas de quelques clients prestataires qui ont besoin de
remonter des sauvegardes de leurs clients équipes en gestion commerciale
pour intervenir sur le dossier en question puis le renvoyer au client),
une évolution a été apportée par la DRI pour permettre de créer des
utilisateurs de jetons internes en dehors de l'AD.

Pour cela, accéder à IsaBOSC (<http://isabosc.groupeisagri.com>) puis
menu « Gestion des utilisateurs », « Jeton interne » (accès est réservé
à D. Lemal et T. Hardion)

Pour créer un utilisateur, saisir un identifiant et un mot de passe.

![cid:image001.png@01D3DD49.B79BABA0](media/image4.png){width="4.125in"
height="2.0520833333333335in"}

Le mot de passe peut aussi être généré aléatoirement en cliquant sur le
lien « générer » (génère un mot de passe de 10 caractères
alpha-numériques + symboles). Attention, une fois l'utilisateur
enregistré, on ne peut plus voir son mot de passe. Par contre, on peut
modifier le mot de passe en cliquant sur « Editer » de la ligne
correspondante dans le tableau :

![cid:image002.png@01D3DD49.B79BABA0](media/image5.png){width="7.114583333333333in"
height="1.8377646544181978in"}

Pour obtenir le jeton interne, l'utilisateur ainsi créé suit la même
procédure qu'un salarié non connecté au réseau interne Isagri : il
renseigne son identifiant et le mot de passe qui lui a été communiqué.

### Quelles particularités de fonctionnement ? {#quelles-particularités-de-fonctionnement .unnumbered}

Pour qu\'une poste soit considéré comme poste interne, 2 conditions sont
nécessaires :

-   Le poste doit être \"potentiellement\" interne : on y lancé
    InternalProtectionDeployment.exe

-   Le jeton poste interne doit être présent et valide (correspondre à
    la machine courante et ne pas avoir expiré)

Il y a 4 particularités pour les postes internes.

-   On peut utiliser un domaine de client avec la licence correspondante
    (contenue dans la sauvegarde que l'on aura récupérée du client) sur
    un poste interne sans devoir l'activer (le poste interne est
    toujours reconnu comme une machine valide pour la licence).

-   Sur un poste interne, si la date de péremption du logiciel ou la
    date de fin de validité de la licence approche, l'affichage du 1^er^
    message d'avertissement ne déclenche pas le compte à rebours pour le
    blocage effectif (sinon, le client qui remonterait la sauvegarde de
    ses données que le CTL lui a renvoyée après une maintenance
    risquerait de se retrouver bloqué à l'entrée dans son domaine, sans
    avoir vu le message d'avertissement au préalable).

-   Une licence démo n'a pas de date d'expiration sur un poste interne

-   Une licence de test (qualifiée comme tel dans IsaGenLic) ne peut
    être utilisée que sur un poste interne

### Utilisation de vrai licence client pour les tests (Maj du 26/02/2021)  {#utilisation-de-vrai-licence-client-pour-les-tests-maj-du-26022021 .unnumbered}

Dans le cadre de l'enchantement client, une évolution a été faite
récemment pour les applications en mode hébergées (FAH)

Cette évolution consiste à réaliser une activation silencieuse de la
licence, ce qui évite tout simplement de proposer cette étape visuelle
d'activation pour les clients :

![](media/image6.png){width="6.09375in" height="3.8333333333333335in"}

En effet, cette étape est inutile pour le client étant donné que
l'activation d'une licence FAH entraine l'association lien machine sur
nos propres serveurs hébergés et non pas un lien avec la machine du
client.

Dans le parcours d'un client FAH, celui-ci reçoit des identifiants de
connexion par mail et son domaine est déjà initialisé par nos soins, il
n'a « juste » qu'à saisir ses identifiants pour s'authentifier dans son
application et n'a pas à réaliser des étapes supplémentaires
d'initialisation de son domaine/licence.

Cette évolution peut avoir des impacts pour les salariés internes,
notamment Dev & CQL :

-   Il faut être vigilant sur l'utilisation d'une licence client sur un
    environnement de PROD.

-   Tant que vous utilisez le jeton interne, il n'y aura pas de
    conséquence, l'activation devenue silencieuse n'aura aucun impact
    sur la licence du client.

-   Tant que vous utilisez des environnements de TEST, il n'y aura
    également pas d'impact.

-   Mais s'il vous arrive pour une raison quelconque de désactiver le
    jeton interne et d'utiliser la licence d'un client sur un
    environnement de PROD, alors il n'y aura plus cette fenêtre
    d'activation pour vous rappeler que vous êtes en train d'utiliser
    une licence client et cela va donc entrainer une activation
    automatique de la licence sur votre propre machine ! (\*)

(\*) : Pour être exacte, le problème ne peut se produire que si vous
simulez un environnement FAH sur votre poste (ex :  HostingType =
Shared), que vous avez désactivé le jeton interne et que vous êtes câblé
sur l'environnement IsaGestLic de PROD : Ce cas doit être très rare mais
nous ne sommes pas à l'abri que cela puisse arriver, alors soyez
vigilant svp.

Pour info, un flash a été réalisé sur le fonctionnement du jeton interne
et ses impacts ainsi que le fait de pointer ou non sur les services de
démo des outils (dont Isagestlic) :

<https://web.microsoftstream.com/video/7697119f-5316-4d12-b050-e61eaf3a2245?channelId=037a750e-318d-4cfd-b003-448627e121e0>

# Historique

Cf. historique géré dans le système documentaire
