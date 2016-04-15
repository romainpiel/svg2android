# gradle-svg2android

A gradle task that converts SVGs to Android vector drawable

[source](https://android.googlesource.com/platform/tools/base/+/master/sdk-common/src/main/java/com/android/ide/common/vectordrawable).

_only available through mavenLocal() until stable enough_

To use it:
```groovy
Task transformTask = project.task("rasterizeSvgsFor${variant.name.capitalize()}", type: SVG2AndroidTask) {
    sources = svgFiles
    outputDir = project.file("$project.buildDir/generated/res/$flavorName/$buildType.name/svg/")
}
```

## Motivations
see https://github.com/trello/victor/pull/43
