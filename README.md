# SVG2Android

An Android build tools library to convert SVGs to Android vector drawables

Source: [Android Studio build tools](https://android.googlesource.com/platform/tools/base/+/master/sdk-common/src/main/java/com/android/ide/common/vectordrawable).

## Motivations

The main motivation behind this repo is to use it in a gradle plugin to convert SVGs to Android vector drawables.
A good candidate for that would be trello/victor:
see https://github.com/trello/victor/pull/43 for more details

## Usage

```gradle
compile 'com.romainpiel.svgtoandroid:svgtoandroid:0.1.0'
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
