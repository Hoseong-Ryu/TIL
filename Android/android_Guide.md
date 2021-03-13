# ANDROID
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