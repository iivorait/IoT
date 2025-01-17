---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-05"

keywords: Client connection URLs, MQTT protocol, device authentication tokens

subcollection: iot-platform

---

{:new_window: target="\_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}
{:important: .important}

# Informações de conexão para aplicativos, dispositivos e gateways
{: #connect_devices_apps_gw}

<p>Essa coleção de documentação do {{site.data.keyword.cloud}} pertence ao plano de precificação Lite do {{site.data.keyword.iot_full}} e inclui informações básicas de introdução, referências de API e informações gerais de resolução de problemas. 
Para a documentação de recurso integral do {{site.data.keyword.iot_short_notm}}, consulte a [documentação do produto do {{site.data.keyword.iot_short_notm}} ![Ícone de link externo](../../../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/overview/overview.html) no IBM Knowledge Center. Mais informações sobre os vários planos podem ser localizadas em [{{site.data.keyword.iot_short_notm}} planos de serviço](/docs/services/IoT?topic=iot-platform-plans_overview#plans_overview). 
</p>
{: important}

É possível conectar aplicativos, dispositivos e gateways ao {{site.data.keyword.iot_full}} usando o protocolo MQTT. Também é possível usar a API de REST HTTP para conectar dispositivos ao {{site.data.keyword.iot_short_notm}}.
{: shortdesc}


## URLs de conexão do cliente
{: #client_connect_url}

Para conectar clientes de dispositivo, aplicativo e gateway à sua instância do {{site.data.keyword.iot_short_notm}}, use as URLs (Localizadores Uniformes de Recursos) de conexão a seguir:

### Endereço do sistema de mensagens

<pre class="pre"><var class="keyword varname">orgId</var>.messaging.internetofthings.ibmcloud.com</pre>
{: codeblock}

### URL (Localizador Uniforme de Recursos) de conexão da API (interface de programação de aplicativos) REST HTTP (Protocolo de Transporte de Hipertexto)

<pre class="pre"><code class="hljs">https://<var class="keyword varname">orgId</var>.internetofthings.ibmcloud.com/api/v0002/device/types/<var class="keyword varname">typeId</var>/devices/<var class="keyword varname">deviceId</var>/events/<var class="keyword varname">eventId</var></code></pre>
{: codeblock}

**Notas**
- Em que *orgId* é o ID exclusivo da organização que foi gerado quando você registrou a instância de serviço.
- Se você estiver conectando um dispositivo ou aplicativo ao serviço de iniciação rápida, especifique 'quickstart' como o valor de *orgId*.

### Segurança de porta
{: #client_port_security}

Dispositivos, gateways e aplicativos conectam-se ao {{site.data.keyword.iot_short_notm}} usando o protocolo MQTT ou HTTP. As conexões podem ser não seguras ou seguras.

|Tipo de conexão |Protocolo|Número da porta|
|:---|:---|:---|
|Não segura*|MQTT e HTTP|1883 ou 80|
|Segura (TLS)|MQTT e HTTPS|8883 ou 443|

&ast; As portas 1883 e 80 ficam desativadas por padrão para o sistema de mensagens. Para obter informações sobre como mudar a configuração padrão, consulte [Configurando políticas de segurança ![Ícone de link externo](../../../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/platform/reference/security/set_up_policies.html#set_up_policies.html){: new_window}.

MQTT é suportado sobre TCP e WebSockets. Os clientes MQTT se conectam usando credenciais apropriadas, como tokens de autenticação de dispositivo para dispositivos e chaves API (interface de programação de aplicativos) e tokens para aplicativos. Como o sistema de mensagens MQTT para a porta não segura 1883 envia essas credenciais em texto simples, sempre use as alternativas seguras 8883 ou 443 em seu lugar. As credenciais do TLS são sempre criptografadas quando enviadas por meio de portas seguras. Esteja ciente de que se deve ativar o TLS no aplicativo (por exemplo, usando o método `tls_set()` na biblioteca Python MQTT). Caso contrário, os dados poderão ser enviados de forma não segura.

Ao usar o sistema de mensagens MQTT seguro nas portas 8883 ou 443, bibliotecas de cliente mais recentes confiam automaticamente no certificado padrão apresentado pelo {{site.data.keyword.iot_short_notm}}. Se esse não for o caso para o ambiente do cliente, será possível fazer download e usar a cadeia de certificados completa de [messaging.pem ![Ícone de link externo](../../../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/ibm-watson-iot/iot-python/blob/master/src/wiotp/sdk/messaging.pem){: new_window}. Se você tiver transferido por upload um certificado customizado, poderá ser necessário assegurar que a cadeia de confiança apropriada seja incluída no ambiente do cliente.

## Configuração de firewall
{: #firewall_configuration .sectiontitle}

Para conectar dispositivos e aplicativos ao {{site.data.keyword.iot_short_notm}}, deve-se assegurar que qualquer firewall esteja configurado para permitir tráfego em portas específicas. Um firewall pode residir em sua máquina local, em seu roteador ou como parte de sua rede corporativa.

Assegure-se de que os endereços IP necessários estejam abertos e ativados para comunicação.

|Região | Endereço IP|Portas do sistema de mensagens</br> (não seguras) | Portas do sistema de mensagens (seguras)|
|:---|:---|:---| :---|
|us-south|169.45.2.16/28* </br>169.46.7.56/29</br>169.48.234.208/29</br>169.62.202.128/29|1883.80 | 8883.443|
|eu-gb|159.8.169.208/28* </br>158.175.111.152/29</br>158.176.104.24/29</br>141.125.70.152/29|1883.80 | 8883.443|
|eu-de|159.122.121.80/28* </br>149.81.125.176/29</br>158.177.82.208/29</br>161.156.96.80/29|1883.80 | 8883.443|
|Iniciação rápida|169.45.2.16/28* </br>169.46.7.56/29</br>169.48.234.208/29</br>169.62.202.128/29|1883.80 | indisponível|
|{{site.data.keyword.iot_short_notm}} dedicado|Entre em contato com o representante da {{site.data.keyword.IBM}}.|-| - |
&ast; Não será mais usado após o primeiro trimestre de 2019.

## Requisito do TLS
{: #tls_requirements}

Algumas bibliotecas do cliente de Segurança da Camada de Transporte (TLS) não suportam domínios que incluem um curinga. Se não for possível mudar as bibliotecas com sucesso, desative a verificação de certificado.

Os requisitos do TLS dependem se você está se conectando ao {{site.data.keyword.iot_short_notm}} usando o protocolo MQTT ou HTTP. As seções a seguir mostram os conjuntos de criptografia que serão suportados se o certificado de servidor padrão for usado. Se você estiver usando seu próprio certificado
de cliente, os conjuntos de criptografia suportados dependerão do certificado usado.

### Requisitos de TLS para conexões MQTT

{{site.data.keyword.iot_short_notm}}  requer TLS v1.2. Assegure-se de que pelo menos um dos seguintes conjuntos de cifras seja permitido:

- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
- TLS_DHE_RSA_WITH_AES_128_GCM_SHA256
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
- TLS_DHE_RSA_WITH_AES_128_CBC_SHA
- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
- TLS_DHE_RSA_WITH_AES_256_GCM_SHA384
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
- TLS_DHE_RSA_WITH_AES_256_CBC_SHA
- TLS_RSA_WITH_AES_128_GCM_SHA256
- TLS_RSA_WITH_AES_256_GCM_SHA384

### Requisitos de TLS para conexões HTTP

Se você está usando o certificado do servidor padrão, o {{site.data.keyword.iot_short_notm}} requer o TLS v1.2. Assegure-se de que pelo menos um dos seguintes conjuntos de cifras seja permitido:


- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
- TLS_DHE_RSA_WITH_AES_128_CBC_SHA
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
- TLS_DHE_RSA_WITH_AES_256_CBC_SHA
- TLS_RSA_WITH_AES_256_CBC_SHA
- TLS_RSA_WITH_AES_128_CBC_SHA

Aumente a intensidade de sua criptografia usando as cifras de sigilo de encaminhamento ECDHE ou DHE em sua lista de cifras.

## Autenticação de cliente MQTT
{: #mqtt_authentication}

**Importante:** cada cliente MQTT requer um identificador de cliente exclusivo. Se você tentar conectar um cliente em sua organização usando um identificador de cliente que já esteja conectado, a primeira conexão será desfeita.

Dispositivos e gateways conectados diretamente ao {{site.data.keyword.iot_short_notm}} exibem um ícone de status no painel para indicar que estão conectados. Os dispositivos conectados indiretamente por meio de um gateway são mostrados como desconectados porque o painel não está ciente de dispositivos conectados por meio de um gateway.

### Identificadores de cliente MQTT

Para que dispositivos, aplicativos e gateways serem autenticados com sucesso, defina cada cliente MQTT usando os identificadores de cliente e formato a seguir:

|Tipo de Cliente |ID|Formato do ID MQTT|
|:---|:---|:---|
|Aplicativos|a|<pre class="pre">a:<var class="keyword varname">orgId</var>:<var class="keyword varname">appId</var></pre>
|Aplicativos Escaláveis|x|<pre class="pre">A:<var class="keyword varname">orgId</var>:<var class="keyword varname">appId</var></pre>
|Dispositivos|d|<pre class="pre">d:<var class="keyword varname">orgId</var>:<var class="keyword varname">deviceType</var>:<var class="keyword varname">deviceId</var></pre>|
|Gateways|h|<pre class="pre">g:<var class="keyword varname">orgId</var>:<var class="keyword varname">typeId</var>:<var class="keyword varname">deviceId</var></pre>|

Em que
- *orgId* é o ID da organização exclusivo de seis caracteres que foi gerado quando você registrou o serviço.
- *appId* é um identificador de sequência exclusivo definido pelo usuário para o cliente.
- *deviceId* identifica exclusivamente um dispositivo ou gateway entre todos os tipos e é análogo a um número de série.
- *device_type* é o identificador para o tipo de dispositivo que está se conectando e é análogo a um número de modelo.
- *typeId* é um identificador do tipo de gateway que está se conectando e é análogo a um número de modelo.

Os valores de *appId*, *type_id*, *device_type* e *device_id* devem ter no máximo 36 caracteres e podem conter somente:
- Caracteres alfanuméricos (a-z, A-Z, 0-9)
- Traços (-)
- Sublinhados (_)
- Pontos (. )

**Notas:**
- Ao se conectar ao serviço de iniciação rápida, autenticação não é necessária.
- Você não precisa registrar um aplicativo antes de se conectar.

Para obter informações sobre o formato de assinaturas compartilhadas, consulte [Conectividade do MQTT para aplicativos ![Ícone de link externo](../../../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/platform/applications/mqtt.html){: new_window}.


### Conectando aplicativos usando MQTT

Aplicativos do {{site.data.keyword.iot_short_notm}} requerem a chave API (interface de programação de aplicativos) para se conectarem a uma organização. Quando uma chave API (interface de programação de aplicativos) é registrada, um token é gerado e ele deve ser usado com essa chave API.

O código a seguir fornece um exemplo de uma chave API (interface de programação de aplicativos):

<pre class="pre">a-<var class="keyword varname">orgId</var>-a84ps90Ajs</pre>
{: codeblock}

O exemplo a seguir mostra um token de autenticação típico:

```
 MP$08VKz!8rXwnR-Q*
```

Ao fazer uma conexão MQTT usando uma chave API (interface de programação de aplicativos), assegure que os requisitos a seguir sejam atendidos:

- O identificador de cliente MQTT está no formato a seguir: a:*orgId*:*appId*
- O nome do usuário MQTT é a chave API (interface de programação de aplicativos), por exemplo, a-*orgId*-a84ps90Ajs
- A senha do MQTT é o token de autenticação, por exemplo, *MP$08VKz!8rXwnR-Q**

Para obter mais informações, consulte [Conectividade do MQTT para aplicativos ![Ícone de link externo](../../../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/platform/applications/mqtt.html){: new_window}.

### Autenticação do Dispositivo

#### Nome
do Usuário
O serviço do {{site.data.keyword.iot_short_notm}} suporta apenas autenticação baseada em token para dispositivos; portanto, cada dispositivo tem apenas um nome de usuário válido.
Um valor igual a `use-token-auth` indica ao serviço que o token de autenticação para o gateway ou dispositivo é usado como a senha para a conexão MQTT.

Para obter mais informações, consulte [Conectividade do MQTT para dispositivos ![Ícone de link externo](../../../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/platform/devices/mqtt.html){: new_window}.

#### senhas
Se o cliente estiver usando a autenticação baseada em token, envie o token de autenticação do dispositivo como a senha para todas as conexões MQTT.
