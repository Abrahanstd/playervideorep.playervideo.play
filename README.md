## How to use our software to play videos outside of your app.
### Insert this code and modify it

```
   String url = "playervideorep.playervideo.play";  //////// Do not touch.
   Intent sendIntent = new Intent();  //////// Do not touch.
   sendIntent.setClassName(url,url + ".MainActivity");  //////// Do not touch.
   sendIntent.setAction(Intent.ACTION_SEND);  //////// Do not touch.
   sendIntent.putExtra("Video-url", selectedItem.getUrl());  //////// Add the ID of the YouTube video you want to play.
   sendIntent.putExtra("Result-Enabled", true);  //////// True if you want that at the end of the video it returns you to validate that the video is over.
   sendIntent.putExtra("Result-Return", "result");  //////// String that will be returned at the end of the video.
   sendIntent.putExtra("Package-Return", "com.example.example");  //////// Here add your package.
   sendIntent.putExtra("Package-classname", "MainActivity");  //////// Class where you will be redirected when receiving the result of your app.
   sendIntent.setType("text/plain");  //////// Do not touch. 
   Intent shareIntent = Intent.createChooser(sendIntent, null);  //////// Do not touch.
   startActivity(shareIntent);  //////// Do not touch.
```


## If you want to receive a result at the end of the video add this in your MANIFEST.
### Add this permission
```
    <uses-permission android:name="android.permission.QUERY_ALL_PACKAGES"/>
```
