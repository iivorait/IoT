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

# Risoluzione dei problemi di {{site.data.keyword.iot_short_notm}}
{: #ts}

<p>Questa raccolta di documentazione {{site.data.keyword.cloud}} è relativa al piano dei prezzi {{site.data.keyword.iot_full}} Lite e include le informazioni introduttive di base, le guide di riferimento API e delle informazioni generali per la risoluzione dei problemi.
Per la documentazione completa della funzione {{site.data.keyword.iot_short_notm}}, vedi la [documentazione del prodotto {{site.data.keyword.iot_short_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/overview/overview.html) nell'IBM Knowledge Center. Ulteriori informazioni sui vari piani sono disponibili in [Piani di servizio {{site.data.keyword.iot_short_notm}}](/docs/services/IoT?topic=iot-platform-plans_overview#plans_overview). 
</p>
{: important}

Queste sono le risposte a domande sulla risoluzione dei problemi comuni riguardo l'utilizzo di {{site.data.keyword.iot_full}} su {{site.data.keyword.cloud_notm}}.
{:shortdesc}

## Problema di accesso alla tua organizzazione {{site.data.keyword.iot_short_notm}}
{: #access-expiry-problem}

Non puoi accedere all'organizzazione {{site.data.keyword.iot_short_notm}} che ti appartiene.
{:shortdesc}

Non puoi accedere alla tua organizzazione {{site.data.keyword.iot_short_notm}} direttamente utilizzando l'URL dell'organizzazione o utilizzando `https://internetofthings.ibmcloud.com`.
{: tsSymptoms}

Il tuo accesso alla tua organizzazione {{site.data.keyword.iot_short_notm}} potrebbe essere scaduto. Le organizzazioni {{site.data.keyword.iot_short_notm}} create utilizzando {{site.data.keyword.cloud}} utilizzano i profili utente temporanei per impostazione predefinita.
{: tsCauses}

Puoi risolvere questo problema accedendo alla tua organizzazione {{site.data.keyword.iot_short_notm}} utilizzando {{site.data.keyword.cloud_notm}} e modificando le impostazioni sulla scadenza del tuo profilo utente. Per modificare le tue impostazioni di scadenza utente:

1. Dal tuo dashboard {{site.data.keyword.cloud_notm}}, apri il tuo servizio {{site.data.keyword.iot_short_notm}}.
2. Fai clic su **Members** dalla barra di navigazione.
3. Fai clic sull'icona **Edit**.
4. Deseleziona la casella di spunta **Access expires** e fai clic su **Save**.
{: tsResolve}

## Problema di connessione a {{site.data.keyword.iot_short_notm}}
{: #connection_problem}

La tua connessione a {{site.data.keyword.iot_short_notm}} cade o si scollega in modo imprevisto.
{:shortdesc}

Quando tenti di collegarti a {{site.data.keyword.iot_short_notm}}, il tuo dispositivo o applicazione riceve un errore.
{: tsSymptoms}

Potresti avere più di un dispositivo che sta tentando di connettersi con ID client e credenziali uguali. È consentita solo una singola connessione per ogni ID client. Non puoi avere più connessioni simultanee che utilizzano lo stesso ID. Le applicazioni possono condividere la stessa chiave API, ma MQTT richiede che l'ID sia sempre univoco.
{: tsCauses}

Puoi escludere questo motivo verificando che non hai più dispositivi che stanno tentando di connettersi utilizzando le stesse credenziali.
{: tsResolve}

## Il dispositivo si scollega a intermittenza da {{site.data.keyword.iot_short_notm}}
{: #disconnection_problem}

La connessione del tuo dispositivo a {{site.data.keyword.iot_short_notm}} cade a intermittenza in modo imprevisto.
{:shortdesc}

Un dispositivo collegato a un servizio {{site.data.keyword.iot_short_notm}} viene scollegato a intermittenza. Il dispositivo di ricollega ma viene di nuovo scollegato in modo imprevisto dopo un poco tempo.
{: tsSymptoms}

Potrebbe essere che quando ti colleghi, stai utilizzando un valore per un opzione di ping MQTT troppo piccola, che la rende simile a un timeout. Ad esempio, se il MQTT client è impostato in modo non corretto, i ping non vengono ricevuti in modo tempestivo e la connessione viene chiusa.
{: tsCauses}

Puoi risolvere questo problema confermando di aver correttamente impostato i parametri ping e KeepAlive per la tua connessione.   
{: tsResolve}
