# ANDROID
## MVVM 패턴
### 개념
- 액티비티에 기능을 붙이다보면 액티비티가 무거워지거나 혹은 종속성이 너무 강해 테스트가 힘들고 유지보수가 어려워진다. 이런 고민 때문에 MVVM 패턴이 등장했다. MVVM은 `View` - `ViewModel` - `Model`을 이용해 각각의 역할을 분리하여 가독성과 재사용성을 높인 디자인 패턴이다. 
![](./img/MVVM.png)
### 장점
-  LiveData로 직접 `View`를 바꿔줄 필요가 없다.
- **생명주기로부터 안전**하고 **메모리 누수**를 방지할 수 있다. 
- 기능별로 모듈화되어있어 유닛테스트가 쉽다.
### 단점
- 다른 아키텍처보다 클래스가 많아서 복잡하다.
### 
## Jetpack
### DataBinding
- gradle 설정
  ~~~
    android {
       buildFeatures {
            dataBinding = true
        } 
    }
  ~~~
  ~~~
  <layout>

    <data>
        <variable
            name="tripList"
            type="com.example.프로젝트 이름.<dataclass이름>" />
    </data>
  </layout>
  ~~~
- xml코드에 `<layout>`으로 시작한다.
- 양방향 데이터 바인딩을 지원한다.

### ViewBinding
- gradle 설정
  ~~~
    android {
       buildFeatures {
            viewBinding = true
        } 
    }
  ~~~
- 뷰 바인딩 무시 속성을 추가 할 수 있다.
- `DataBinding`보다 컴파일 시간이 더 빠르다 