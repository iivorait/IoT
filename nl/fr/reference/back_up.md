---

copyright:

years: 2017, 2019
lastupdated: "2019-04-05"

keywords: Data backup Use, data backup strategy, records of device management requests

subcollection: iot-platform

---

{:new_window: target="\_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:important: .important}



# Sauvegarde des données
{: #back_up}

<p>Cette série de documents {{site.data.keyword.cloud}} concerne le plan de tarification {{site.data.keyword.iot_full}} Lite et inclut le guide d'initiation, les références d'API et les informations générales relatives au traitement des incidents.
Pour la documentation complète de la fonction {{site.data.keyword.iot_short_notm}}, voir [la documentation du produit {{site.data.keyword.iot_short_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/support/knowledgecenter/fr/SSQP8H/iot/overview/overview.html) dans l'IBM Knowledge Center.  Vous trouverez davantage d'informations sur les divers plans dans [{{site.data.keyword.iot_short_notm}}Plans de service](/docs/services/IoT?topic=iot-platform-plans_overview#plans_overview). 
</p>
{: important}

Utilisez les informations ci-après pour comprendre la stratégie de sauvegarde des données d'{{site.data.keyword.iot_full}}.

## Quel type de données est sauvegardé ?

Les types de données client suivants sont sauvegardés dans le cadre de la stratégie {{site.data.keyword.iot_short_notm}} :

- Les informations organisationnelles
- Les informations sur les terminaux
- Les clés d'API et les jetons
- Les informations utilisateur
- Tous les enregistrements des demandes de gestion des terminaux, notamment l'historique de toutes les demandes initiées, par exemple l'état en cours de la demande
- Les définitions des regroupements de demandes de gestion de terminaux personnalisées

**Remarque :** toutes les données d'une organisation sont conservées pendant les 14 jours qui suivent l'annulation de l'accès au service. Contactez le support dans un délai de 14 jours pour restaurer une organisation.

## Quel type de données n'est pas sauvegardé ?

Les types de données suivants ne sont pas sauvegardés dans {{site.data.keyword.iot_short_notm}} :

- Les événements de terminaux
- L'état de messagerie transitoire, par exemple les données en transit
- Les messages MQTT envoyés dans le cadre d'une demande de gestion de terminal
<!-- - Analytics rules and alert configuration -->

## A quelle fréquence les données sont-elles sauvegardées et où sont-elles stockées ?

Les données sont sauvegardées toutes les 24 heures.

Les données sont stockées hors site à partir du service {{site.data.keyword.iot_short_notm}} principal afin d'offrir une redondance géographique et de permettre la restauration des services en cas d'incident majeur. Les clients sont contactés si une restauration des données est requise. Toutes les données sont chiffrées et respectent les exigences de protection des données locales.

Les emplacements hors site actuellement utilisés pour la sauvegarde de données sont les suivants :

Emplacement                   | Emplacement de la sauvegarde                      
------------- | -------------
IBM Cloud Sud des Etats-Unis (Dallas)| Washington
IBM Cloud Royaume-Uni (Londres) | Francfort
IBM Cloud Allemagne (Francfort) | Londres
IBM Cloud Dedicated | En fonction de la demande client au moment de la commande de {{site.data.keyword.iot_short_notm}} Dedicated

**Remarque :** les emplacements sont susceptibles de changer dans le futur afin de prendre en compte les lois sur la confidentialité des données, par exemple l'impact potentiel du Brexit sur les règles de souveraineté des données de l'Union européenne.
