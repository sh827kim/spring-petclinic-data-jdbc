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
$ ./gradlew build
```

jar file 문제없이 실행 가능한지 확인

```shell
$ java -jar build/libs/spring-petclinic-data-jdbc-2.1.0.BUILD-SNAPSHOT.jar
```



## 2. Dockerfile Build

docker build

```shell
$ docker build -t sh827kim/petclinic-spark:1.0 .
```

image push to dockerhub

```shell
$ docker push sh827kim/petclinic-spark:1.0
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

2. gradle spring build를 위한 springboot-gradle plugin 추가 적용

3. Dockerfile 추가

4. kubernetes configuration 파일 추가






