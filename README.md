## How to use our software to play videos outside of your app.
### Insert this code and modify it

```
   String url = "playervideorep.playervideo.play";  //////// Do not touch.
   Intent sendIntent = new Intent();  //////// Do not touch.
   sendIntent.setClassName(url,url + ".MainActivity");  //////// Do not touch.
   sendIntent.setAction(Intent.ACTION_SEND);  //////// Do not touch.
   sendIntent.putExtra("Video-url", selectedItem.getUrl());  //////// Add the ID of the YouTube video you want to play.
   sendIntent.putExtra("Result-Enabled", true);
   sendIntent.putExtra("Result-Return", "xVeryfy");
   sendIntent.putExtra("Package-Return", "com.diamantespro.diamondsfreefire");
   sendIntent.putExtra("Package-classname", "Index");
   sendIntent.setType("text/plain");  //////// Do not touch.
   Intent shareIntent = Intent.createChooser(sendIntent, null);  //////// Do not touch.
   startActivity(shareIntent);  //////// Do not touch.
```
