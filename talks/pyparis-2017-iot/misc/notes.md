## plan

* Quel type d'IoT, la nécessité d'avoir des protocoles adaptés

* Description des protocoles pour l'IoT:
   * CoAP: requêtes GET/PUT/POST/DELETE + OBSERVE
       * implémentations python: Aiocoap, TxThings, CoAPthon (plus jeune)
       * Plugin Navigateur: Copper
   * MQTT: publish/subscribe avec broker
       * implémentations: paho (eclipse, implémentation de référence),
         hbmqtt (basé asyncio)

* Rappel du projet initial:
    * Quelques mots sur RIOT
    * démo permanente
    * données affichées en temps réel sur un tableau de bord,
    * intégrer facilement les nouveautés développée dans RIOT
    * Projet OpenSource => chacun peut se l'approprier et n'est pas contraint
      de passer par un Cloud propriétaire

* Projet Pyaiot:
    * Description architecture globale:
        * page web vuejs + client websocket,
        * broker
        * gateways distribuées multi-protocoles
    * Remontée des données en temps-réel grâce aux websockets
    * Basé sur asyncio => utilisation en priorité, le futur de Python
    * Python 3 => pas de compatibilité python 2 mais problème de compatibilité entre
      versions de python 3 (ex: python 3.4.2 != 3.4.4, mot clé arrivés en 3.5, etc)
    * Application web en Tornado
        * Compatible asyncio
        * API Client/serveur websocket super simple
        * Pas le plus performant => considérer aiohttp un jour ou un autre
    * Problème de la découverte des ressources => géré au niveau des gateways
    * Indépendant des protocoles IoT: supporte CoAP, MQTT et websocket
    * Le projet fournit des noeuds exemples pour expliquer le workflow
    * What's next:
        * Déploiement des services sous forme de conteneur docker
        * Plus de sécurité avec les websocket secure/https
        * Documentation
        * Tests
        * Ajout d'une gateway pour noeuds en HTTP

* Conclusion
    * Python adapté pour l'IoT
    * Prototypage rapide alors que le sujet est complexe
    * Prise en main de la programmation asynchrone avec Python
    * Benchmarks
