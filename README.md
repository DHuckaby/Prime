Prime
=

Prime is an all-in-one image management solution. One of the major hurdles for developers is to correctly implement an remote image retrieval system, Prime handles all of it for you. Using our simple and powerful apis you can retrieve images painlessly and fluidly in all development scenarios.

Prime is available as a JAR file from the downloads area of this GitHub repo.

All examples can be found on [Google Play][3].

![Examples][2]

Usage
=

The most fool-proof method of integration is to use [RemoteImageView.setImageURL(String)][4].

    String imageURL = "http://example.com/image";
    RemoteImageView remoteImageView = (RemoteImageView) findViewById(R.id.icon);
    remoteImageView.setImageURL(imageURL);
 
If you want to receive images asynchronously without the use of the RemoteImageView wrapper you can easily get images by using [ImageManager.get(String, OnImageReceivedListener)][5] or [ImageManager.get(Request)][6].

    final String imageURL = "http://example.com/image";
    ImageManager imageManager = ImageManager.getInstance(context);
    imageManager.get(imageURL, new OnImageReceivedListener() {

        @Override
        public void onImageReceived(String source, Bitmap bitmap) {
            // Do something with the retrieved Bitmap
        }
    }
 
    imageManager.get(new Request() {
 
        @Override
        public String getSource() {
            return imageURL;
        }
 
        @Override
        public void onImageReceived(String source, Bitmap bitmap) {
            // Do something with the retrieved Bitmap
        }
    });
 
If you want to retrieve images synchronously you can use [ImageManager.get(String)][7].

    ImageManager imageManager = ImageManager.getInstance(context);
    String imageURL = "http://example.com/image";
    Bitmap bitmap = imageManager.get(imageURL);

Documentation
=

* [JavaDoc][1]

Developed By
=

* Daniel Huckaby - <handlerexploit@gmail.com>

License
=

    Copyright (C) 2012 Daniel Huckaby

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

[1]: http://dhuckaby.github.com/Prime/
[2]: http://dhuckaby.github.com/Prime/images/featured.jpg
[3]: https://play.google.com/store/apps/details?id=com.handlerexploit.prime.example
[4]: http://dhuckaby.github.com/Prime/com/handlerexploit/prime/widgets/RemoteImageView.html#setImageURL(java.lang.String)
[5]: http://dhuckaby.github.com/Prime/com/handlerexploit/prime/utils/ImageManager.html#get(java.lang.String,%20com.handlerexploit.prime.utils.ImageManager.OnImageReceivedListener)
[6]: http://dhuckaby.github.com/Prime/com/handlerexploit/prime/utils/ImageManager.html#get(com.handlerexploit.prime.utils.ImageManager.Request)
[7]: http://dhuckaby.github.com/Prime/com/handlerexploit/prime/utils/ImageManager.html#get(java.lang.String)