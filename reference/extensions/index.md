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

# External service integrations
{: #ref-index}

<p>This {{site.data.keyword.cloud}} documentation collection pertains to the {{site.data.keyword.iot_full}} Lite pricing plan and includes basic getting started information, API references, and general troubleshooting information. 
For the full {{site.data.keyword.iot_short_notm}} feature documentation, see the [{{site.data.keyword.iot_short_notm}} product documentation ![External link icon](../../../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/overview/overview.html) on IBM Knowledge Center. More information about the various plans can be found in [{{site.data.keyword.iot_short_notm}} service plans](/docs/services/IoT?topic=iot-platform-plans_overview#plans_overview). 
</p>
{: important}

External service integration allows you to access data and operations from third-party or external services within your {{site.data.keyword.iot_full}} organization.

## Jasper
{: #jasper}

Jasper is an administration and management platform for SIM devices. Jasper is integrated into the {{site.data.keyword.iot_short_notm}} dashboard, making it possible to administer Jasper devices through your {{site.data.keyword.iot_short_notm}} organization dashboard.

### Supported operations for Jasper

The built-in Jasper integration that is provided by our platform provides support for the following Jasper operations:

- View overall Jasper data
  - Shows status, rate plan, month-to-date data usage, month-to-date SMS usage, month-to-date voice usage, overage limits, date added, and date modified.
- Change SIM activation state
  - Select from inventory, activation ready, activated, deactivated, and retired.
- View SIM usage
  - Shows cycle start date, billable and total data, billable and total SMS, billable and total voice.
  - The cycle start date can be set by using a YYYY-MM-DD date format.
- Send SMS to SIM
- Change rate plan

You can access the supported operations in the device drill-down of a Jasper-connected device after the following configuration steps are completed.

### REST APIs for Jasper
To access the REST API for Jasper, see the Jasper Extension section in the [{{site.data.keyword.iot_short_notm}} HTTP REST API ![External link icon](../../../../icons/launch-glyph.svg "External link icon")](https://docs.internetofthings.ibmcloud.com/apis/swagger/v0002/ext-jasper.html){: new_window} documentation.

### Configuration for Jasper

To connect your Jasper service to your {{site.data.keyword.iot_short_notm}} organization, you must complete two stages of configuration. First, your {{site.data.keyword.iot_short_notm}} must be connected to your Jasper service, then your {{site.data.keyword.iot_short_notm}} devices must be configured.


1. Enable the Jasper extension. To enable Jasper integration with your {{site.data.keyword.iot_short_notm}} organization, complete the following steps:
  1. From the {{site.data.keyword.iot_short_notm}} dashboard, select **Extensions**.
  2. On the **Extensions** page, click **Add Extension**.
  3. Click **Add** next to Jasper.
  4. Enter your Jasper username, password, access key, and domain ID.
  5. Click **Done**.

2. Configure your devices.
You can configure the devices that are connected to both your {{site.data.keyword.iot_short_notm}} organization and your Jasper account to display data from Jasper in the {{site.data.keyword.iot_short_notm}} dashboard.  
**Important:** The Jasper configuration cannot be applied as part of the Add Device process. Only previously connected devices can be configured with Jasper.  
To configure your Jasper-connected devices, complete the following steps:
 1. In the Devices page of your {{site.data.keyword.iot_short_notm}} dashboard, find the Jasper-connected device to configure.
 2. Select the device to open the Device Drilldown view.
 3. Scroll down to Extension Configuration.
 4. Enter the extension configuration by using the following JSON format and then click **Confirm changes** to save your configuration.  

```json  
    {
        "jasper": {
            "iccid": "string"
        }
    }

```

When the organization is successfully configured, the Extensions section is displayed under the Extensions Configuration section in the Device Drilldown view.

## AT&T
{: #att}

### Supported operations for AT&T

The AT&T extension enables the following AT&T operations:

- View overall AT&T data
  - Shows status, rate plan, month-to-date data usage, month-to-date SMS usage, month-to-date voice usage, overage limits, date added, and date modified.
- Change SIM activation state
  - Select from inventory, activation ready, activated, deactivated, and retired.
- View SIM usage
  - Shows: cycle start date, billable and total data, billable and total SMS, billable and total voice.
  - The cycle start date can be set by using a YYYY-MM-DD date format.
- Send SMS to SIM
- Change rate plan

### REST APIs for AT&T
To access the REST API for AT&T, see the AT&T Extension section in the [{{site.data.keyword.iot_short_notm}} HTTP REST API ![External link icon](../../../../icons/launch-glyph.svg "External link icon")](https://docs.internetofthings.ibmcloud.com/apis/swagger/v0002/ext-atnt.html){: new_window} documentation.

### Configuration for AT&T

To connect your {{site.data.keyword.iot_short_notm}} organization to AT&T, you must complete organization configuration and device configuration.

To configure your {{site.data.keyword.iot_short_notm}} platform, complete the following steps:

1. Enable the AT&T extension. To enable AT&T integration with your {{site.data.keyword.iot_short_notm}} organization, complete the following steps:
  1. From the {{site.data.keyword.iot_short_notm}} dashboard, select **Extensions**.
  2. On the **Extensions** page, click **Add Extension**.
  3. Click **Add** next to AT&T.
  4. Enter your AT&T username, password, access key, and domain ID.
  5. Click **Done**.

To connect your {{site.data.keyword.iot_short_notm}} organization with your AT&T account, you must complete two stages of configuration. Complete the the organization configuration and then configure your devices.


2. Configure your devices
You can configure the devices that are connected to both your {{site.data.keyword.iot_short_notm}} organization and your AT&T account to display data from AT&T in the {{site.data.keyword.iot_short_notm}} dashboard.  
**Important:** The AT&T configuration cannot be applied as part of the Add Device process. Only previously connected devices can be configured with AT&T.  
To configure your AT&T-connected devices, complete the following steps:
 1. In the Devices page of your {{site.data.keyword.iot_short_notm}} dashboard, find the AT&T-connected device to configure.
 2. Select the device to open the Device Drilldown view.
 3. Scroll down to Extension Configuration.
 4. Enter the extension configuration by using the following JSON format and then click **Confirm changes** to save your configuration.  

```json  
    {
        "atnt": {
            "iccid": "string"
        }
    }

```

When the organization is successfully configured, the Extensions section is displayed under the Extensions Configuration section in the Device Drilldown view.

## Arm Mbed bridge
{: #arm}

The bridge enables Arm Mbed devices to integrate with {{site.data.keyword.iot_short_notm}} and exchange messages bidirectionally. To enable this integration, you first need to sign up for an Arm Mbed Cloud account and then provide the requested connection information for your {{site.data.keyword.iot_short_notm}} configuration.

### Setup configuration


1. Enable the Arm Mbed bridge extension. To enable the extension, complete the following steps:
  1. From the {{site.data.keyword.iot_short_notm}} dashboard, select **Extensions**.
  2. On the Extensions page, click **Add Extension**.
  3. Click **Add** next to the Arm Mbed bridge extension.
  4. Enter your Arm Mbed access key. You can create it by using the Arm Mbed portal at [https://portal.mbedcloud.com ![External link icon](../../../../icons/launch-glyph.svg "External link icon")](https://portal.mbedcloud.com){: new_window}.
  5. Check the credentials are correct by clicking the **Check Connection** button.
  6. Click **Done**.

### Payload format

The Arm Mbed platform uses two types of incoming messages: notifications and asynchronous responses. {{site.data.keyword.iot_short_notm}} can send commands to devices that are connected to the Arm Mbed platform.

#### Notifications

Notifications are generated by changes in device or sensor data. After {{site.data.keyword.iot_short_notm}} processes the message, it is sent to the device event topic in the same way as a device that is connected directly to {{site.data.keyword.iot_short_notm}}. The event type that is used for notifications that originate on devices that are connected to the Arm Mbed platform is `notify`.

The following code sample shows the payload format for a notification sent by the Arm Mbed platform API:

```
{
  "ep":<endpoint/deviceID>,
  "path":<resource path>,
  "ct":<content type>,
  "payload":<Base64 encoded payload>,
  "max-age":<how long the payload is valid, in seconds>
}
```

#### Asynchronous responses

When {{site.data.keyword.iot_short_notm}} sends a command to a device that is connected to the Arm Mbed platform, the device sends a confirmation message back to {{site.data.keyword.iot_short_notm}}. This confirmation message is called an _asynchronous response_ and uses the event type `asyncResponse`.

The following code sample shows the payload format for an asynchronous response that is sent by the Arm Mbed Cloud service:

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

#### Sending commands to the Arm Mbed platform

{{site.data.keyword.iot_short_notm}} can send commands to devices that are connected to the Arm Mbed platform. Commands that are sent to the Arm Mbed platform must use the following JSON format:

```
{
  "method":<PUT or POST>,
  "deviceId":<endpoint/deviceId>,
  "resourceId":<resource path>,
  "payload": <Base64 encoded payload>
}
```
The method chosen is case sensitive. The initial `/` of the resource path must be skipped.


The payload must be published on the following topic:

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

## Historical data storage
{: #historical_data}

The historical data storage extension lets you locate and configure compatible message storage services, such as [{{site.data.keyword.cloudantfull}} ![External link icon](../../../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/platform/cloudant_connector.html){: new_window} or [{{site.data.keyword.messagehub_full}} ![External link icon](../../../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/platform/message_hub.html){: new_window}, for your IoT data.

## Custom device management packages
{: #device_mgmt}

Device management is a core feature of {{site.data.keyword.iot_short_notm}}, however, it can be extended to develop additional functionality. Custom device management packages must consist of valid JSON and define at least one custom device management action.

For more information on custom device management functions, including an example of the required JSON format, see [device management custom extensions ![External link icon](../../../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/platform/devices/device_mgmt/custom_actions.html){: new_window}.

### Adding a custom device management package

Custom device management packages can be added either by using the {{site.data.keyword.iot_short_notm}} dashboard or by using the API.

To add a custom device management package by using the {{site.data.keyword.iot_short_notm}} dashboard:

1. From your {{site.data.keyword.iot_short_notm}} dashboard, click **Settings** from the navigation bar.
2. Click **Custom Device Management Packages**.
3. Click the **Add Package** button.
4. Select your package file and click **Open**.

To add a custom device management package by using the API, see the [{{site.data.keyword.iot_short_notm}} API documentation ![External link icon](../../../../icons/launch-glyph.svg "External link icon")](https://docs.internetofthings.ibmcloud.com/apis/swagger/v0002/orgAdmin.html){: new_window}.

## Email
{: #email}

Users can be added to {{site.data.keyword.iot_short_notm}} by using email invitations. For information, see  [Managing user access](/docs/services/IoT?topic=iot-platform-managing-user-access#managing-user-access).

To use the email invitation feature, an email extension must be configured to use the SendGrid online service or a Simple Mail Transfer Protocol (SMTP) service. The extension can also use the SendGrid {{site.data.keyword.cloud_notm}} application.

### SendGrid online service

To configure the email extension for use with the SendGrid online service, follow these steps:

1. Retrieve the authorized API key from your SendGrid online account.
2. In your {{site.data.keyword.iot_short_notm}} dashboard, click **Extensions** from the navigation bar.
3. In the **Email** section, click **Setup**.
4. Select **SendGrid with API key**
5. Enter the name and email address of your site administrator and the authorized API key.

### SMTP service

To configure the email extension for use with an SMTP service, follow these steps:

1. In your {{site.data.keyword.iot_short_notm}} dashboard, click **Extensions** from the navigation bar.
2. In the **Email** section, click **Setup**.
3. Select **SMTP**.
4. Enter the configuration details of your SMTP service.

### SendGrid {{site.data.keyword.cloud_notm}} application

To configure the email extension for use with the SendGrid {{site.data.keyword.cloud_notm}} application, follow these steps:

1. Create a dummy application and bind the SendGrid service.  
In order to retrieve the configuration credentials, add and bind the SendGrid service to a dummy application.

 1. From your {{site.data.keyword.cloud_notm}} dashboard, click **Create Service**.
 2. Select the SendGrid service from the catalog and click **Create**.
 3. From the {{site.data.keyword.cloud_notm}} dashboard, add the {{site.data.keyword.runtime_nodejs_full}} application.
 4. Click the {{site.data.keyword.runtime_nodejs_notm}} application from the {{site.data.keyword.cloud_notm}} dashboard and click **Bind a service or API**.
 5. Select the SendGrid service and click **Add**.
 6. Restage the {{site.data.keyword.runtime_nodejs_notm}} application.
2. Prepare to configure the {{site.data.keyword.iot_short_notm}} service.  
{{site.data.keyword.iot_short_notm}} can be configured by using the {{site.data.keyword.iot_short_notm}} dashboard or by using the {{site.data.keyword.iot_short_notm}} API.  
 1. Click the {{site.data.keyword.runtime_nodejs_notm}} application from the {{site.data.keyword.cloud_notm}} dashboard.
 2. Click **Environment Variables** from the navigation bar.
 3. Copy the displayed JSON to a temporary text file.  
 The JSON should have the following format:
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
3. Add the configuration data to the {{site.data.keyword.iot_short_notm}} organization.
 1. Open the {{site.data.keyword.iot_short_notm}} dashboard.
 2. Click **Extensions** from the navigation bar.
 3. Click **Setup** under the **Email** icon.
 4. Select **SendGrid with username**.
 5. Enter the configuration data from the temporary text file.
 6. Click **Done**.
