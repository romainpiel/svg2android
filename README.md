# SVG2Android

An Android build tools library to convert SVGs to Android vector drawables

[source](https://android.googlesource.com/platform/tools/base/+/master/sdk-common/src/main/java/com/android/ide/common/vectordrawable).

## Motivations
see https://github.com/trello/victor/pull/43

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
