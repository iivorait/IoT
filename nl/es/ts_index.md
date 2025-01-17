---

copyright:
  years: 2016, 2019
lastupdated: "2019-04-05"

keywords: Watson IoT Platform, Watson IoT Platform organization, IoT Platform, troubleshooting

subcollection: iot-platform

---

{:new_window: target="\_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:important: .important}

# Resolución de problemas de {{site.data.keyword.iot_short_notm}}
{: #ts}

<p>Esta recopilación de documentación de {{site.data.keyword.cloud}} pertenece al plan de precios Lite de {{site.data.keyword.iot_full}} e incluye información básica de iniciación, referencias de API e información general de resolución de problemas. 
Para obtener la documentación completa de {{site.data.keyword.iot_short_notm}}, consulte la [documentación de producto de {{site.data.keyword.iot_short_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/overview/overview.html) en IBM Knowledge Center. Encontrará más información acerca de los distintos planes en [Planes del servicio {{site.data.keyword.iot_short_notm}}](/docs/services/IoT?topic=iot-platform-plans_overview#plans_overview). 
</p>
{: important}

A continuación se muestran las respuestas a preguntas de resolución de problemas comunes sobre cómo utilizar {{site.data.keyword.iot_full}} en {{site.data.keyword.cloud_notm}}.
{:shortdesc}

## Problema al acceder a la organización de {{site.data.keyword.iot_short_notm}}
{: #access-expiry-problem}

No puede iniciar una sesión en una organización de {{site.data.keyword.iot_short_notm}} de la que es propietario.
{:shortdesc}

No puede iniciar una sesión en su organización de {{site.data.keyword.iot_short_notm}} directamente mediante el URL o mediante `https://internetofthings.ibmcloud.com`.
{: tsSymptoms}

Es posible que su acceso a la organización de {{site.data.keyword.iot_short_notm}} haya caducado. Las organizaciones de {{site.data.keyword.iot_short_notm}} creadas mediante {{site.data.keyword.cloud}} utilizan de forma predeterminada perfiles de usuario temporales.
{: tsCauses}

Puede solucionar este problema accediendo a su organización de {{site.data.keyword.iot_short_notm}} mediante {{site.data.keyword.cloud_notm}} y modificando el valor de caducidad de su perfil de usuario. Para cambiar los valores de caducidad de usuario:

1. En el panel de control de {{site.data.keyword.cloud_notm}}, abra el servicio {{site.data.keyword.iot_short_notm}}.
2. Pulse **Miembros** en la barra de navegación.
3. Pulse el icono **Editar**.
4. Desmarque el recuadro de selección **El acceso caduca** y pulse **Guardar**.
{: tsResolve}

## Problema de conexión al {{site.data.keyword.iot_short_notm}}
{: #connection_problem}

Su conexión al {{site.data.keyword.iot_short_notm}} se descarta o se desconecta de forma inesperada.
{:shortdesc}

Cuando intente conectarse al {{site.data.keyword.iot_short_notm}}, su dispositivo o aplicación recibirá un error.
{: tsSymptoms}

Es posible que tenga más de un dispositivo que esté intentando conectarse con el mismo ID de cliente y las mismas credenciales. Solo se permite una única conexión por ID de cliente. No puede tener varias conexiones simultáneas que utilicen el mismo ID. Las aplicaciones pueden compartir la misma clave de API, pero MQTT requiere que el ID de cliente sea siempre exclusivo.
{: tsCauses}

Puede descartar esta razón verificando que no tiene varios dispositivos que estén intentando conectarse mediante las mismas credenciales.
{: tsResolve}

## El dispositivo se desconecta de forma intermitente de {{site.data.keyword.iot_short_notm}}
{: #disconnection_problem}

La conexión del dispositivo al {{site.data.keyword.iot_short_notm}} se descarta intermitentemente de forma inesperada.
{:shortdesc}

Un dispositivo que está conectado al servicio de {{site.data.keyword.iot_short_notm}} está desconectado de forma intermitente. El dispositivo vuelve a conectarse, pero se desconecta de forma inesperada de nuevo después de unos minutos.
{: tsSymptoms}

Es posible que cuando se conecte esté utilizando un valor para una opción de ping de MQTT que es demasiado bajo, lo que hace que tenga el aspecto de que la conexión ha excedido el tiempo de espera. Por ejemplo, si el MQTT del cliente se ha establecido de forma incorrecta, no se reciben los pings de forma puntual, y se cierra la conexión.
{: tsCauses}

Puede solucionar este problema confirmando que ha establecido correctamente los parámetros ping y KeepAlive para la conexión.   
{: tsResolve}
