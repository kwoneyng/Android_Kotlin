## Kotlin코드로 View 생성 및 삽입

#### 액티비티에서 View 생성

- ```kotlin
  // 뷰를 생성한다
  val inflater = applicationContext.getSystemService(Context.LAYOUT_INFLATER_SERVICE) as LayoutInflater
  inflater.inflate(R.layout.dog_list,null,true)

  // 미리 설정한 레이아웃을 inflater로 불러오고 원하는 View 밑에 .addView(inflater)를 통해 추가 할 수 있다.
  ```