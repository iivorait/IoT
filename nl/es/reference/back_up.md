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



# Copia de seguridad de datos
{: #back_up}

<p>Esta recopilación de documentación de {{site.data.keyword.cloud}} pertenece al plan de precios Lite de {{site.data.keyword.iot_full}} e incluye información básica de iniciación, referencias de API e información general de resolución de problemas. 
Para obtener la documentación completa de {{site.data.keyword.iot_short_notm}}, consulte la [documentación de producto de {{site.data.keyword.iot_short_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/overview/overview.html) en IBM Knowledge Center. Encontrará más información acerca de los distintos planes en [Planes del servicio {{site.data.keyword.iot_short_notm}}](/docs/services/IoT?topic=iot-platform-plans_overview#plans_overview). 
</p>
{: important}

Utilice la siguiente información para entender la estrategia de copia de seguridad de datos para {{site.data.keyword.iot_full}}.

## ¿De qué tipo de datos se realiza copia de seguridad?

Actualmente, se realiza copia de seguridad de los siguientes tipos de datos de cliente como parte de la estrategia de {{site.data.keyword.iot_short_notm}}:

- Información organizativa
- Información de dispositivos
- Claves de API y señales
- Información de usuario
- Todos los registros de las solicitudes de gestión de dispositivos, incluyendo el historial de cualquier solicitud iniciada; por ejemplo, el estado actual de la solicitud
- Definiciones de paquetes de solicitud de gestión de dispositivos personalizadas

**Nota:** Todos los datos de una organización se conservan durante 14 días después del desaprovisionamiento de servicios. Póngase en contacto con el soporte dentro de la ventana de 14 días para que se restaure una organización.

## ¿De qué tipo de datos no se realiza copia de seguridad?

De los siguientes tipos de datos no se realiza copia de seguridad en {{site.data.keyword.iot_short_notm}}:

- Sucesos de dispositivo
- Estado de mensaje transitorio, por ejemplo: datos en curso
- Mensajes MQTT enviados y recibidos como parte de una solicitud de gestión de dispositivos
<!-- - Analytics rules and alert configuration -->

## ¿Con qué frecuencia se realiza copia de seguridad de los datos y dónde se almacena?

La copia de seguridad de los datos se realiza una vez cada 24 horas.

Los datos se almacenan fuera del servicio principal de {{site.data.keyword.iot_short_notm}}, proporcionando redundancia geográfica y habilitando que los servicios se restauren en caso de una incidencia importante. Se contactará con los clientes si la restauración de datos fuese necesaria en algún momento. Todos los datos están cifrados y cumplen con los requisitos de protección de datos locales.

Actualmente se utilizan las siguientes ubicaciones externas para la copia de seguridad de datos:

Ubicación                   | Ubicación de la copia de seguridad                      
------------- | -------------
IBM Cloud EE.UU. sur (Dallas)| Washington
IBM Cloud Reino Unido (Londres) | Frankfurt
IBM Cloud Alemania (Frankfurt) | Londres
IBM Cloud Dedicated | Según la solicitud del cliente cuando pide {{site.data.keyword.iot_short_notm}} Dedicated

**Nota:** Las ubicaciones futuras pueden cambiar para reflejar leyes de privacidad de datos, por ejemplo el impacto potencial del Brexit en las reglas de soberanía de los datos de la Unión Europea.
