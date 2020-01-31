# WebView practice
Simple website(https://maxsop.com/) convert to android app using webview.

### Fullscreen 
In style.xml file set 'NoActionBar'
```xml
<style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
    ...
</style>
```

In MainActivity.java (remove status bar)
```java
getWindow().setFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN, WindowManager.LayoutParams.FLAG_FULLSCREEN);
```
