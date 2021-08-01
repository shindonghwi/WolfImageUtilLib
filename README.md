WolfImageUtil
=====

WolfImageUtil가 제공하는 기능은 아래와 같다.
1. 비트맵 압축
2. 비트맵 byteArray 가져오기
3. 비트맵 비율에 맞게 리사이즈
4. 비트맵 회전
5. 정방향 비트맵 가져오기

------------------------------------------------------

Download [![](https://jitpack.io/v/shindonghwi/WolfImageUtilLib.svg)](https://jitpack.io/#shindonghwi/WolfImageUtilLib)
--------

### Gradle
```
[ project - build.gradle ]
allprojects {
  repositories {
    maven { url 'https://jitpack.io' }
  }
}
```
or 
```
[ setting.gradle ]
dependencyResolutionManagement {
  repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
  repositories {
    google()
    mavenCentral()
    maven { url 'https://jitpack.io' }
  }
}
```
------------------------------------------------------
```
[ app - build.gradle ]
dependencies {
  ...
  implementation 'com.github.shindonghwi:WolfImageUtilLib:release_version' // release_version 자리에 위에 작성되있는 0.0.12와 같은 문자열을 기입하면됩니다.
}
```
------------------------------------------------------

## How To Use

#### 1. 비트맵을 압축하는 기능
```
// return -> Bitmap
WolfImageUtil.bitmapCompress(
    bitmap = /** bitmap */,
    format = /** Bitmap.CompressFormat.PNG or Bitmap.CompressFormat.JPEG */,
    compressionRate = /** value -> 0 until 100 */
)
```

#### 2. 비트맵 byteArray 가져오기
```
// return -> Bitmap
WolfImageUtil.bitmapToByteArray(
    bitmap = /** bitmap */,
    format = /** Bitmap.CompressFormat.PNG or Bitmap.CompressFormat.JPEG */,
    compressionRate = /** value -> 0 until 100 */
)
```

#### 3. 비트맵 비율에 맞게 리사이즈
```
// default 가로 최대 크기 : 1024
// default 세로 최대 크기 : 1024
// return -> Bitmap
WolfImageUtil.bitmapRatioResize(
    bitmap = /** bitmap */,
    maxWidth: Int = 1024,
    maxHeight: Int = 1024
)
```

#### 4. 비트맵 회전
```
// return -> Bitmap
WolfImageUtil.bitmapRotate(
    bitmap = /** bitmap */,
    degrees: Int /** 회전 값 */
)
```

#### 5. 정방향 비트맵 가져오기
```
// 갤러리에서 이미지를 가져온 후 서버에 업로드를하게 되면 이미지가 회전되어 있는 현상이 발생합니다.
// 그래서 이미지를 정방향으로 변경해주는 함수 입니다.
// return -> Bitmap
WolfImageUtil.bitmapForward(
    bitmap = /** bitmap */,
    filepath = /** 이미지 파일의 경로 */
)
```


## License 
 ```code
Copyright 2021 ShinDongHwi

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
