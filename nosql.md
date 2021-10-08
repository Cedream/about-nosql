#NoSQL
Écrit par Jebira Sélim, Thonus Cedric & Potaznik Jérémie

## Histoire du NoSQL 

Le besoin pour ce genre de base de donnée, plus grande, d’une structure non fixe, a commencé a se faire ressentir dès les années 2000 où :  Google, amazon, ebay et autres géants ont commencé à émergé, et brasser des quantités énormes de données.

Les bases de données devenaient alors trop grandes pour une seule machine, et leur structure commençaient à ne plus convenir aux besoins de ces mastodontes. Fin des années 2000 début 2010, des articles présentant de nouvelles formes de bases de données ont vu le jour, ces forme était plus flexible et surtout plus extensibles. Ces premières nouvelles bases de données étaient alors open-source afin de pouvoir partager et améliorer collectivement cette technologie. Le nom NoSQL est alors retenu lors d’une conférence à San Francisco en 2009 comme l’ensemble de ces nouvelles formes de bases de données. Des nouvelles bases de données NoSQL sont alors développées et vendues. Vendues trop chères selon Amazon (avec SimpleDB) et Google qui décide alors de créer leur propre technologie NoSQL.  

## Principe de base du NoSQL 

La structure n’est plus liée à un schéma relationnel très difficile à modifier, la base peut donc croitre sans contraintes. Ces bases de données laissent tomber l’idée d’enregistrements et de relations entre les éléments. Ces bases de données s’avèrent donc beaucoup plus flexible, évolutive.
Le développeur n’a plus à se soucier de l’emplacement des données, fractionné ou non. Lorsque la base de données devient trop grande, il suffit de définir une nouvelle machine connectée sur le réseau, et la base de données NoSQL s’occupe du reste, automatiquement. Cela permet la création de bases de données de plusieurs centaines de Tétra-octets et ce sur plusieurs machines.

## Raison d’utilisation 

Le langage SQL et les bases de données relationnelles posent un certain nombre de contraintes de sécurité et de structures parfaites pour gérer les données courantes ou en stocker quelques-unes en plus. Mais ces contraintes deviennent d’énormes obstacle dès que l’ont veux stocker un nombre conséquent de données (parfois redondantes) pour les analyser (bigData) ou pour les utiliser dans un temps relativement long (un joueur peut vouloir se connecter plusieurs années après avoir arrêter de jouer). Il faut donc changer un peut la structure et avoir des outils permettant d’analyser/utiliser toutes ses données.

### Back-end 

Il existe plusieurs formes de bases de données noSQL :
- clé-valeur
- Orienté Colonnes
- Orienté Documents
- Graphs
  
A noter que Clé-valeur et orienté document sont très similaire, le premier liant une clé a une donnée-information, le deuxième a un document. 

### Clé-valeur et documents 

Ces bases de données NoSQL se présente sous la forme de clé, valeur. La valeur est alors un document (souvent en JSON ou xml) contenant alors les informations. Ces document sont alors structuré comme les développeurs le veulent, pouvant toutefois toujours être modifié en cas de besoin. 
Cette méthode est beaucoup utilisée pour la sauvegarde de beaucoup d’informations pouvant être utilisé et modifié dans le futur.  Par exemple les compte Hearstone des joueurs, contenant : score, cartes, decks, etc…. A noter que dans cet exemple, une autre base de données existe pour la simple connexion au compte, ses comptes étant en effet lié à plusieurs jeux, et donc contenant des liens vers les bases de données correspondantes.  Les information sont rapidement et super facilement accessibles dès lors que nous avons la clé. Si nous ne disposons pas de cette clé, les recherches restent possibles mais sont alors plus lentes. C’est pourquoi ce genre de méthode est très rarement utilisées pour le bigData.  Pour ajouter une donnée, il suffit donc d’ajouter une clé et sa valeur/son document.

### Orienté colonne 

Cette forme est beaucoup utilisée pour réaliser des analyses massives de donnée, comme le BigData. Elles sont toutefois plus complexes à exploiter humainement.
Une ligne a une clé, cette clé lie des colonnes contenant alors pleins de lignes. Cela est donc rapide a processer car il « suffit » de faire tourner un algorithme sur toutes les lignes une par une sans s’arrêter, sans passer de lignes. Le tout pour une ou plusieurs clés.  Si l’on souhaite ajouter une donnée, soit un ajoute une clé-ligne, soit une ligne dans une clé existante. On peut aussi ajouter une colonne pour une clé-ligne déjà existante.

### Orienté Graphs 

Cette forme s’intéresse particulièrement aux liens entre des éléments, par exemple deux personnes ou un nom et une entreprise. Un bon moyen de s’imaginer ça, est un grand dessin où chaque donnée est un point et chaque liens un trait entre ces deux points. Ces liens peuvent être identifié comme « aime », « appartient », etc… Il devient alors facile de voir aussi qui n’appartient pas à X ou qui n’aime pas Y.  Ce type de bases de données peut alors être exploité, par exemple pour les réseaux sociaux.
 Nous pouvons ajouter des points, et d’autres types de liens, afin d’agrandir la base de donnée.

### Marché actuel

