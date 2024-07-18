# nine-patch
strech a png like nine patch 

# 适用场景

左右 是药丸形状的图片，高度 拉伸或者压缩，导致左右圆角变形

# 只拉伸中间部分

先 维持 原图宽高比，缩放到 目标 高度，然后取 中间的 centerX，一个像素，左右扩大，直到宽度 = 目标宽度

```kotlin
data class Size(width, height, ratio = width/height)

val bitmap
val bitmapSize // size from bitmap


val targetBitmap
val targetSize //

# scale to target height, with same aspect ratio
val scale = targetSize.height / bitmapSize.height
val scaleBitmap = bitmap.scaleTo(scale)

// stretch to target width, fill with centerX of bitmap
val center = scaleBitmp[centerX] * (target.width - scaleBitmap.width)

val left = scaleBitmap.leftHaft
val right = scaleBitmap.rightHaft

// concat to new bitmap
val resultBitmap = left + center + right

```
