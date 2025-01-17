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



# Backup de dados
{: #back_up}

<p>Essa coleção de documentação do {{site.data.keyword.cloud}} pertence ao plano de precificação Lite do {{site.data.keyword.iot_full}} e inclui informações básicas de introdução, referências de API e informações gerais de resolução de problemas. 
Para a documentação de recurso integral do {{site.data.keyword.iot_short_notm}}, consulte a [documentação do produto do {{site.data.keyword.iot_short_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/overview/overview.html) no IBM Knowledge Center. Mais informações sobre os vários planos podem ser localizadas em [{{site.data.keyword.iot_short_notm}} planos de serviço](/docs/services/IoT?topic=iot-platform-plans_overview#plans_overview). 
</p>
{: important}

Use as informações a seguir para entender a estratégia de backup de dados do {{site.data.keyword.iot_full}}.

## Qual tipo de dados é submetido a backup?

Os seguintes tipos de dados do cliente estão sendo submetidos a backup atualmente como parte da estratégia do {{site.data.keyword.iot_short_notm}}:

- Informações organizacionais
- Informações sobre o dispositivo
- Chaves API e tokens
- Informações sobre o usuário
- Todos os registros de solicitações de gerenciamento de dispositivo, incluindo o histórico de quaisquer solicitações iniciadas, por exemplo: o estado atual da solicitação
- Definições de pacotes configuráveis de solicitações de gerenciamento de dispositivo customizado

**Nota:** todos os dados de uma organização são retidos por 14 dias após o desprovimento de serviços. Entre em contato com o suporte dentro da janela de 14 dias para que uma organização seja restaurada.

## Que tipo de dados não é submetido a backup?

Os seguintes tipos de dados não são submetidos a backup no {{site.data.keyword.iot_short_notm}}:

- Eventos de dispositivo
- Estado de sistema de mensagens transiente, por exemplo: dados em andamento
- Mensagens MQTT que são enviadas e recebidas como parte de uma solicitação de gerenciamento de dispositivo
<!-- - Analytics rules and alert configuration -->

## Com que frequência é feito backup de dados e onde está armazenado?

Os dados são submetidos a backup uma vez a cada 24 horas.

Os dados são armazenados de forma externa do serviço {{site.data.keyword.iot_short_notm}} principal, fornecendo redundância geográfica e permitindo que os serviços sejam restaurados no caso de um incidente significativo. Os clientes serão contatados se a restauração de dados for necessária. Todos os dados são criptografados e estão em conformidade com os requisitos de proteção de dados local.

Os seguintes locais externos são usados atualmente para backup de dados:

Localização                   | Local de backup                      
------------- | -------------
IBM Cloud US Sul (Dallas)| Washington
IBM Cloud United Kingdom (Londres) | Frankfurt
IBM Cloud Alemanha (Frankfurt) | Londres
IBM Cloud Dedicated | Conforme solicitação do cliente ao pedir o {{site.data.keyword.iot_short_notm}} Dedicado

**Nota:** Os futuros locais podem mudar para refletir as leis de privacidade de dados, por exemplo, o impacto potencial de Brexit nas regras de soberania de dados da UE.
