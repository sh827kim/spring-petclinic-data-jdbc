# 빌드 및 실행 방법

본 문서에는 총 3가지의 절차가 기술되어있습니다.

1. 프로젝트 gradle 빌드 방법
2. docker image creation
3. kubernetes에 배포하는 방법



## 1. Gradle을 활용한 jar file 생성 절차

gradle clean

```shell
$ ./gradlew clean
```

gradle build

```shell
$ ./gradlew bootJar
```



## 2. Docker Build

docker build

```shell
$ ./gradlew jib
```






## 3. kubernetes deploy

mysql-configuration.yaml 실행을 통해 PV, PVC 생성, mysql pod deploy

```shell
$ kubectl apply -f mysql-configuration.yaml
```

petclinic-configuration.yaml 실행을 통해 deployment 생성, service 생성, ingress configuration

```shell
$ kubectl apply -f petclinic-configuration.yaml
```



## 기존 github 코드와 달라진 점

1. application.properties log 관련 config 일부 수정

2. gradle spring build를 위한 springboot-gradle plugin, docker build를 위한 jib 추가 적용

3. kubernetes configuration 파일 추가






