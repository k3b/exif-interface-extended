[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![CI status](https://github.com/Tommy-Geenexus/exif-interface-extended/workflows/Instrumentation%20Tests/badge.svg)](https://github.com/Tommy-Geenexus/exif-interface-extended/actions?query=workflow%3A%22Instrumentation+Tests%22)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.github.tommy-geenexus/exif-interface-extended/badge.svg)](https://maven-badges.herokuapp.com/maven-central/io.github.tommy-geenexus/exif-interface-extended)
# exif-interface-extended
This library
- includes the full [AndroidX ExifInterface](https://developer.android.com/reference/androidx/exifinterface/media/ExifInterface) API,
without major behavioral changes*

- is kept in sync with [AndroidX ExifInterface](https://developer.android.com/reference/androidx/exifinterface/media/ExifInterface)


*Minor changes include bug fixes as well as additional sanity checks for I/O operations. Major changes were made only to reading metadata from JPEG, PNG or WebP images, where additional metadata (XMP for PNG/WebP, ExtendedXMP/Photoshop for JPEG, ICC profile for JPEG/PNG/WebP) will be recognized.


## Usage
`implementation("io.github.tommy-geenexus:exif-interface-extended:1.0.0")`

## API Examples

**Save the JPEG, PNG or WebP image without metadata**
```
val exifInterfaceExtended = ExifInterfaceExtended(source)
exifInterfaceExtended.saveExclusive(source, sink, preserveOrientation)
```

**Check whether the JPEG, PNG or WebP image has attributes**
```
val exifInterfaceExtended = ExifInterfaceExtended(source)
val hasAttributes = exifInterfaceExtended.hasAttributes(ignoreImageWidthAndLength)
```

**Check whether the JPEG, PNG or WebP image contains XMP metadata**
```
val exifInterfaceExtended = ExifInterfaceExtended(source)
val hasXmp = exifInterfaceExtended.hasXmp()
```

**Check whether the JPEG image contains ExtendedXMP metadata**
```
val exifInterfaceExtended = ExifInterfaceExtended(source)
val hasExtendedXmp = exifInterfaceExtended.hasExtendedXmp()
```

**Check whether the JPEG image contains Photoshop metadata**
```
val exifInterfaceExtended = ExifInterfaceExtended(source)
val hasPhotoshopImageResources = exifInterfaceExtended.hasPhotoshopImageResources()
```

**Check whether the JPEG, PNG or WebP image contains an embedded ICC profile**
```
val exifInterfaceExtended = ExifInterfaceExtended(source)
val hasIccProfile = exifInterfaceExtended.hasIccProfile()
```
