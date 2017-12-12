---

copyright:

years: 2017
lastupdated: "2017-11-01"

---

{:new_window: target="\_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# 할당량
이 절에서는 플랜 유형별로 {{site.data.keyword.iot_full}} 서비스에 대해 설정된 한계에 대한 정보를 제공합니다. 멀티테넌트 시스템의 모든 사용자에 대해 오용으로 인한 부정적인 영향이 성능에 미치지 않도록 공정 사용 정책의 일부로 한계가 지정되어 있습니다. 또한 한계를 사용하면 실제 사용자 워크로드가 부주의로 인해 서비스 거부(DoS) 공격으로 식별되는 일을 방지할 수 있습니다.

## 소개
{: #metrics_about}

할당량은 리소스에 설정되는 상한을 지정합니다. 사용량이 지정된 한계를 초과하면 사용자 요청이 지연되거나 거부될 수 있습니다. 예외 상황에서는 시스템 안정성에 영향을 미치는 한계 초과로 인해 다른 사용자가 영향을 받지 않도록 {{site.data.keyword.iot_short_notm}} 조직이 일시중단될 수 있습니다.

다음 표에는 {{site.data.keyword.iot_short_notm}}에 대한 한계가 나열되어 있습니다. 디바이스에 대해 명시적으로 나열되지 않는 한, 지정된 대부분의 한계는 {{site.data.keyword.iot_short_notm}} 조직에서의 한계입니다. 일부 한계는 최대값이 적용되는 반면, 다른 한계는 요청 시 늘어날 수 있습니다. 지정된 한계보다 높은 한계가 필요하면 [티켓(![외부 링크 아이콘](../../../icons/launch-glyph.svg))](https://support.ng.bluemix.net/gethelp/){: new_window}을 여십시오.

## 메시징
{: #messaging_metrics}

메트릭        | 라이트 플랜  | 표준 및 고급 보안 플랜     | 데디케이티드 플랜
------------- | -------------|------------- |
디바이스 유형의 최대 수 |50 |1000 |1000
동시에 연결된 디바이스의 최대 수 | 500| 500K. 50,000개가 넘는 디바이스를 연결하려면 플랜 논의를 위해 연락하십시오. | 500K
등록된 디바이스의 최대 수 |500| 1백만 | 증분당 100K
최대 ['A' 애플리케이션 - 공유](../applications/mqtt.html#scalable_apps) |1| 10개의 공유 구독. 각각 50개의 인스턴스를 가짐|10개의 공유 구독. 각각 50개의 인스턴스를 가짐
최대 ['a' 애플리케이션 - 비공유](../applications/mqtt.html#client_connections) |500개의 API 키 | 2000개의 API 키 | 2000개의 API 키
월간 최대 데이터 | 200MB	| 무제한 |무제한
디바이스 연결 수|10/초 | 300/초 |300/초 
디바이스-투-클라우드 전송(MQTT) - 디바이스 | 5개 메시지/초 또는 20KB/초 | 10개 메시지/초 또는 40KB/초 |10개 메시지/초 또는 40KB/초
디바이스-투-클라우드 전송(MQTT) - 게이트웨이 | 50개 메시지/초 또는 200KB/초 | 100개 메시지/초 또는 400KB/초| 100개 메시지/초 또는 400KB/초
디바이스-투-클라우드 전송(MQTT) - 애플리케이션 | 10개 메시지/초 또는 40KB/초 | 20개 메시지/초 또는 80KB/초| 20개 메시지/초 또는 80KB/초
디바이스-투-클라우드 전송(MQTT) - 조직당 | 5000개 메시지/초 | 6000개 메시지/초 | 6000개 메시지/초
디바이스-투-클라우드 전송(HTTP) - 디바이스 | 30개 메시지/분 또는 2KB/초 | 1개 메시지/초 또는 4KB/초 | 1개 메시지/초 또는 4KB/초
디바이스-투-클라우드 전송(HTTP) - 게이트웨이 | 5개 메시지/초 또는 20KB/초 | 10개 메시지/초 또는 40KB/초 | 10개 메시지/초 또는 40KB/초
디바이스-투-클라우드 전송(HTTP) - 애플리케이션 | 1개 메시지/초 또는 4KB/초| 2개 메시지/초 또는 8KB/초 | 2개 메시지/초 또는 8KB/초
디바이스-투-클라우드 전송(HTTP) - 조직당 | 500개 메시지/초 | 600개 메시지/초 | 600개 메시지/초
클라우드-투-디바이스 전송(MQTT) - 디바이스 |1개 메시지/초 |2개 메시지/초 또는 8KB/초 |2개 메시지/초 또는 8KB/초
클라우드-투-디바이스 전송(MQTT) - 게이트웨이 | 10개 메시지/초 |20개 메시지/초 또는 80KB/초 |20개 메시지/초 또는 80KB/초 
클라우드-투-디바이스 전송(MQTT) - 애플리케이션 | 10개 메시지/초 |20개 메시지/초 또는 80KB/초 |20개 메시지/초 또는 80KB/초 
클라우드-투-디바이스 전송(MQTT) - 조직당 |1000개 메시지/초 | 12K 메시지/초|12K 메시지/초
클라우드-투-디바이스 전송(HTTP) - 디바이스당 버스트 비율 | 30개 메시지/분| 30개 메시지/분 | 30개 메시지/분
클라우드-투-디바이스 전송(HTTP) - 조직당 |  1000개 메시지/초|  1200개 메시지/초 |  1200개 메시지/초
인바운드 수신 미확인 메시지의 최대 수 - 디바이스당 | 10 |10 |10
인바운드 수신 미확인 메시지의 최대 수 - 게이트웨이당 | 1000 |1000 |1000
인바운드 수신 미확인 메시지의 최대 수 - 애플리케이션 연결당 |2000 | 2000|2000
아웃바운드 수신 미확인 메시지의 최대 수 - 디바이스당 |10  |10 |10
디바이스-투-클라우드 지속성 | 24시간|24시간 |24시간
클라우드-투-디바이스 지속성 |48시간(기본값). 최대 7일 및 50 큐 깊이| 48시간(기본값). 최대 7일 및 50 큐 깊이 |48시간(기본값). 최대 7일 및 50 큐 깊이
QoS 1 메시지 전달을 위한 최대 재시도 간격 | 다시 연결 시 재시도 |다시 연결 시 재시도 |다시 연결 시 재시도
연결 비활동 한계(활성 유지 간격) | 연결 시 클라이언트가 지정함 |연결 시 클라이언트가 지정함 |연결 시 클라이언트가 지정함 
웹 소켓 연결 기간 |연결 시 클라이언트가 지정함 | 연결 시 클라이언트가 지정함 |연결 시 클라이언트가 지정함 
최대 메시지 크기 | 128KB |128KB |128KB 
디바이스당 최대 구독 수 |50 |50 |50
애플리케이션당 최대 구독 수 | 500|500|500
큐 깊이 - 디바이스당 구독에 따른 최대 버퍼링된 메시지 수 | 50 |50 |50
'A' 애플리케이션에 대한 최대 버퍼링된 메시지 수 |50K 지속 가능, 50K 지속 불가능 |50K 지속 가능, 50K 지속 불가능 |50K 지속 가능, 50K 지속 불가능


## API
{: #api_metrics}

메트릭        | 라이트 플랜  | 표준 및 고급 보안 플랜     | 데디케이티드
------------- | -------------|------------- |
API 호출|10/초 |10/초 |10/초 

## 규칙 엔진
{: #rule_engine_metrics}

메트릭        | 라이트 플랜  | 표준 및 고급 보안 플랜     | 데디케이티드
------------- | -------------|------------- |
조직 당 최대 규칙 수 |100|1000|1000
규칙당 조치 수|10|10|10

## 디바이스 관리
{: #device_mgmt_metrics}

메트릭        | 라이트 플랜  | 표준 및 고급 보안 플랜     | 데디케이티드
------------- | -------------|------------- |
디바이스당 진단 로그의 최대 크기 |500K|500K|500K
보유한 진단 로그의 최대 히스토리 버전 |2|2|2
진단 로그를 보유하는 최대 시간 |7일| 7일|7일
인플라이트 메시지당 시작된 최대 조치 수 |200|200|200
조치당 최대 디바이스 수 |5000 |5000 | 5000

## 마지막 이벤트 캐시
{: #last_event_metrics}

메트릭        | 라이트 플랜  | 표준 및 고급 보안 플랜     | 데디케이티드
------------- | -------------|------------- |
디바이스당 이벤트 ID의 최대 수 |5|5|5
최대 형식 수 |2|3|3
마지막 이벤트 캐시의 만기 |12개월 |12개월 | 12개월

## 확장
{: #extensions_metrics}

메트릭        | 라이트 플랜  | 표준 및 고급 보안 플랜     | 데디케이티드
------------- | -------------|------------- |
바인드할 수 있는 최대 서비스 수 |12|12|12

## 정보 관리
{: #information_management_metrics}

메트릭        | 라이트 플랜  | 표준 및 고급 보안 플랜     | 데디케이티드
------------- | -------------|------------- |
JSON 페이로드의 최대 중첩 깊이 |5|5|5
최대 JSON 문자열 크기 |512|512|512

## 보안
{: #security_metrics}

메트릭        | 라이트 플랜  | 표준 및 고급 보안 플랜     | 데디케이티드
------------- | -------------|------------- |
최대 사용자 정의 역할 수 |20|20|20
최대 사용자 구성원 수 |1000|1000|1000
리소스 그룹의 최대 디바이스 수 |300|300|300
게이트웨이에 지정된 최대 리소스 그룹 수 |10|10|10
디바이스가 속하는 최대 리소스 그룹 수 |10|10|10

## 사용자 인터페이스
{: #UI_metrics}

메트릭        | 라이트 플랜  | 표준 및 고급 보안 플랜     | 데디케이티드
------------- | -------------|------------- |
최대 대시보드 수 |50|50|50
보드의 최대 카드 수 |30|30|30