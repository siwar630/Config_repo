# Spring-cloud-config-example

Ce dépôt contient les fichiers de configuration pour les microservices utilisés avec Spring Cloud Config Server. Les configurations sont organisées par application.

## Structure du dépôt

Le dépôt est structuré avec un fichier de configuration distinct pour chaque application. Chaque fichier contient les propriétés de configuration spécifiques à l'application correspondante.

### Fichiers de configuration

- `Config-api-gateway.properties`
- `Config-service1.properties`
- `Config-service2.properties`

## Utilisation avec Spring Cloud Config Server

### Configuration du serveur de configuration

Assurez-vous que votre serveur de configuration Spring Cloud est configuré pour lire les fichiers de ce dépôt. Voici un exemple de configuration pour le serveur de configuration :

``properties``


spring.application.name=config-server

server.port=8888

spring.cloud.config.server.git.uri=https://github.com/siwar630/Config_repo

spring.cloud.config.server.git.username=siwar630

spring.cloud.config.server.git.password=************

spring.cloud.config.server.git.default-label=main


eureka.client.service-url.defaultZone=http://localhost:8761/eureka/

eureka.client.register-with-eureka=true

eureka.client.fetch-registry=true 

### Configuration des applications clients

Assurez-vous que chaque application cliente est configurée pour utiliser le serveur de configuration. Voici un exemple de configuration pour une application cliente :

`properties`

spring.application.name=service1

spring.cloud.config.uri=http://localhost:8888

## Tester les services avec Eureka

![Capture d’écran (125)](https://github.com/user-attachments/assets/39c2153f-dd5e-471e-80f2-1bdc8dc0d54f)

## Lancer le serveur de configuration
Clonez ce dépôt sur votre machine locale.
Assurez-vous que votre serveur de configuration pointe vers ce dépôt.
Lancez le serveur de configuration.

Vérification du serveur de configuration
Pour vérifier que le serveur de configuration fonctionne correctement, accédez aux URLs suivantes dans votre navigateur ou utilisez un outil comme curl :

Pour service1 : http://localhost:8888/Config-service1/default

![Capture d’écran (126)](https://github.com/user-attachments/assets/696c066b-1687-4dfb-8e75-30dea8c2a49c)
de meme pour les autres services .


