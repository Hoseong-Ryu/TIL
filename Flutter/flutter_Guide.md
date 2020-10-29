# 플러터 
## 에러 발생
```! Some Android licenses not accepted. To resolve this```
1. Open your terminal
2. type flutter doctor --android-licenses
3. press y to accept every license.

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
