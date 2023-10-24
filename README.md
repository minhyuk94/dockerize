# dockerize

### memo
```
docker-compose.yaml의 delegated는 컨테이너가 일부 데이터를 기록해야 하는 경우에
결과를 호스트머신에 즉시 반영하지 않고 배치로 기본 처리함으로써 성능 향상을 기대할 수 있다.
```

```
composer.dockerfile 에서 ignoer-platform-reqs 옵션을 통해
일부 종속성이 누락되더라도 실행 가능하도록 할 수 있음.
```

### docker-compose를 통해 laravel docker container 구축하기
```
--rm 옵션은 컨테이너 중지 시 삭제되도록 설정
docker-compose run --rm composer create-project --prefer-dist laravel/laravel .
```

### nginx laravel 연동시시키
```
target을 지정해서 compose up시킬 수 있음.
-d 는 detached mode로 backgound에서 작동시킬 때 사용.

docker-compose up -d server php mysql 

server php mysql를 구동할때마다 입력하는건 불필요하므로
depends_on 에 추가해서 같이 실행되도록 하는것도 가능.

docker-compose up -d 
이미지가 있는지 확인하고 이미지가 있으면 그 이미지를 사용하는것(리빌드 하는게 아님)
만일 Dockerfile에 변경이 있다면 build를 옵션에 추가해줘야함

docker-compose up -d --build server
```

