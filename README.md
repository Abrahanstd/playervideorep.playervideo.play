## How to use our software to play videos outside of your app.



   Intent sendIntent = new Intent();
   sendIntent.setClassName(url,url + ".MainActivity");
   sendIntent.setAction(Intent.ACTION_SEND);
   sendIntent.putExtra("Video-url", selectedItem.getUrl());
   sendIntent.putExtra("Result-Return", "xVeryfy");
   sendIntent.putExtra("Result-Enabled", true);
   sendIntent.putExtra("Package-Return", "com.diamantespro.diamondsfreefire");
   sendIntent.putExtra("Package-classname", "Index");
   sendIntent.setType("text/plain");
   Intent shareIntent = Intent.createChooser(sendIntent, null);
   startActivity(shareIntent);
