# SoobinBatchToyProject
Spring Batch 를 활용하여 토이 프로젝트를 개발해봤습니다.

Spring Batch 는 대용량의 데이터를 단발성으로 처리하기 위해서 만들어졌으나,
개인 프로젝트로 대용량의 데이터를 다루기 어려워 간단한 예제로 진행하였습니다.

## 프로젝트의 흐름

##### job
- job 을 실행합니다.
- job 하위에는 여러 Step 이 존재할 수 있으나 전 하나의 Job 으로 구성했습니다.
##### step
- Step 은 Reader 와 Write 를 실행시킵니다.
- Reader 에서 대용량의 데이터를 읽어옵니다.
- Write 는 데이터를 저장합니다.
- chunk 수를 지정합니다.
##### reader
- 네이버 URL 을 활용하여 TITLE 을 구해옵니다.
![image](https://github.com/soobinJung/NaverSportNewsBatch/assets/66097044/32e95457-a3ec-464a-9a80-ef656a4d73cf)

##### write
- chunk 수에 따라 데이터를 분할하여 저장합니다.
![image](https://github.com/soobinJung/NaverSportNewsBatch/assets/66097044/429f7d64-454d-4d7b-86d9-e7b71c976b18)



## 배치 어플리케이션의 조건
##### 대용량 데이터
- 배치 어플리케이션은 대량의 데이터를 가져오거나, 전달하거나, 계산하는 등의 처리를 할 수 있어야 합니다.
##### 자동화
- 배치 어플리케이션은 심각한 문제 해결을 제외하고는 사용자 개입 없이 실행되어야 합니다.
##### 견고성
- 배치 어플리케이션은 잘못된 데이터를 충돌/중단 없이 처리할 수 있어야 합니다.
##### 신뢰성
- 배치 어플리케이션은 무엇이 잘못되었는지를 추적할 수 있어야 합니다. (로깅, 알림)
##### 성능
- 배치 어플리케이션은 지정한 시간 안에 처리를 완료하거나 동시에 실행되는 다른 어플리케이션을 방해하지 않도록 수행되어야합니다.
