## UrlImageViewHelper
UrlImageViewHelper will fill an ImageView with an image that is found at a URL.

### Original Project URL

https://github.com/koush/UrlImageViewHelper

### Changes to original project

#### 1. now there are two parameters to control the bitmap scaling:

```java
    private static boolean mUseZoomIn = true;
    private static boolean mUseZoomOut = true;
```

mUseZoomIn enables a better display result for small images

#### 2. scaled size matches target size better

```
  screen size is 800X1280
  image size is 2048X1536
  original implementation: the scaled size is 512X384
  new implementation: the scaled size is 800X600
```

#### 3. set error drawable for downloading failure

```
    // set error resource, this resource will be used when failed to load image
    UrlImageViewHelper.setErrorResource(R.drawable.failure_night);
```

#### 4. set threshold for max image size to download


```
    // set threshold for max image size
    UrlImageViewHelper.setMaxImageSize(50*1024);
```

#### 5. disable cache to avoid out-of-memory error

see http://androidcocktail.blogspot.in/2012/05/solving-bitmap-size-exceeds-vm-budget.html