Aujourd’hui les SGBD relationnel sont encore largement utilisé par des entreprises moyenne ayant des quantités de données moyennes, par exemple le traitement des transactions, gestion des employés…
Mais le NoSQL est de plus en plus utilisé pour tout ce qui est connexion a des compte, sur des applications comme des sites web fréquentés. Les logiciels permettant de continuer a utiliser les SGBD traditionnels rapidement nécessitent des installations couteuses et des compétence en optimisation peu répandues.
Il existe de nos jours pleins de solutions NoSQL abordable, au niveau du prix, comme de l’apprentissage et de l’utilisation. 
Dans le marché des SGBD NoSQL se trouvent Cassandra (Facebook), MongoDB, Voldemort, CouchDB et SimpleDB (Amazon).

## La sécurité

Les bases de données NoSQL sont de plus en plus utilisées par les entreprises ayant besoin d'un grand volume de stockage, mais point de vue sécurité, ce type de pratique est-il tout aussi sécurisé que les bases relationnelles?

Tout d'abord, il est important de savoir, que lors de la conception de NoSQL, la sécurité n'était pas une priorité. Ce qui oblige donc les équipes de développeurs utilisant cette technologie d'ajouter une couche de sécurité aux applications NoSQL de leur entreprise.

Les problèmes de sécurité que rencontrent les bases relationnelles sont les mêmes que ceux rencontrés par les bases NoSQL.Cependant les bases NoSQL ne fournissent pas ou très peu de solutions pour s'en prémunir.
Heureusement, à mesure que le marché NoSQL grandit, la sécurité,quant à elle grandit également apportant des solutions avec entre autre,l'apparation de modules d'authentification Kerberos.

### Les petites entreprises et NoSQL

Très souvent, de petites entreprises manipulant de grandes quantités de données se voient dans l'obligation de migrer vers une architecture plus souple telle que NoSQL, mais celles-ci ignorent les mesures de sécurité NoSQL, mesures qui auraient été implémentées par defaut avec les bases relationnelles.

### MongoDB et la sécurité

Prenons la base de données NoSQL leader du moment, MongoDB, celle-ci fonctionne avec des systèmes de sécurité avancés telles que:
- **L'authentification Kerberos**
    - C'est un système d'authentification réseau qui fonctionne avec le chiffrement symétrique(ancienne forme de chiffrement, elle permet à l'aide d'une clé secrète de chiffrer et de déchiffrer des données) mais également avec l'utilisation de tickets.
    ![](https://miro.medium.com/max/1810/1*T7OCCglhAI5WPSFR00Is0w.png)
&nbsp;
- **LDAP** (Lightweight Directory Access Protocol)
    - LDAP est un protocole permettant de gérer des bases d'informations sur les utilisateurs d'un réseau, grâce aux protocoles TCP/IP. Depuis sa version 3, il fonctionne avec un système de chiffrement ainsi que d'authentification.
    - Ce protocole fournit aux utilisateurs des solutions leur permettant de se connecter, déconnecter, insérer des entrées, en modifier ou en supprimer.

Ces systèmes de sécurité garantissent un contrôle total sur l'accès aux données.

À ses débuts, MongoDB n'utilisait pas ses systèmes de sécurité, ce qui avait un gros impact au niveau des transmissions réseau où aucun chiffrement n'était fait entre le serveur et le client, les données étaient envoyées en clair.

### Cassandra et la sécurité

Cassandra est le deuxième système de gestion de base de données le plus utilisé après son homologue MongoDB, lui aussi possède des systèmes de sécurité telles que :

- Cryptage client à nœud, qui inclut une forme de communication sécurisée et optionnelle d'un ordinateur client à un cluster de bases de données (SSL). Ce qui garantit l'intégrité des données.

&nbsp;
- La technologie JMX (Java Management Extensions) est composé de 3 parties:
  1. **Authentification** : le client distant doit être authentifié dans le serveur.
  2. **Contrôle d'accès** : le contrôle de l'accès des beans gérés définit les privilèges d'accès aux informations de beans gérés et les droits d'exécution des opérations de beans gérés.
  3. **Transfert sécurisé** : le transfert entre le client et le serveur JMX peut être sécurisé à l'aide du protocole TLS/SSL.
&nbsp;
En bref, JMX est une API qui permet de surveiller et gérer des ressources.
\
&nbsp;

##### Sources
- https://blogs.perficient.com/2015/06/22/nosql-nosecuity-security-issues-with-nosql-database/
- https://www.ibm.com/support/knowledgecenter/fr/SSTVLU_7.1.1/com.ibm.websphere.extremescale.doc/cxsjmxsec.html
- https://www.jmdoudoux.fr/java/dej/chap-jmx.htm
- https://docs.datastax.com/en/cassandra/3.0/cassandra/configuration/secureIntro.html
- https://www.mongodb.com/scale/nosql-database-security
- https://www.researchgate.net/publication/254018091_Security_Issues_in_NoSQL_Databases
- https://www.computerweekly.com/tip/Securing-NoSQL-applications-Best-practises-for-big-data-security
- https://medium.com/@dewni.matheesha/kerberos-the-computer-network-authentication-protocol-a198309339b7
- https://www.piloter.org/business-intelligence/base-nosql.htm
-https://www.illustradata.com/bases-nosql-documents-quest-cest/
- https://fr.wikipedia.org/wiki/NoSQL
- https://www.quora.com/-What-are-the-main-differences-between-the-four-types-of-NoSql-databases-KeyValue-Store-Column-Oriented-Store-Document-Oriented-Graph-Database
- https://database.guide/what-is-a-column-store-database/
- https://info.couchbase.com/

