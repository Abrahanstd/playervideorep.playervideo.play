## How to use our software to play videos outside of your app.
To use our service in your app, the user needs to have our app installed
https://play.google.com/store/apps/details?id=playervideorep.playervideo.play
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
### Add this to the activity that will open on receiving the result.
```
    <intent-filter>
    <action android:name="android.intent.action.SEND" />
    <category android:name="android.intent.category.DEFAULT" />
    <data android:mimeType="text/plain" />
    </intent-filter>
```
Note: Remember that it has to be the same Activity that you put here
```
    sendIntent.putExtra("Package-classname", "MainActivity");  //////// Class where you will be redirected when receiving the result of your app.
```
### Add this queries in this location of the MANIFEST.
```
 </application>
    <queries>
        <intent>
            <action android:name="android.intent.action.MAIN" />
        </intent>
    </queries>
</manifest>
```
