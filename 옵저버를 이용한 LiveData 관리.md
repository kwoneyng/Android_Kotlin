## 옵저버를 이용한 LiveData 관리

#### MutableSupplier object 생성후 LiveData 정의

- ```kotlin
// Data를 관리하는 코틀린 파일인 Data.kt에 정의함
object MutableSupplier {
    var user: MutableLiveData<User> = MutableLiveData()
    var dogsSelected: MutableLiveData<ArrayList<DogInfo>> = MutableLiveData()
    var dogs: MutableLiveData<ArrayList<DogInfo>> = MutableLiveData()
    var currentAddress: MutableLiveData<String> = MutableLiveData("내 위치")
}
  ```

#### 옵저버를 데이터에 설정하고 안에 원하는 작업을 실행한다.

- ```kotlin
  MutableSupplier.dogsSelected.observe(this, Observer {
                dogs ->
            mRecyclerViewTop.adapter!!.notifyDataSetChanged()
            Supplier.dogsSelected = dogs
        })
  // 리사이클러 뷰의 리스트가 변경되었을때 자동으로 어댑터에 반영하기 위해서 adapter.notifyDAtaSetChanged() 를 넣어야한다.
  ```

