# Dépôt de test pour IA

## Contenu
[La protection 2013 : fonctionnement salarié (docx)](./Protection_2013_fonctionnement_salarie.docx)

[La protection 2013 : fonctionnement salarié (md)](./Protection_2013_fonctionnement_salarie.md)

[La protection 2013 : principes généraux (docx)](./Protection_2013_principes_generaux.docx)

[La protection 2013 : principes généraux (md)](./Protection_2013_principes_generaux.md)

<p><strong>Contenu</strong></p>
<p><a href="#contexte-et-objet">I. Contexte et objet
<span>3</span></a></p>
<p><a href="#contexte">Contexte <span>3</span></a></p>
<p><a href="#objet">Objet <span>3</span></a></p>
<p><a href="#type-de-protection">II. Type de protection
<span>3</span></a></p>
<p><a href="#glossaire">III. Glossaire <span>4</span></a></p>
<p><a href="#application-technique">Application technique
<span>4</span></a></p>
<p><a href="#client">Client <span>4</span></a></p>
<p><a href="#domaine">Domaine <span>4</span></a></p>
<p><a href="#licence">Licence <span>5</span></a></p>
<p><a href="#modules-fonctionnels">Modules fonctionnels
<span>5</span></a></p>
<p><a href="#modules-commerciaux">Modules commerciaux
<span>6</span></a></p>
<p><a href="#solutions-commerciales">Solutions commerciales
<span>6</span></a></p>
<p><a href="#solutions-client">Solutions client <span>6</span></a></p>
<p><a href="#volumétries">Volumétries <span>6</span></a></p>
<p><a href="#typologie-client">Typologie client <span>6</span></a></p>
<p><a href="#activités">Activité(s) <span>7</span></a></p>
<p><a href="#pays-et-langue">Pays et langue <span>7</span></a></p>
<p><a href="#produit-blanc">Produit blanc <span>7</span></a></p>
<p><a href="#date-de-fin-de-validité">Date de fin de validité
<span>7</span></a></p>
<p><a href="#dépendance-par-rapport-à-la-machine">IV. Dépendance par
rapport à la machine <span>8</span></a></p>
<p><a href="#principe">Principe <span>8</span></a></p>
<p><a href="#installation-identifiée">Installation identifiée
<span>8</span></a></p>
<p><a href="#installation-versus-activation">Installation versus
activation <span>8</span></a></p>
<p><a href="#tolérance">Tolérance <span>8</span></a></p>
<p><a href="#licences-non-liées-à-la-machine">Licences non liées à la
machine <span>9</span></a></p>
<p><a href="#_Toc41320387">Module commercial <span>9</span></a></p>
<p><a href="#solution-commerciale">Solution commerciale
<span>9</span></a></p>
<p><a href="#solution-client">Solution client <span>10</span></a></p>
<p><a
href="#les-diverses-applications-impliquées-dans-la-protection-2013">V.
Les diverses applications impliquées dans la protection 2013
<span>11</span></a></p>
<p><a href="#isagisa">IsaGISA <span>11</span></a></p>
<p><a href="#isabosc">IsaBOSC <span>11</span></a></p>
<p><a href="#isagestlic">IsaGestLic <span>11</span></a></p>
<p><a href="#isagenlic">IsaGenLic <span>11</span></a></p>
<p><a href="#isadminfah">IsAdminFAH <span>12</span></a></p>
<p><a href="#licence-registration">Licence registration
<span>12</span></a></p>
<p><a href="#jeton-interne">Jeton interne <span>12</span></a></p>
<p><a href="#environnements-et-connexion">VI. Environnements et
connexion <span>12</span></a></p>
<p><a href="#historique">VII. Historique <span>13</span></a></p>
<h1 id="contexte-et-objet">Contexte et objet</h1>
<h2 class="unnumbered" id="contexte">Contexte</h2>
<p>La protection a pour objectif de contrôler que nos clients utilisent
leur logiciel conformément à ce qu’ils ont acheté.  La réécriture des
applications Isagri a nécessité une réécriture complète du système de
protection « Protection 2013 »). Sa mise en œuvre est complexe et fait
intervenir de nombreuses équipes (Dev outils, DRI « GISA » et « GRC »,
MktM, MktPr, Dev Progiciel, CQL Progiciel, ADV – Clientèle, SL, IAH, ...
France et export).</p>
<p>Ce document fait partie d’une série de documentations expliquant le
fonctionnement et la mise en œuvre de la protection 2013 dans les
applications Convergence. Pour une vision générale des documentations
disponibles, cf. <a
href="http://projectsrv2010/sites/Coordination/SystemeDocumentaire/_layouts/DocIdRedir.aspx?ID=R6RHQAPNUWS3-52-255">ici</a>.</p>
<h2 class="unnumbered" id="objet">Objet</h2>
<p>Ce document présente les grands principes relatifs à la protection
2013 (concepts mis en œuvre, applications concernées dans
l’administration des licences, …). Il est un préambule indispensable à
la compréhension des autres documents</p>
<h1 id="type-de-protection">Type de protection</h1>
<p>La nouvelle génération du système de protection des applications
Isagri (« Protection 2013 ») est une <strong>protection de type
logiciel</strong> et non pas une protection physique (clé USB, …).</p>
<p><strong>Une version qui reconnaît la protection « 2013 » ne reconnaît
plus que celle-ci. La compatibilité avec les protections antérieures
(protection 2007, code CPVN, clés IKey, …) est supprimée. Et cela quelle
que soit la situation</strong> : France / export ; poste connecté ou non
à Internet ; client connu d’Isagri ou non ; client individuel ou
prestataire ; …</p>
<h1 id="glossaire">Glossaire</h1>
<h2 class="unnumbered" id="application-technique">Application
technique</h2>
<p>Il s'agit du logiciel au sens de la protection (et pas forcément au
sens commercial).</p>
<p>Ainsi, du point de vue de la protection,</p>
<ul>
<li><p>IsaRevise et IsaCotis ne sont pas des applications techniques
(mais des modules d’IsaCompta)</p></li>
<li><p>IsaFact et IsaVigne sont une seul et même application
technique</p></li>
<li><p>IsaCompta indiv et IsaCompta prestataire sont 2 applications
techniques différentes</p></li>
</ul>
<h2 class="unnumbered" id="client">Client</h2>
<p>Le client de la licence est la structure juridique qui a acquis le
droit d’<strong>utiliser</strong> le logiciel (qui peut être distincte
de la structure juridique facturée ou livrée des maj).</p>
<h2 class="unnumbered" id="domaine">Domaine</h2>
<p>Le domaine une entité transversale aux divers logiciels que possède
le client, contenant une ou plusieurs entreprises <strong>d’un même
client</strong>, entreprises qui partage(nt) des données au sein d’un
même logiciel Isagri (ex : les mêmes matériels en PV, les mêmes articles
en GC, …) ou entre logiciels (ex : le plan comptable entre IsaCompta et
IsaPaye).</p>
<p>Pour que les partages de données entre logiciels fonctionnent de
manière automatique (par appels de services et non pas par export puis
import), les données correspondantes doivent être gérées dans le même
domaine dans les différents logiciels possédés par le client :
l’entreprise X ne peut être gérée dans le domaine 1 dans IsaCompta et
dans le domaine 2 dans Geofolia, sous peine de ne pouvoir partager des
données communes aux 2 logiciels pour cette entreprise.</p>
<p><strong>En règle générale, un client a un seul domaine et y gère
toutes ses entreprises.</strong> Cette règle générale est appliquée par
défaut lors de l’achat d’un 2ème logiciel (si le client possède déjà un
domaine pour un logiciel X, par défaut, on lui rattache le même domaine
si il achète le logiciel Y).</p>
<p>En pratique toutefois, un même client peut avoir besoin de plusieurs
domaines dans les cas suivants :</p>
<ul>
<li><p>Il souhaite gérer certaines de ses entreprises de manière
complètement séparée des autres. Par ex, un client a 2 exploitations,
distinctes géographiquement, qui ne partagent aucun facteur de
production -&gt; il doit gérer 2 domaines (et donc disposer de 2
licences) Geofolia</p></li>
<li><p>Il existe une contrainte technique qui empêche de partager des
données entre une BDD installée en local et une BDD installée en FAH.
Cette contrainte oblige un client à gérer des domaines différents entre
2 applications dont l’une est installée en FAH (ex Geofolia) et l’autre
en local (ex : IsaGC, qui ne gèrera le FAH qu’en fin de réécriture)</p>
<ul>
<li><p>16/01/2020 : cette contrainte technique est en train d'être levée
; une fois qu'elle le sera, un même domaine pourra accueillir des
données en local pour un logiciel et en FAH pour un autre</p></li>
</ul></li>
</ul>
<p>Pour un prestataire, les données de ses propres clients (dossiers
comptables en IsaCompta, entreprises en Paye, exploitations en Geofolia)
sont gérées dans le(s) domaine(s) du prestataire (le prestataire n’a pas
un domaine pour chacun de ses clients). Il en va de même pour celles des
agriculteurs en mode partenaire dans Geofolia ou des entreprises
utilisatrices d'Isacompta collaboratif</p>
<p>Pour + de détails, cf. la <a
href="http://projectsrv2010/sites/Coordination/SystemeDocumentaire/_layouts/DocIdRedir.aspx?ID=R6RHQAPNUWS3-52-271">documentation
spécialisée sur le sujet</a></p>
<h2 class="unnumbered" id="licence">Licence </h2>
<p>Une licence définit les droits à utilisation pour <strong>un
logiciel, sur un domaine, pour un client utilisateur</strong> de ce
domaine, en fonction de ce qu’a acheté le client.</p>
<p>Un client dispose <strong>d’une et d’une seule licence</strong> pour
un même logiciel et un même domaine, même s’il a effectué plusieurs
achats successifs (ex en Geofolia, il a acheté un « Geofolia bureau sans
carto ni fumure » puis l’option « Fumure », il dispose d’une seule
licence Geofolia qui lui donne le droit d’utiliser les fonctionnalités
de « Geofolia bureau » avec la fumure)</p>
<p>Outre l'application technique, le domaine, le client, la licence
porte diverses informations qui vont permettre à l’application de
contrôler ses droits effectifs. Ce sont :</p>
<ul>
<li><p>Les modules fonctionnels autorisés (cf. <a
href="#modules-fonctionnels">Modules fonctionnels</a>)</p></li>
<li><p>Les volumétries autorisées (cf. <a
href="#modules-commerciaux">Volumétries</a>)</p></li>
<li><p>La « typologie » du client (cf. <a
href="#typologie-client">Typologie client</a>)</p></li>
<li><p>La ou les activités (cf. <a
href="#activités">Activité(s)</a>)</p></li>
<li><p>Le pays et langue (cf. <a href="#pays-et-langue">Pays et
langue</a>)</p></li>
<li><p>Le nom du produit blanc (cf. <a href="#produit-blanc">Produit
blanc</a>)</p></li>
<li><p>Une éventuelle date de fin de validité (cf. <a
href="#date-de-fin-de-validité">Date de fin de validité</a>)</p></li>
<li><p>Le nombre d’installations autorisées (cf. <a
href="#dépendance-par-rapport-à-la-machine">Dépendance par rapport à la
machine</a>)</p></li>
</ul>
<h2 class="unnumbered" id="modules-fonctionnels">Modules
fonctionnels</h2>
<p>Les modules fonctionnels correspondent aux différentes
fonctionnalités disponibles dans l’application.</p>
<p>Ex de modules fonctionnels :</p>
<ul>
<li><p>Fumure, carto, liaison ISA360, … en Geofolia</p></li>
<li><p>Charges engagées, échéances techniques, analyse de groupe, … en
IsaG.I.</p></li>
<li><p>Emprunts, stocks, … en compta</p></li>
</ul>
<p>Ils sont définis par l'équipe de développement et doivent être pensés
pour être <strong>stables dans le temps</strong> : une fonctionnalité du
produit ne devrait pas changer de module fonctionnel en fonction de
l’évolution de la politique commerciale. Par contre, on peut bien
entendu ajouter de nouveaux modules fonctionnels au fur et à mesure de
la disponibilité de nouvelles fonctionnalités dans les nouvelles
versions du logiciel. Le respect de cette préconisation permet de faire
évoluer la politique commerciale sans nécessiter de développements dans
l’application (et donc sans renvoyer de versions aux clients
existants).</p>
<p>La licence indique pour chaque module fonctionnel si le client y a
droit ou pas.</p>
<h2 class="unnumbered" id="modules-commerciaux">Modules commerciaux</h2>
<p>Cf. <a
href="file:///C:\Temp\Protection_2013_definition_des_solutions_commerciales.docm#Module_commercial">Definition_des_solutions_commerciales</a></p>
<h2 class="unnumbered" id="solutions-commerciales">Solutions
commerciales</h2>
<p>Cf. <a
href="file:///C:\Temp\Protection_2013_definition_des_solutions_commerciales.docm#Solution_commerciale">Definition_des_solutions_commerciales</a></p>
<h2 class="unnumbered" id="solutions-client">Solutions client</h2>
<p>Cf. <a
href="file:///C:\Temp\Protection_2013_definition_des_solutions_commerciales.docm#Solution_client">Definition_des_solutions_commerciales</a></p>
<h2 class="unnumbered" id="volumétries">Volumétries</h2>
<p>La politique commerciale peut prévoir des tarifs différents selon la
volumétrie gérée par le client pour certains concepts. Exemples :</p>
<ul>
<li><p>Nombre de vaches en Troup'O, de truies en Pig'up</p></li>
<li><p>Nombre d'e-mails envoyés par an depuis la GC</p></li>
<li><p>Nombre d'utilisateurs dans différents logiciels</p></li>
</ul>
<p>Pour chacune de ces natures de volumétries, un plafond est défini en
fonction de ce qu'a acheté le client. La licence contrôle que ce plafond
n'est pas dépassé</p>
<p>Les volumétries achetées par le client et les natures de volumétries
correspondantes sont véhiculées par la licence (à charge de
l’application de calculer où on en est).</p>
<p>Les limites de volumétries sont définies pour le domaine. En cas
d’installation de plusieurs BDD, les limites définies sont valables pour
chacune des BDD (il n’y a pas de cumul entre les diverses BDD).</p>
<p>Les volumétries achetées peuvent être définies par activité</p>
<blockquote>
<p>Ex : dans le cas de Troup'O, pour la nature de volumétrie « Nombre de
vaches »; on peut renseigner, pour un même domaine, un nombre pour
l’activité « Bovin lait » (il s'agit de vaches laitières) et un autre
nombre pour l’activité « Bovin viande » (il s'agit de vaches
allaitantes)</p>
</blockquote>
<p>Le nombre d’<strong>utilisateurs</strong> est une des natures de
volumétrie gérées. Il s’agit d’un nombre <strong>d’utilisateurs
déclarés</strong> (càd. définis dans l’application et autorisés à
utiliser celle-ci). Il n’y a pas de contrôle possible d’un nombre
<strong>d’utilisateurs simultanés.</strong></p>
<p>Le nombre d’installations autorisé n’est pas une nature de volumétrie
mais est contrôlé par un autre mécanisme (cf. <a
href="#dépendance-par-rapport-à-la-machine">Dépendance par rapport à la
machine</a>).</p>
<h2 class="unnumbered" id="typologie-client">Typologie client</h2>
<p>La licence définit également la typologie du client. Il en existe 4,
communes à toutes les applis</p>
<ul>
<li><p>Individuel</p></li>
<li><p>Organisme (= prestataire)</p></li>
<li><p>Ecole</p></li>
<li><p>Isagri (typologie utilisée pour les licences internes destinées à
gérer les référentiels)</p></li>
</ul>
<p>Une licence porte 1 et 1 seule typologie client</p>
<p>Cela permet à l’application d’adapter son fonctionnel (ex :
fonctionnement particulier pour les écoles)</p>
<h2 class="unnumbered" id="activités">Activité(s)</h2>
<p>La licence porte également la notion d’activité du client (le
marché). Les activités sont spécifiques à l'application technique</p>
<blockquote>
<p>Ex :</p>
</blockquote>
<ul>
<li><p>En Geofolia, on a les activités Grand cultures, Elevage,
Viticulture ;</p></li>
<li><p>En Ruminants, on a les activités Bovin lait, Bovin viande, Ovin
lait, Ovin viande, Caprins, …</p></li>
</ul>
<p>Une licence peut porter de 0 à n activités.</p>
<p>Cela permet à l’application d’adapter son vocabulaire ou son
fonctionnel en fonction de la ou des activités du domaine (ex : parler
d’agnelage ou de vêlage en ruminants selon que l’activité est Bovin ou
Ovin ; adapter le nom du logiciel, …)</p>
<h2 class="unnumbered" id="pays-et-langue">Pays et langue</h2>
<p>La licence définit la culture (pays et langue) <strong>de
fonctionnement de l’application</strong> (qui conditionne l’activation
de tel fonctionnement spécifique au pays, le référentiel utilisé, …).
Ils peuvent être différents du pays de résidence du client ou de la
langue d’affichage de l’IHM.</p>
<blockquote>
<p>Ex : on vend Geofolia à un client français pour une exploitation
qu’il possède en Roumanie. La licence doit être générée pour la Roumanie
/ le Roumain pour que les spécificité Roumaines soient gérées. Mais le
client peut utiliser l’application avec l’IHM en Français</p>
</blockquote>
<h2 class="unnumbered" id="produit-blanc">Produit blanc</h2>
<p>Un produit blanc est un produit vendu par un distributeur sous sa
propre marque.</p>
<blockquote>
<p>Ex : Weelogic pour Isacompta</p>
</blockquote>
<p>L’application doit être « customisée » (iconographie, nom du
logiciel, fonctionnalités accessibles…).</p>
<p>La licence contient le code du produit blanc correspondant. Elle peut
ainsi se baser sur cette information pour adapter son fonctionnement.
Pour le produit standard Isagri, ce code n’est pas renseigné.</p>
<h2 class="unnumbered" id="date-de-fin-de-validité">Date de fin de
validité</h2>
<p>La licence peut porter une date de fin de validité pour gérer les
licences à durée limitée : contrats essais, ...</p>
<h1 id="dépendance-par-rapport-à-la-machine">Dépendance par rapport à la
machine</h1>
<h2 class="unnumbered" id="principe">Principe</h2>
<p>Pour empêcher un client de diffuser sa licence, on limite le nombre
d'installations autorisées pour une même licence, selon ce qu'a acheté
le client (« nombre de licences » dans IsagestLic).</p>
<blockquote>
<p>Plutôt que de « nombre de licences » dans IsaGestLic, il vaudrait
mieux parler de « Nombre d’installations principales autorisées »</p>
</blockquote>
<h2 class="unnumbered" id="installation-identifiée">Installation
identifiée</h2>
<p>On identifie l’instance de <strong>SQL Server</strong> (le moteur de
base de données) et non pas les postes "clients".</p>
<p>Cela a pour conséquence, qu'avec une seule "installation", un client
en FAH (ou en réseau local) peut accéder à son application depuis autant
de postes qu'il le souhaite (puisqu'il utilise toujours la même instance
de SQL server). En règle générale (y compris les prestataires en
multi-sites ou avec des collaborateurs en mobilité ainsi que les
"saisies décentralisées" en GC, grâce à la notion de licence
secondaire), <strong>un client n'a donc besoin que d'une seule
installation.</strong></p>
<p>L'instance SQL server est identifiée via une clé générée
aléatoirement lors de l’installation de SQL server. Il n’y a pas de lien
avec les composants physiques de la machine (carte réseau, carte mère,
…). Un changement de carte réseau par exemple ne modifiera pas
l’identifiant de la machine. Par contre, un formatage du serveur de BDD
entraînera la génération d’une nouvelle clé lors de la réinstallation de
SQL server et on considèrera donc qu’il s’agit d’une nouvelle
machine.</p>
<h2 class="unnumbered" id="installation-versus-activation">Installation
versus activation</h2>
<p>On distingue l’installation de licence et l’activation de
celle-ci.</p>
<p>L’<strong>installation</strong> consiste à <strong>installer la
licence dans la BDD SQL Server</strong>.</p>
<blockquote>
<p>L’installation est obligatoire pour que le client puisse commencer à
utiliser le logiciel (sans licence installée, le logiciel est
inutilisable puisqu’il ne connaît pas le domaine, les modules autorisés
ou non, …). Une fois la licence installée, le client peut utiliser
l’application pendant une durée limitée (14 j). Il doit activer sa
licence pour pouvoir continuer à utiliser son logiciel au-delà.</p>
</blockquote>
<p>L’<strong>activation</strong> permet de <strong>lier la licence à la
machine sur laquelle elle est installée</strong>.</p>
<blockquote>
<p>Pour cela, le client doit récupérer auprès d’Isagri une clé
d’activation dépendante de l'instance SQL Server utilisée.</p>
<p>Une fois la licence activée pour l'instance SQL Server, l’application
peut être utilisée (jusqu’à la version majeure suivante - qui
nécessitera une réactivation - ou jusqu’à la date de fin de validité de
la licence si elle en a une)</p>
<p>L'activation est complètement transparente pour le client dans le cas
d’un poste connecté à Internet.</p>
</blockquote>
<h2 class="unnumbered" id="tolérance">Tolérance</h2>
<p>Comme pour la protection 2007, on n’a pas prévu de désactivation de
la licence en cas de changement de machine (en effet un tel système
impliquerait une manipulation sur la machine obsolète mais celle-ci peut
ne plus fonctionner ou ne plus être disponible). En conséquence, un
système de <strong>tolérance</strong> a été mis en place : le client
peut temporairement (jusqu’à la version suivante) utiliser son
application sur une machine de plus que ce qu’il a acheté. Au-delà de la
tolérance (tentative d’activation sur plus d’une machine excédentaire ou
même machine excédentaire utilisée pour 2 versions), le client est
bloqué (ne peut activer).</p>
<p>Ex :</p>
<blockquote>
<p>Le client a droit à 2 installations ;</p>
<p>Il active la version 10.00 pour le poste A et le poste B ;</p>
<p>Il remplace sa machine B par une nouvelle machine C :</p>
</blockquote>
<ul>
<li><p>Il peut activer la version 10.00 sur cette machine C grâce à la
tolérance</p></li>
<li><p>On l’avertit qu’il dépasse son quota d’installations autorisées
mais ce message ne bloque pas l’installation sur la machine C.</p></li>
<li><p>Techniquement, rien ne l’empêche de continuer à utiliser la
version 10.00 sur la machine B.</p></li>
</ul>
<blockquote>
<p>Il installe la version 11.00 (soit une nouvelle version majeure
nécessitant une réactivation) :</p>
</blockquote>
<ul>
<li><p>Il peut l’activer uniquement sur 2 postes parmi A, B et C (…ce
qui est cohérent car il n'est plus censé utiliser B).</p></li>
<li><p>Il pourra toutefois bénéficier d’une nouvelle tolérance sur une
machine D (mais sera à nouveau bloqué à 2+1 machines avec la version
12.00).</p></li>
</ul>
<p>En résumé :</p>
<ul>
<li><p>Ce client sera toujours limité à 2+1=3 activations par version
majeure associée à cette licence ;</p></li>
<li><p>Un message d’avertissement non-bloquant devra l’informer du
dépassement de quota lors d’une troisième activation ;</p></li>
<li><p>Une quatrième activation sera impossible.</p></li>
</ul>
<h2 class="unnumbered" id="licences-non-liées-à-la-machine">Licences non
liées à la machine</h2>
<p>La majorité des licences sont liées à la machine.</p>
<p>Il est toutefois possible de définir des licences non liées à la
machine, qui peuvent donc être installées sur autant de machines que
l’on veut. C’est par exemple le cas des licences de démo, des licences
écoles, ... Dans ce cas, l'ADV va renseigner une validité limitée dans
le temps pour limiter le risque de piratage.</p>
<p>Une licence non liée à la machine n’est pas à activer. L’installation
de celle-ci suffira pour utiliser le logiciel le temps de sa validité
(sur autant de serveurs de BDD que l’on veut donc). Pour des raisons de
sécurité, de telles licences doivent toujours avoir une date de fin de
validité</p>
<h2 class="unnumbered" id="module-commercial">Module commercial</h2>
<p>Cf. <a
href="http://projectsrv2010/sites/Coordination/SystemeDocumentaire/DocOfficielsSansValidation/Protection_2013_definition_des_solutions_commerciales.docm">Protection_2013_definition_des_solutions_commerciales.docm</a></p>
<h2 class="unnumbered" id="solution-commerciale">Solution
commerciale</h2>
<p>Cf. <a
href="http://projectsrv2010/sites/Coordination/SystemeDocumentaire/DocOfficielsSansValidation/Protection_2013_definition_des_solutions_commerciales.docm">Protection_2013_definition_des_solutions_commerciales.docm</a></p>
<h2 class="unnumbered" id="solution-client">Solution client</h2>
<p>Cf. <a
href="http://projectsrv2010/sites/Coordination/SystemeDocumentaire/DocOfficielsSansValidation/Protection_2013_definition_des_solutions_commerciales.docm">Protection_2013_definition_des_solutions_commerciales.docm</a></p>
<h1
id="les-diverses-applications-impliquées-dans-la-protection-2013">Les
diverses applications impliquées dans la protection 2013</h1>
<p>Diverses applications sont impliquées dans la diffusion des licences
et le contrôle de la conformité entre ce que le client utilise et ce
qu’il a acheté.</p>
<p>Initialisation du domaine Installation de la licence</p>
<p>Utilisation</p>
<p>Création du client</p>
<p>IsaGISA</p>
<p>IsaBOSC</p>
<p>Création du domaine Configuration de la licence</p>
<p>IsaGenLic</p>
<p>IsaGestLic</p>
<p>Activation</p>
<p>IsaGestic</p>
<p>Progiciel Isagri</p>
<p>Jeton interne</p>
<p>IsAdminFAH</p>
<p>Progiciel Isagri</p>
<p>Licence</p>
<p>Autre logiciel de facturation</p>
<p>Licence registration</p>
<p>Liste clients</p>
<p>Liste clients</p>
<h2 class="unnumbered" id="isagisa">IsaGISA</h2>
<p>IsaGISA est l’application qui est utilisée pour la gestion et la
facturation des clients. C’est une application de type client lourd,
elle est principalement utilisée par l’équipe Administration Des Ventes
et par certaines filiales à l’export (Italie, Espagne, etc.). Elle est
gérée par l’équipe DRI-GISA.</p>
<h2 class="unnumbered" id="isabosc">IsaBOSC</h2>
<p>IsaBOSC (Isa BackOffice Service Clients) est une application web qui
permet, comme son nom l’indique, d’administrer certains éléments liés au
service client. À ce jour elle dispose de deux grandes fonctionnalités :
la gestion de l’updater, service utilisé pour envoyer des mises à jour
aux clients via le web, et l’intégration des clients de l’export et des
filiales qui n’utilisent pas IsaGISA dans la base Isagri. Cette
application est également gérée par l’équipe DRI-GRC.</p>
<h2 class="unnumbered" id="isagestlic">IsaGestLic</h2>
<p>IsaGestLic est une application web qui permet de créer les licences
clients selon ce qu’ils ont acheté. Elle gère également la création des
domaines dans le SI Isagri (attribution d’un n° unique, rattachement au
client). Elle est utilisée par le marketing marché pour mettre en place
tous les paramétrages nécessaires à la génération des licences et par
l’ADV pour y créer les domaines et licences sur base des bons de
commandes des clients (et cela par Isagri France mais aussi par les
filiales à l’export et par les autres distributeurs). L’application est
développée et maintenue par l’équipe DRI-GRC.</p>
<h2 class="unnumbered" id="isagenlic">IsaGenLic</h2>
<p>IsaGenLic est un utilitaire qui permet de générer des licences
« internes » destinées à être utilisées par les collaborateurs Isagri
(Support, CIM, AET) pour effectuer des tests. Cela permet de ne pas
avoir à gérer des clients / des licences dans les outils de production
(IsaGISA et IsaGestLic). Cet utilitaire est géré par l’équipe
Outils.</p>
<h2 class="unnumbered" id="isadminfah">IsAdminFAH</h2>
<p>IsAdminFAH est une application gérée par la DRI qui permet
d’administrer les BDD <strong>en FAH</strong>. En particulier, elle
automatise la création de nouvelles BDD, l’initialisation des domaines
dans ces BDD, l’installation de la licence dans chaque domaine.</p>
<p>En mode local, ces fonctionnalités sont prises en charge par le
progiciel Isagri</p>
<h2 class="unnumbered" id="licence-registration">Licence
registration</h2>
<p>Licence registration est une application web qui permet aux clients
utilisant leur progiciel Isagri sur un poste non connecté à Internet
d’activer leurs licences en ligne (depuis un autre poste). Pour les
clients qui utilisent leur progiciel Isagri sur un poste connecté à
Internet, cette activation est transparente. Dans les 2 cas, les données
sont stockées dans IsaGestLic, de manière à contrôler le nombre
d’installations de l’application sur des PC différents.. Cette
application est gérée par l’équipe DRI-GRC</p>
<h2 class="unnumbered" id="jeton-interne">Jeton interne</h2>
<p>Cet utilitaire développé par l’équipe Outils permet d’être
authentifié en tant que collaborateur Isagri et de pouvoir utiliser des
licences internes générées avec IsaGenLic ou d’utiliser la licence d’un
client sans l’activer.</p>
<h1 id="environnements-et-connexion">Environnements et connexion</h1>
<p>La protection 2013 étant complexe, un environnement de démonstration
a été mis en place afin que les utilisateurs puissent effectuer
différents tests avant de réaliser les opérations directement en
production. Les versions de démonstration permettent également aux
utilisateurs et aux testeurs de tester les nouvelles fonctionnalités
développées avant leur passage en production.</p>
<p>Tous les utilisateurs ayant accès à la version de production d’une
application disposent également d’un accès sur la version de
démonstration (l’inverse n’est pas vrai).</p>
<p>Voici les adresses des différentes applications gérées par l’équipe
DRI-GRC (pour les autres applications renseignez-vous auprès des équipes
concernées).</p>
<table>
<colgroup>
<col style="width: 22%" />
<col style="width: 39%" />
<col style="width: 37%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><strong>Démonstration</strong></th>
<th><strong>Production</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>IsaBOSC</strong></td>
<td><a
href="http://demo.isabosc.groupeisagri.com/">http://demo.isabosc.groupeisagri.com/</a></td>
<td><a
href="http://isabosc.groupeisagri.com/">http://isabosc.groupeisagri.com/</a></td>
</tr>
<tr class="even">
<td><strong>IsaGestLic</strong></td>
<td><a
href="http://demo.isagestlic.groupeisagri.fr/">http://demo.isagestlic.groupeisagri.fr/</a></td>
<td><a
href="http://isagestlic.groupeisagri.fr/">http://isagestlic.groupeisagri.fr/</a></td>
</tr>
<tr class="odd">
<td><strong>Licence registration</strong></td>
<td><a
href="http://demo.isalicence.isagri.fr/">http://demo.isalicence.isagri.fr/</a></td>
<td><a
href="http://www.licence-registration.com/">http://www.licence-registration.com/</a></td>
</tr>
</tbody>
</table>
<h1 id="historique"><br />
Historique</h1>
<table>
<colgroup>
<col style="width: 18%" />
<col style="width: 81%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p>Date et auteur des modifications</p>
</blockquote></th>
<th><blockquote>
<p>Détail des modifications apportées</p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>16/01/2020<br />
D. Lemal</p>
</blockquote></td>
<td><blockquote>
<p>Corrections mineures</p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>03/07/2019<br />
D. Lemal</p>
</blockquote></td>
<td><blockquote>
<p>Corrections de mise en forme</p>
</blockquote></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>20/06/2016<br />
D. Lemal</p>
</blockquote></td>
<td><blockquote>
<p>Correction mineure</p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>27/05/2016<br />
D. Lemal</p>
</blockquote></td>
<td><blockquote>
<p>Ajout de la notion de produit blanc / de la langue</p>
</blockquote></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>16/03/2016<br />
D. Lemal</p>
</blockquote></td>
<td><blockquote>
<p>Mise en forme pour publication dans le système documentaire
production</p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>22/10/2015<br />
D. Lemal</p>
</blockquote></td>
<td><blockquote>
<p>Création</p>
</blockquote></td>
</tr>
</tbody>
</table>
