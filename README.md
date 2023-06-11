# IOTProjectMiage
# Projet IoT de Surveillance de Piscine

Bienvenue sur le projet de surveillance de piscines basé sur IoT. Il a été conçu et développé lors d'un cours dans le programme de MIAGE, sous la supervision de M. Gilles Menez. L'objectif principal de ce projet est de démontrer l'utilisation et les avantages des technologies de l'Internet des objets (IoT). En se concentrant sur l'utilisation des protocoles MQTT et HTTP, de l'outil de flux de données Node-RED, et de l'intégration avec divers services web, ce projet facilite la communication entre un dispositif ESP32 et une base de données MongoDB.

# Présentation du projet

Bienvenue sur le projet de surveillance de piscines basé sur IoT. Il a été conçu et développé lors d'un cours dans le programme de MIAGE, sous la supervision de M. Gilles Menez. L'objectif principal de ce projet est de démontrer l'utilisation et les avantages des technologies de l'Internet des objets (IoT). En se concentrant sur l'utilisation des protocoles MQTT et HTTP, de l'outil de flux de données Node-RED, et de l'intégration avec divers services web, ce projet facilite la communication entre un dispositif ESP32 et une base de données MongoDB.

Présentation du projet
Le projet est centré sur la surveillance d'un groupe de piscines. Les informations associées à chaque piscine, y compris leurs températures respectives, sont publiées sur un sujet MQTT spécifique. Les informations sont ensuite récupérées, comparées et la piscine avec la température la plus élevée est marquée en rouge sur une carte Node-RED.

De plus, notre système intègre également des données de localisation de personnes souhaitant utiliser ces piscines. Pour ce faire, nous avons mis en place une application appelée OwnTracks. Cette application est configurée pour envoyer des informations de localisation à un autre sujet MQTT, qui est ensuite reçu et traité par notre dispositif ESP32.

Lorsqu'un utilisateur souhaite entrer dans une piscine, une demande est envoyée via une requête GET. Cette demande est ensuite transmise à aa notre ESP et apres notre service web via une requête POST. Le service web traite la demande et l'enregistre dans notre base de données MongoDB. En outre, l'application vérifie si la distance entre la piscine et l'utilisateur est inférieure à 100 mètres, ce qui est un prérequis pour que l'utilisateur puisse accéder à la piscine.

Suite au traitement de la demande,la LED de l'ESP32 s'allume pendant 30 secondes. Notez qu'à la première demande, il peut être nécessaire de réessayer en raison d'un problème de watchdog que nous n'avons pas réussi à résoudre. Cependant, ce problème ne se présente pas pour les demandes suivantes.

En parallèle, l'emplacement de l'utilisateur est mis en évidence en jaune sur notre carte Node-RED.

# Lien vers le service Web
Pour obtenir les données : https://iotwebservice-kspm.onrender.com/get
Pour insérer des données : https://iotwebservice-kspm.onrender.com/insert


# Dashboard d'administration

Dans le cadre de ce projet, nous avons également mis en place un tableau de bord d'administration. Ce tableau de bord permet de garder une trace de toutes les entrées et sorties de la piscine.

# Lien vers le git de Dashboard

https://github.com/Ibrahim-krimi/iotProjet_dashboardAdmin

# Lien vers le git de WebService

https://github.com/Ibrahim-krimi/IOT

# Lien vers le git de la partie Arduino

https://github.com/Ibrahim-krimi/IOTProjectMiage

# Lancement du projet

Pour démarrer le Dashboard, vous devez utiliser la commande Http-server.

Pour démarrer le Service localement, vous devez utiliser la commande node service.js.

Pour démarrer le Service arduino , vous devez avoir une Carte ESP32 et Arduino sur votre pc.


# Retour d'expérience

La mise en œuvre de ce projet a été une expérience très enrichissante, car c'est la première fois que nous nous sommes plongés dans le monde passionnant de l'IoT. Nous avons appris comment les différents composants et technologies peuvent être combinés pour créer une solution complète qui peut avoir des applications réelles dans le monde d'aujourd'hui. Cela nous a également donné une idée de comment les dispositifs IoT peuvent être utilisés pour automatiser et simplifier certains processus quotidiens.

