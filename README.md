# Mise en place d'un Wake-on-Lan over Internet

Fichier PWP : [Mise en place d'un Wake-on-Lan over Internet.pptx](https://github.com/RaphBarniques/woli/files/7685943/Mise.en.place.d.un.Wake-on-Lan.over.Internet.pptx)


## Défi:  
Avoir accès à distance à son ordinateur en tout temps est bien pratique. Cependant, le logiciel VNC server/viewer requiert que l’ordinateur soit allumé. La solution? Le Wake-on-Lan!

## C'est quoi?
 Le Wake-on-Lan est la possibilité d’allumer un ordinateur uniquement par le résseau local. La mention “over internet” étend cette opération au-delà du réseau local. (WAN)
 
 ## Comment ça marche?
 L’ordinateur peut être allumé avec des “Magic packets”. Les “Magic packets” sont des paquets d’information qui contient, entre autre l’adresse ip du client mais aussi l’adresse Mac unique de la carte réseau.

Ces informations sont envoyés à tout les appareils du réseau mais n’agit seulement que sur celui qui correspond au informations.

## Les étapes
 01. Interface : Les infos sont fournies par l'utilisateur
 02. Serveur : La demande est formulée et envoyée
 03. Routeur : Transmet la demande
 04. Carte réseau : Se reconnaît et allume l'ordinateur

## 01. Interface
Vous devrez récupérer quelques information avant de commencer:
* Adresse IP : Adresse IPv4 publique. - Accessible par une recherche web.
* Adresse MAC : Adresse unique qui identifie le composant. - Accessible avec la commande ipconfig /all dans l'invite de commande.
![2021-12-09_01h25_51](https://user-images.githubusercontent.com/94623626/145414516-62c56421-d117-4850-aa0c-0b99be61a6e9.png)
### Note: Pour fonctionner, l’ordinateur doit obligatoirement communiquer avec le routeur via Ethernet.

## 02. Serveur
Bien que nous aurions pu l'héberger nous-même dans le cloud, j'utiliserai [depicus.com](www.depicus.com).

Depicus : Permet de recueillir les données formater le paquet et l’envoyer.
Contient aussi des outils de troubleshooting.

## 03. Routeur
Nous devrons préparer quelque trucs avec notre routeur.
* Pare-feu : Les routeurs n’aime pas que les serveurs discutent directement avec les ordinateurs. Nous devons donc lui permettre de communiquer avec nous. (Exceptions)
* Redirection de port : Nous enverrons la requêtes à un port du routeur (porte d’entrée) qui sera redirigé vers l’ordinateur.

## 04. Carte réseau
Du côté de l'ordinateur aussi, nous devrons aller activer quelques paramètres.
* BIOS : Activer l’option Wake-on-Lan dans le menu BIOS de la carte-mère
* Gestionnaire : Permettre à la carte réseau de démarrer l’ordinateur lorsqu’elle reçoit un “Magic packet”
![2021-12-09_01h55_43](https://user-images.githubusercontent.com/94623626/145417658-ffa9cdd6-42f1-429e-b3e8-244eeec535a1.png)

# Voilà!
Vous pouvez maintenant allumer votre ordinateur de n'importe où!



