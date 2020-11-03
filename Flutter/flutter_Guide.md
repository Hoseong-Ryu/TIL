# 플러터 
## 에러 발생
```! Some Android licenses not accepted. To resolve this```
1. Open your terminal
2. type flutter doctor --android-licenses
3. press y to accept every license.
## 플러터 위젯 계층 
![플러터 위젯 계층 이미지](./img/flutter-1.png)
## 레이아웃 만들기
아이템을 수평으로 정렬 ```row``` 위젯
아이템을 수직으로 정렬 ```Column``` 위젯
남은 공간 모두 채우는  ```Expanded``` 위젯


## 웹 빌드
최신 버전의 플러터 sdk를 사용하고 웹 지원
~~~ 
flutter channel beta
flutter upgrade
flutter config --enable-web
~~~

웹 지원
~~~
flutter create <myapp> OR .
cd myapp
~~~

웹 빌드
~~~
flutter build web
~~~

