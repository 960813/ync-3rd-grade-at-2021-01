## 나인패치(Nine Patch) 이미지

* 이미지가 늘어나거나 줄어들 때 생기는 이미지 왜곡을 해결하는 방법을 정의한 것
* 서로 다른 해상도를 가진 여러 단말에 dp 단위로 뷰의 크기를 맞추다 보면 이미지 크기가 자동 조절되면서 왜곡되는 현상 발생 => 나인패치 이미지로 해결

## 커스텀 뷰 생성

* 뷰를 상속하여 새로운 뷰를 정의할 수 있음
* 뷰의 크기를 결정할 수도 있고 뷰 위에 그래픽을 그릴 수도 있음

### Reference

```java
public void onMeasure (int widthMeasureSpec, int heightMeasureSpec) {}
public void onDraw (Canvas canvas) {}

void setMeasuredDimension (int measuredWidth, int measuredHeight) {}
```



## Activity LifeCycle

* onCreate: 
* onStart: 화면과 관련된 동작 수행
  * 뷰에 그래픽이 그려질 때 onDraw() 메소드가 호출됨
  * 다시 그릴경우 invalidate() 메소드 사용(임의로 onDraw 호출하는 효과를 보임)
* onResume:
* Execute(실행)
* onPause
* onStop=>Execute(Other Activity)

## 리싸이클러뷰

* 일종의 어댑터 뷰 / ListView와 동일하다고 생각하면 된다(단, 소스코드의 구성과 약간 다름)
* 원본 데이터 => Apadater => AdapterView

### 커스텀 어댑터

* 레이아웃의 어떤 위젯에 어떤 정보를 출력할 것인질르 지정하기 위해 어댑터를 작성
* 어댑터는 원본과 어댑터 뷰 사이를 중계
  * 메서드를 통해 대화