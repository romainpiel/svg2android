# SVG2Android

[![Build Status](https://travis-ci.org/RomainPiel/svg2android.svg?branch=master)](https://travis-ci.org/RomainPiel/svg2android)

An Android build tools library that converts SVGs to Android vector drawables

Source: [Android Studio build tools](https://android.googlesource.com/platform/tools/base/+/master/sdk-common/src/main/java/com/android/ide/common/vectordrawable).

## Motivations

The main motivation behind this repo is to use it in a gradle plugin to convert SVGs to Android vector drawables.
A good candidate for that would be trello/victor:
see https://github.com/trello/victor/pull/43 for more details

## Usage

```gradle

repositories {
    jcenter()
}

dependencies {
    compile 'com.romainpiel.svgtoandroid:svgtoandroid:0.1.0'
}
```

```java
File destination = new File(resDir, getDestinationFile(svgFile.name))
OutputStream outStream = new FileOutputStream(destination)
String error = Svg2Vector.parseSvgToXml(svgFile, outStream)
if (!error.isEmpty()) {
    logger.error(error)
}

outStream.flush()
outStream.close()
```

## License
```
Copyright 2016 Romain Piel

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```