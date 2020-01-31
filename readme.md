# WebView practice
Simple website(https://maxsop.com/) convert to android app using webview.

### Enable internet 
In AndroidManifest.xml
```xml
<uses-permission android:name="android.permission.INTERNET"></uses-permission>
```

### Enable javascript 
In MainActivity.java
```java
WebSettings webSettings = webView.getSettings();
webSettings.setJavaScriptEnabled(true);
```

### Set webclint and manage events
In MainActivity.java
```java
webView.setWebViewClient(new WebViewClient());
```

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

Transparent status bar
```java
getWindow().setFlags(WindowManager.LayoutParams.FLAG_LAYOUT_NO_LIMITS, WindowManager.LayoutParams.FLAG_LAYOUT_NO_LIMITS);
```

### Back press
```java
@Override
public void onBackPressed() {
    if(webView.canGoBack()) {
        webView.goBack();
    } else {
        super.onBackPressed();
    }
}
```

### Sleep using Thread
```java
Thread thread = new Thread(new Runnable() {
    @Override
    public void run() {
        try {
            sleep(3000);

            // new intent
            Intent intent = new Intent(SplashScreenActivity.this, MainActivity.class);
            startActivity(intent);

            // kill the current activity
            finish();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
});

// run the thread
thread.start();
```

Thanks.
