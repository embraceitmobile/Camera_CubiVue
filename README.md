![Download](/images/1.png)

# CubiVue Camera
Built on JetPack compose & Compose Material 3. This camera app uses CameraX library.

# Features
- Full screen mode
- Full sensor orientation support
- Image capture & preview

![Images](/images/2.png)


# How To Use

## In Manifest file:

```xml
  <application>
      <activity
         android:name=".MainCameraActivity"/>
         <activity
             android:name=".base.BaseCameraActivity"/>
  </application>
```
    

## From your Fragment or Activity class:

```kotlin
    var mStartForResult: ActivityResultLauncher<Intent> =
    registerForActivityResult(
        ActivityResultContracts.StartActivityForResult()
           ) { result ->
               if (result.resultCode === Activity.RESULT_OK) {
                   var bundle = result.data?.extras
                   Log.e("TAG", "URI ${bundle?.getString("URI")}")
                   }
               }

     mStartForResult.launch(Intent(this, MainCameraActivity::class.java))
```

# License

    Copyright 2022 CubiVue

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
