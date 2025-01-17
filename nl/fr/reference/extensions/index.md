---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-10"

keywords: IoT Platform organization, SIM devices, IBM Watson

subcollection: iot-platform

---

{:new_window: target="\_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:important: .important}

# Intégrations de service externe
{: #ref-index}

<p>Cette série de documents {{site.data.keyword.cloud}} concerne le plan de tarification {{site.data.keyword.iot_full}} Lite et inclut le guide d'initiation, les références d'API et les informations générales relatives au traitement des incidents.
Pour la documentation complète de la fonction {{site.data.keyword.iot_short_notm}}, voir la [documentation du produit {{site.data.keyword.iot_short_notm}} ![Icône de lien externe](../../../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/support/knowledgecenter/fr/SSQP8H/iot/overview/overview.html) dans l'IBM Knowledge Center. Vous trouverez davantage d'informations sur les divers plans dans [{{site.data.keyword.iot_short_notm}}Plans de service](/docs/services/IoT?topic=iot-platform-plans_overview#plans_overview). 
</p>
{: important}

L'intégration de service externe vous permet d'accéder à des données et des opérations à partir de services tiers ou externes au sein de votre organisation {{site.data.keyword.iot_full}}.

## Jasper
{: #jasper}

Jasper est une plateforme de gestion et d'administration des terminaux SIM. Elle est intégrée au tableau de bord {{site.data.keyword.iot_short_notm}}, ce qui vous permet d'administrer des terminaux Jasper via votre tableau de bord d'organisation {{site.data.keyword.iot_short_notm}}.

### Opérations prises en charge pour Jasper

L'intégration Jasper fournie par notre plateforme assure la prise en charge des opérations Jasper suivantes :

- Affichage de l'ensemble des données Jasper
  - Affiche le statut, le plan tarifaire, l'utilisation mensuelle des données à ce jour, l'utilisation mensuelle des SMS à ce jour, l'utilisation mensuelle de la voix à ce jour, les limites de dépassement, les dates d'ajout et les dates de modification.
- Modification de l'état d'activation d'un terminal SIM
  - Sélectionnez un état parmi inventory, activation ready, activated, deactivated et retired.
- Affichage de l'utilisation du terminal SIM
  - Affiche la date de début du cycle, les données facturables et le total des données, les SMS facturables et le total des SMS, la voix facturable et le total pour la voix.
  - La date de début du cycle peut être définie au format de date AAAA-MM-JJ.
- Envoi d'un SMS à un terminal SIM
- Modification du plan tarifaire

Les opérations prises en charge sont accessibles dans le menu d'exploration d'un terminal connecté via Jasper, après l'exécution des étapes de configuration ci-dessous.

### API REST pour Jasper
Pour accéder à l'API REST pour Jasper, voir la section Jasper Extension dans la documentation [{{site.data.keyword.iot_short_notm}} HTTP REST API ![Icône de lien externe](../../../../icons/launch-glyph.svg "Icône de lien externe")](https://docs.internetofthings.ibmcloud.com/apis/swagger/v0002/ext-jasper.html){: new_window}.

### Configuration pour Jasper

Pour connecter votre terminal Jasper à votre organisation {{site.data.keyword.iot_short_notm}}, vous devez suivre deux étapes de configuration. Vous devez connecter votre instance {{site.data.keyword.iot_short_notm}} à votre service Jasper, puis configurer les terminaux {{site.data.keyword.iot_short_notm}}.


1. Activez l'extension Jasper. Pour activer l'intégration de Jasper à votre organisation {{site.data.keyword.iot_short_notm}}, procédez comme suit :
  1. Dans le tableau de bord {{site.data.keyword.iot_short_notm}}, sélectionnez **Extensions**.
  2. Dans la page **Extensions**, cliquez sur **Ajouter une extension**.
  3. Cliquez sur **Ajouter** en regard de Jasper.
  4. Entrez vos nom d'utilisateur, mot de passe, clé d'accès et ID de domaine Jasper.
  5. Cliquez sur **Terminé**.

2. Configurez vos terminaux.
Vous pouvez configurer les terminaux connectés à votre organisation {{site.data.keyword.iot_short_notm}} et à votre compte Jasper afin d'afficher les données provenant de Jasper dans le tableau de bord {{site.data.keyword.iot_short_notm}}.  
**Important :** la configuration de Jasper ne peut pas être appliquée dans le cadre du processus d'ajout de terminal. Seuls les terminaux précédemment connectés peuvent être configurés avec Jasper.  
Pour configurer vos terminaux connectés via Jasper, procédez comme suit :
 1. Dans la page Terminaux de votre tableau de bord {{site.data.keyword.iot_short_notm}}, localisez le terminal connecté via Jasper à configurer.
 2. Sélectionnez le terminal pour ouvrir la vue Exploration du terminal.
 3. Faites défiler l'écran jusqu'à Configuration d'une extension.
 4. Entrez la configuration d'extension au format JSON ci-dessous, puis cliquez sur **Confirmation des modifications** pour sauvegarder votre configuration.  

```json  
    {
        "jasper": {
            "iccid": "string"
        }
    }

```

Une fois l'organisation correctement configurée, la section Extensions s'affiche sous la section Configuration des extensions dans la vue Exploration du terminal.

## AT&T
{: #att}

### Opérations prises en charge pour AT&T

L'extension AT&T permet d'effectuer les opérations AT&T suivantes :

- Affichage de l'ensemble des données AT&T
  - Affiche le statut, le plan tarifaire, l'utilisation mensuelle des données à ce jour, l'utilisation mensuelle des SMS à ce jour, l'utilisation mensuelle de la voix à ce jour, les limites de dépassement, les dates d'ajout et les dates de modification.
- Modification de l'état d'activation d'un terminal SIM
  - Sélectionnez un état parmi inventory, activation ready, activated, deactivated et retired.
- Affichage de l'utilisation du terminal SIM
  - Affiche la date de début du cycle, les données facturables et le total des données, les SMS facturables et le total des SMS, la voix facturable et le total pour la voix.
  - La date de début du cycle peut être définie au format de date AAAA-MM-JJ.
- Envoi d'un SMS à un terminal SIM
- Modification du plan tarifaire

### API REST pour AT&T
Pour accéder à l'API REST pour AT&T, voir la section AT&T Extension dans la documentation [{{site.data.keyword.iot_short_notm}} HTTP REST API ![Icône de lien externe](../../../../icons/launch-glyph.svg "Icône de lien externe")](https://docs.internetofthings.ibmcloud.com/apis/swagger/v0002/ext-atnt.html){: new_window}.

### Configuration pour AT&T

Pour connecter votre organisation {{site.data.keyword.iot_short_notm}} à &T, vous devez effectuer une configuration d'organisation et une configuration de terminal.

Pour configurer votre plateforme {{site.data.keyword.iot_short_notm}}, procédez comme suit :

1. Activez l'extension AT&T. Pour activer l'intégration d'AT&T à votre organisation {{site.data.keyword.iot_short_notm}}, procédez comme suit :
  1. Dans le tableau de bord {{site.data.keyword.iot_short_notm}}, sélectionnez **Extensions**.
  2. Dans la page **Extensions**, cliquez sur **Ajouter une extension**.
  3. Cliquez sur **Ajouter** en regard de AT&T.
  4. Entrez vos nom d'utilisateur, mot de passe, clé d'accès et ID de domaine.
  5. Cliquez sur **Terminé**.

Pour connecter votre organisation {{site.data.keyword.iot_short_notm}} à votre compte AT&T, vous devez suivre deux étapes de configuration. Exécutez la configuration de l'organisation, puis configurez vos terminaux.


2. Configurez vos terminaux.
Vous pouvez configurer les terminaux connectés à votre organisation {{site.data.keyword.iot_short_notm}} et à votre compte AT&T afin d'afficher les données provenant d'AT&T dans le tableau de bord {{site.data.keyword.iot_short_notm}}.  
**Important :** la configuration d'AT&T ne peut pas être appliquée dans le cadre du processus d'ajout de terminal. Seuls les terminaux précédemment connectés peuvent être configurés avec AT&T.  
Pour configurer vos terminaux connectés via AT&T, procédez comme suit :
 1. Dans la page Terminaux de votre tableau de bord {{site.data.keyword.iot_short_notm}}, localisez le terminal connecté via AT&T à configurer.
 2. Sélectionnez le terminal pour ouvrir la vue Exploration du terminal.
 3. Faites défiler l'écran jusqu'à Configuration d'une extension.
 4. Entrez la configuration d'extension au format JSON ci-dessous, puis cliquez sur **Confirmation des modifications** pour sauvegarder votre configuration.  

```json  
    {
        "atnt": {
            "iccid": "string"
        }
    }

```

Une fois l'organisation correctement configurée, la section Extensions s'affiche sous la section Configuration des extensions dans la vue Exploration du terminal.

## Pont Arm Mbed
{: #arm}

Le pont permet aux terminaux Arm Mbed de s'intégrer à {{site.data.keyword.iot_short_notm}} et d'échanger des messages de façon bidirectionnelle. Pour permettre cette intégration, vous devez d'abord vous inscrire afin d'obtenir un compte Arm Mbed Cloud, puis fournir les informations de connexion demandées pour votre configuration {{site.data.keyword.iot_short_notm}}.

### Configuration


1. Activez l'extension de pont Arm Mbed. Pour activer l'extension, procédez comme suit :
  1. Dans le tableau de bord {{site.data.keyword.iot_short_notm}}, sélectionnez **Extensions**.
  2. Dans la page Extensions, cliquez sur **Ajouter une extension**.
  3. Cliquez sur **Ajouter** en regard de l'extension de pont Arm Mbed.
  4. Saisissez votre clé d'accès Arm Mbed. Vous pouvez créer cette clé sur le portail Arm Mbed à l'adresse [https://portal.mbedcloud.com ![Icône de lien externe](../../../../icons/launch-glyph.svg "Icône de lien externe")](https://portal.mbedcloud.com){: new_window}.
  5. Vérifiez que les données d'identification sont correctes en cliquant sur le bouton **Vérifier la connexion**.
  6. Cliquez sur **Terminé**.

### Format de contenu

La plateforme Arm Mbed utilise deux types de messages entrants : les notifications et les réponses asynchrones. {{site.data.keyword.iot_short_notm}} peut envoyer des commandes aux terminaux qui sont connectés à la plateforme Arm Mbed.

#### Notifications

Des notifications sont générées par les modifications apportées aux données de terminal ou de capteur. Après le traitement du message par {{site.data.keyword.iot_short_notm}}, le message est envoyé au sujet d'événement du terminal, comme le ferait un terminal directement connecté à {{site.data.keyword.iot_short_notm}}. Le type d'événement utilisé pour les notifications qui sont émises par les terminaux connectés à la plateforme Arm Mbed est `notify`.

L'exemple de code suivant illustre le format de contenu d'une notification envoyée par l'API de la plateforme Arm Mbed :

```
{
  "ep":<endpoint/deviceID>,
  "path":<resource path>,
  "ct":<content type>,
  "payload":<Base64 encoded payload>,
  "max-age":<how long the payload is valid, in seconds>
}
```

#### Réponses asynchrones

Lorsque {{site.data.keyword.iot_short_notm}} envoie une commande à un terminal connecté à la plateforme Arm Mbed, le terminal renvoie un message de configuration à {{site.data.keyword.iot_short_notm}}. Ce message de confirmation est appelé _réponse asynchrone_ et utilise le type d'événement `asyncResponse`.

L'exemple de code suivant illustre le format de contenu d'une réponse asynchrone envoyée par le service cloud Arm Mbed :

```
{
  "id":<transaction id>,
  "status":<200 is command was sucessfully executed. Check other HTTP response codes>,
  "ct":<content type>,
  "max-age":<how long the payload is valid, in seconds>,
  "payload":<base64 encoded payload>,
  "ep":<endpoint/deviceID affected by the command>,
  "path":<resource path affected by the command>
}
```

#### Envoi de commandes à la plateforme Arm Mbed

{{site.data.keyword.iot_short_notm}} peut envoyer des commandes aux terminaux qui sont connectés à la plateforme Arm Mbed. Les commandes qui sont envoyées à la plateforme Arm Mbed doivent utiliser le format JSON suivant :

```
{
  "method":<PUT or POST>,
  "deviceId":<endpoint/deviceId>,
  "resourceId":<resource path>,
  "payload": <Base64 encoded payload>
}
```
La méthode choisie est sensible à la casse. La barre oblique de début `/` du chemin d'accès à la ressource doit être ignorée.


Le contenu doit être publié dans le sujet suivant :

```
iot-2/type/<device_type>/id/<deviceId>/cmd/<command_type>/fmt/<command_format>
```

<!--
## Orange
{: #orange}

The Orange extension allows you to view SIM card data from devices that are connected to your {{site.data.keyword.iot_short_notm}} and have an Orange SIM card installed.

### Supported operations for Orange

If you have a device that is connected to your {{site.data.keyword.iot_short_notm}} service and has an Orange SIM card, you can use the Orange extension to view the following SIM card data:

- SIM serial number
- Activation status
- Last status change
- Last status refresh
- Location status

### REST APIs for Orange
To access the REST API for Orange, see the Orange Extension section in the [{{site.data.keyword.iot_short_notm}} HTTP REST API ![External link icon](../../../../icons/launch-glyph.svg "External link icon")](https://docs.internetofthings.ibmcloud.com/apis/swagger/v0002/ext-orange.html){: new_window} documentation.

### Configuration for Orange

To enable the Orange extension:

1. From the {{site.data.keyword.iot_short_notm}} dashboard, select **Extensions**.
2. On the **Extensions** page, click **Add Extension**.
3. Click **Add** next to the Orange extension.
4. Enter your Orange user name and password.
6. Click **Done**.

After the Orange extension has been enabled, each device that has an Orange SIM card must be configured to display Orange SIM data.

1. In the devices tab of your {{site.data.keyword.iot_short_notm}} dashboard, find the Orange SIM device to configure.
2. Select the device and scroll down to **Extension Configuration**.
3. Enter the extension configuration by using the following JSON format and then click **Confirm changes** to save your configuration.

```json
    {
        "orange": {
            "serialnumber": "<serial number of Orange SIM>"
        }
    }

```
When the organization is successfully configured, the Extensions section is displayed under the Extensions Configuration section in the Device Drilldown view.
-->

## Stockage de données historiques
{: #historical_data}

L'extension de stockage de données historiques vous permet de localiser et de configurer des services de stockage de message compatibles, par exemple [{{site.data.keyword.cloudantfull}} ![Icône de lien externe](../../../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/support/knowledgecenter/fr/SSQP8H/iot/platform/cloudant_connector.html){: new_window} ou [{{site.data.keyword.messagehub_full}} ![Icône de lien externe](../../../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/support/knowledgecenter/fr/SSQP8H/iot/platform/message_hub.html){: new_window}, pour vos données IoT.

## Packages de gestion des terminaux personnalisés
{: #device_mgmt}

La gestion des terminaux est une fonction de base de {{site.data.keyword.iot_short_notm}} mais elle peut être étendue pour développer des fonctions supplémentaires. Les packages de gestion des terminaux personnalisés doivent être composés d'un document JSON valide et définir au moins une action de gestion des terminaux personnalisée.

Pour plus d'informations sur les fonctions de gestion des terminaux personnalisées, y compris un exemple du format JSON requis, voir [Extensions personnalisées de gestion des terminaux ![Icône de lien externe](../../../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/support/knowledgecenter/fr/SSQP8H/iot/platform/devices/device_mgmt/custom_actions.html){: new_window}.

### Ajout d'un package de gestion des terminaux personnalisé

Vous pouvez ajouter des packages de gestion des terminaux personnalisés depuis le tableau de bord {{site.data.keyword.iot_short_notm}} ou à l'aide de l'API.

Pour ajouter un package de gestion des terminaux personnalisé à l'aide du tableau de bord {{site.data.keyword.iot_short_notm}} :

1. Depuis votre tableau de bord {{site.data.keyword.iot_short_notm}}, cliquez sur **Paramètres** dans la barre de navigation.
2. Cliquez sur **Packages de gestion des terminaux personnalisés**.
3. Cliquez sur le bouton **Ajouter un package**.
4. Sélectionnez votre fichier de package et cliquez sur **Ouvrir**.

Pour ajouter un package de gestion des terminaux personnalisé à l'aide de l'API, voir la [documentation d'API {{site.data.keyword.iot_short_notm}} ![Icône de lien externe](../../../../icons/launch-glyph.svg "Icône de lien externe")](https://docs.internetofthings.ibmcloud.com/apis/swagger/v0002/orgAdmin.html){: new_window}.

## Courrier électronique
{: #email}

Les utilisateurs peuvent être ajoutés à {{site.data.keyword.iot_short_notm}} via des invitations par courrier électronique. Pour plus d'informations, voir  [Gestion des accès utilisateur](/docs/services/IoT?topic=iot-platform-managing-user-access#managing-user-access).

L'utilisation de la fonction d'invitation par courrier électronique nécessite de configurer une extension de messagerie pour utiliser le service en ligne SendGrid ou un service SMTP (Simple Mail Transfer Protocol). L'extension peut également utiliser l'application {{site.data.keyword.cloud_notm}} SendGrid.

### Service en ligne SendGrid

Pour configurer l'extension de messagerie à utiliser avec le service en ligne SendGrid, procédez comme suit :

1. Récupérez la clé d'API autorisée à partir de votre compte en ligne SendGrid.
2. Dans votre tableau de bord {{site.data.keyword.iot_short_notm}}, cliquez sur **Extensions** dans la barre de navigation.
3. Dans la section **Adresse électronique**, cliquez sur **Configurer**.
4. Sélectionnez **SendGrid avec clé d'API**.
5. Entrez le nom et l'adresse électronique de votre administrateur de site, ainsi que la clé d'API autorisée.

### Service SMTP

Pour configurer l'extension de messagerie à utiliser avec un service SMTP, procédez comme suit :

1. Dans votre tableau de bord {{site.data.keyword.iot_short_notm}}, cliquez sur **Extensions** dans la barre de navigation.
2. Dans la section **Adresse électronique**, cliquez sur **Configurer**.
3. Sélectionnez **SMTP**.
4. Entrez les détails de configuration pour votre service SMTP.

### Application {{site.data.keyword.cloud_notm}} SendGrid

Pour configurer l'extension de messagerie à utiliser avec l'application {{site.data.keyword.cloud_notm}} SendGrid, procédez comme suit :

1. Créez une application factice et établissez une liaison au service SendGrid.  
Pour récupérer les données d'identification de configuration, ajoutez et liez le service SendGrid à une application factice.

 1. Depuis votre tableau de bord {{site.data.keyword.cloud_notm}}, cliquez sur **Créer un service**.
 2. Sélectionnez le service SendGrid dans le catalogue, puis cliquez sur **Créer**.
 3. Dans le tableau de bord {{site.data.keyword.cloud_notm}}, ajoutez l'application {{site.data.keyword.runtime_nodejs_full}}.
 4. Cliquez sur l'application {{site.data.keyword.runtime_nodejs_notm}} à partir du tableau de bord {{site.data.keyword.cloud_notm}}, puis cliquez sur **Lier un service ou une API**.
 5. Sélectionnez le service SendGrid, puis cliquez sur **Ajouter**.
 6. Reconstituez en production l'application {{site.data.keyword.runtime_nodejs_notm}}.
2. Préparez-vous à configurer le service {{site.data.keyword.iot_short_notm}}.  
{{site.data.keyword.iot_short_notm}} peut être configuré depuis le tableau de bord {{site.data.keyword.iot_short_notm}} ou à l'aide de l'API {{site.data.keyword.iot_short_notm}}.  
 1. Cliquez sur l'application {{site.data.keyword.runtime_nodejs_notm}} dans le tableau de bord {{site.data.keyword.cloud_notm}}.
 2. Cliquez sur **Variables d'environnement** dans la barre de navigation.
 3. Copiez les données JSON affichées dans un fichier texte temporaire.  
 Les données JSON doivent se présenter au format suivant :
```
{
  "name": "SendGridServiceName",
  "label": "user-provided",
  "credentials": {
    "password": "xxx",
    "hostname": "smtp.sendgrid.net",
    "username": "username"
  }
}
```
3. Ajoutez les données de configuration à l'organisation {{site.data.keyword.iot_short_notm}}.
 1. Ouvrez le tableau de bord {{site.data.keyword.iot_short_notm}}.
 2. Cliquez sur **Extensions** dans la barre de navigation.
 3. Cliquez sur **Configurer** sous l'icône **Courrier électronique**.
 4. Sélectionnez **SendGrid avec nom d'utilisateur**.
 5. Entrez les données de configuration à partir du fichier texte temporaire.
 6. Cliquez sur **Terminé**.
