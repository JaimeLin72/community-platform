# Arquitectura de la Plataforma Comunitaria (Zen)

+Zen se compone principalmente de un puñado de microservicios:

![](services-2.png)

+Estos servicios residen en los siguientes repositorios de código:

* [cp-zen-platform](https://github.com/CoderDojo/cp-zen-platform)
* [cp-events-service](https://github.com/CoderDojo/cp-events-service)
* [cp-badges-service](https://github.com/CoderDojo/cp-badges-service)
* [cp-salesforce-service](https://github.com/CoderDojo/cp-salesforce-service)
* [cp-dojos-service](https://github.com/CoderDojo/cp-dojos-service)
* [cp-users-service](https://github.com/CoderDojo/cp-users-service)

## cp-zen-platform

cp-zen-platform contiene todo el código de interface [AngularJS](https://angularjs.org/), así como también implementa los REST API del lado del servidor. El servidor está escrito utilizando el entorno [Hapi](http://hapijs.com/). Las llamadas al REST API son en su mayoría llamadas al proxy a través de microservicios [Seneca](http://senecajs.org/).

## cp-events-service

El servicio de eventos implementa todos los eventos relacionados con la funcionalidad en el Zen. Los datos de eventos se almacena en [PostgresSQL](http://www.postgresql.org/).

## cp-badges-service

El servicio Badges implementa todas las funcionalidades relacionadas con Badges de Zend. Este servicio le habla a un [BadgeKit](http://badgekit.openbadges.org) a través de los BadgeKit API, todos los datos relativos al Badge están almacenados en BadgeKit.

## cp-salesforce-service

El servicio de Salesforce implementa toda la funcionalidad relacionada con Salesforce en el Zen. Este servicio conversa directamente con [Salesforce](https://developer.salesforce.com/). Salesforce es utilizado internamente por el personal del CoderDojo Foundation.

## cp-dojos-service

El servicio Dojos implementa toda la funcionalidad relacionada con Dojos en el Zen. Todos los datos relacionados con dojo están almacenados en [PostgresSQL](http://www.postgresql.org/).

## cp-users-service

El servicio Users implementa todas las funcionalidades relacionadas a usuarios en Zen. Todos los datos de usuarios son almacenados en [PostgresSQL](http://www.postgresql.org/).

## Servicios Externos

La lista completa de servicios externos con los que integra Zen son los siguientes:

* [NodeBB](https://nodebb.org/) - Foros Mentores y Jovenes
* [Google Apps Gmail, reCAPTCHA](https://developers.google.com/) - correos auto-creados
* [Google Maps](https://maps.google.com) - Google Maps
* [Salesforce](https://www.salesforce.com/) - Salesforce
* [Intercom](https://www.intercom.io/) - Intercom
* [New Relic](http://newrelic.com/) - New Relic
* [CrowdIn](https://crowdin.com/project/zen-community-platform) - Plataforma de Administración de Localización
* [Mozilla BadgeKit](http://badgekit.openbadges.org/) - Open Badges
* [MailTrap](https://mailtrap.io/) - Prueba de email

## Alojamiento

Zen es desplegado en [AWS](http://aws.amazon.com/) y también utiliza una gran cantidad de servicios de AWS, ninguno de los cuales es utilizado directamente desde el código de arriba. Cómo está construído y desplegado Zen está más allá de los alcances de este documento.
