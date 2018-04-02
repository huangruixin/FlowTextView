FlowTextView
============

A wrapping TextView for Android

I originally uploaded this project on [Google code][3] over 2 years ago but I left it to rot and never maintained it so I decided to 'hub it and start refactoring it. Pull requests welcome!

![Logo](http://i.imgur.com/iyntFbz.png)


A TextView that extends RelativeLayout. The text will wrap around any child views inside the layout.

This widget has basic support for HTML using Html.fromHtml("< your markup ... />") It will recognise links, bold italic etc. 

How to use
--------

Add to your XML layout with your child views inside it:

```xml
<uk.co.deanwild.flowtextview.FlowTextView
	android:id="@+id/ftv"
	android:layout_width="fill_parent"
	android:layout_height="wrap_content" >

		<ImageView
			android:layout_width="wrap_content"
			android:layout_height="wrap_content"
			android:layout_alignParentLeft="true"
			android:layout_alignParentTop="true"
			android:padding="10dip"
			android:src="@drawable/android"/>

		<ImageView
			android:layout_width="wrap_content"
			android:layout_height="wrap_content"
			android:layout_alignParentRight="true"
			android:layout_marginTop="400dip"
			android:padding="10dip"
			android:src="@drawable/android2"/>
</uk.co.deanwild.flowtextview.FlowTextView>
```

Then in your code:
```java
		FlowTextView flowTextView = (FlowTextView) findViewById(R.id.ftv);
        Spanned html = Html.fromHtml("<html>Your html goes here....");
        flowTextView.setText(html);
```

Gradle
--------

Add jitpack to your your build.gradle at the end of repositories:

```groovy
repositories {
	    // ...
	    maven { url "https://jitpack.io" }
	}
```

Add the dependency:

```groovy
compile 'com.github.deano2390:FlowTextView:2.0.5'
```


License
-------

    Copyright 2014 Dean Wild

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


History
-------

A text wrap around images and other views are required in an Android APP, however, there is no way to achieve them by native programming.  Using WebViews is the only practical way to achieve the goal. The direct control and performance are closed because WebViews is a bit bloaty and overkilled. The native widget is used to extend RelativeLayout which is capable of painting text around its child views. The code is rough and the author suspects vast improvement in many areas.
	
TODO
--------

 - Add support for parameters to be supplied directly in XML layout.
 
 - Improve HTML support. For now it can handle basic tags like bold, italic, break and a href but it would be nice to support everything
 
 - Add support for Right to Left text printing.
 
 - Performance - this can always be improved. The larger the text content the slower this beast gets at the moment. Perhaps ART might do the trick though


[1]: https://oss.sonatype.org/content/repositories/releases/uk/co/deanwild/flowtextview/2.0.2/flowtextview-2.0.2.aar
[2]: https://github.com/deano2390/FlowTextView/releases/download/v2.0.2/flowtextview-2.0.2.jar
[3]: https://code.google.com/p/android-flowtextview/
