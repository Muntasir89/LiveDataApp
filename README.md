# LiveDataApp
It is an Android Architecture Components.
It is observable Data Holder Class and Lifecycle aware.
- MutableLiveData  class is a subclass of LiveData class. In other words, MutableLiveData  child class has created by extending the parent  LiveData class.
- A MutableLiveData instance can do everything a LiveData instnce can do and more.
- Data in a LiveData object are only readable. We cannot update those values.
- But, in the other hand, a Mutable LiveData object allows us to change(update) its values.
- So, When we are creating our own live data(mostly in ViewModels), we define them as MutableLiveData.
- But, when we are getting live data from other libraries such as Room and Retrofit we get them as LiveData.
```kotlin
class MainViewModel: ViewModel() {
    private val factsLiveDataObject = MutableLiveData<String>("This is a fact")

    val factsLiveData: LiveData<String> get() = factsLiveDataObject
    fun updateLiveData(){
        factsLiveDataObject.value = "Another Facts"
    }
}
```
### Output:
![ouput](https://user-images.githubusercontent.com/78687005/201042951-5d5668ac-8aff-4061-8226-d43073162021.gif)
