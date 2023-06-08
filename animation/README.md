# Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step1: Start the program

Step2: Create a necessary xml files

Step3: Import the necessary packages and libraries.

Step4: Create a class named MainActivity that extends AppCompatActivity.

Step5: Declare ImageView and Button variables for the views in the layout.

Step6: Override the onCreate() method and set the content view to the activity_main layout.

Step7: Initialize the ImageView and Button variables by finding them using their IDs.

Step8: Set click listeners for each button to handle the animation actions.

Step9: Inside the click listeners:

Step9.1: Load the animation from the appropriate XML file using
AnimationUtils.loadAnimation() method.

Step9.2: Start the animation on the ImageView by calling startAnimation() and passing the
animation object.

Step9.3: To stop the animation, call the clearAnimation() method on the ImageView.

Step10: End the click listeners.

Step11: End the onCreate() method.

Step12: End the program

## PROGRAM:
```
activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:tools="http://schemas.android.com/tools"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity">
 <ImageView
 android:id="@+id/imageview"
 android:layout_width="200dp"
 android:layout_height="200dp"
 android:layout_centerHorizontal="true"
 android:layout_marginTop="40dp"
 android:contentDescription="@string/app_name"
 android:src="@drawable/img" />
 <LinearLayout
 android:id="@+id/linear1"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_below="@id/imageview"
 android:layout_marginTop="30dp"
 android:orientation="horizontal"
 android:weightSum="3">
 <Button
 android:id="@+id/BTNblink"
 style="@style/TextAppearance.AppCompat.Widget.Button"
 android:layout_width="0dp"
 android:layout_height="wrap_content"
 android:layout_margin="10dp"
 android:layout_weight="1"
 android:padding="3dp"
 android:text="@string/blink"
 android:textColor="@color/white" />
 <Button
 android:id="@+id/BTNrotate"
 style="@style/TextAppearance.AppCompat.Widget.Button"
 android:layout_width="0dp"
 android:layout_height="wrap_content"
 android:layout_margin="10dp"
 android:layout_weight="1"
 android:padding="3dp"
 android:text="@string/clockwise"
 android:textColor="@color/white" />
 <Button
 android:id="@+id/BTNfade"
 style="@style/TextAppearance.AppCompat.Widget.Button"
 android:layout_width="0dp"
 android:layout_height="wrap_content"
 android:layout_margin="10dp"
 android:layout_weight="1"
 android:padding="3dp"
 android:text="@string/fade"
 android:textColor="@color/white" />
 </LinearLayout>
 <LinearLayout
 android:id="@+id/linear2"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_below="@id/linear1"
 android:layout_marginTop="30dp"
 android:orientation="horizontal"
 android:weightSum="3">
 <Button
 android:id="@+id/BTNmove"
 style="@style/TextAppearance.AppCompat.Widget.Button"
 android:layout_width="0dp"
 android:layout_height="wrap_content"
 android:layout_margin="10dp"
 android:layout_weight="1"
 android:padding="3dp"
 android:text="@string/move"
 android:textColor="@color/white" />
 <Button
 android:id="@+id/BTNslide"
 style="@style/TextAppearance.AppCompat.Widget.Button"
 android:layout_width="0dp"
 android:layout_height="wrap_content"
 android:layout_margin="10dp"
 android:layout_weight="1"
 android:padding="3dp"
 android:text="@string/slide"
 android:textColor="@color/white" />
 <Button
 android:id="@+id/BTNzoom"
 style="@style/TextAppearance.AppCompat.Widget.Button"
 android:layout_width="0dp"
 android:layout_height="wrap_content"
 android:layout_margin="10dp"
 android:layout_weight="1"
 android:padding="3dp"
 android:text="@string/zoom"
 android:textColor="@color/white" />
 </LinearLayout>
 <Button
 android:id="@+id/BTNstop"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_below="@id/linear2"
 android:layout_marginLeft="30dp"
 android:layout_marginTop="30dp"
 android:layout_marginRight="30dp"
 android:text="@string/stop_animation" />
 </RelativeLayout>
 
 blink.xml:
 <?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
 android:layout_width="match_parent"
 android:layout_height="match_parent">
 <alpha android:fromAlpha="0.0"
 android:toAlpha="1.0"
 android:interpolator="@android:anim/accelerate_interpolator"
 android:duration="500"
 android:repeatMode="reverse"
 android:repeatCount="infinite"/>
</set>

fade.xml:
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 android:interpolator="@android:anim/accelerate_interpolator">
 <alpha
 android:duration="1000"
 android:fromAlpha="0"
 android:toAlpha="1" />
 <alpha
 android:duration="1000"
 android:fromAlpha="1"
 android:startOffset="2000"
 android:toAlpha="0" />
</set>

move.xml:
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
 android:interpolator="@android:anim/linear_interpolator"
 android:fillAfter="true">
 <translate
 android:fromXDelta="0%p"
 android:toXDelta="75%p"
 android:duration="700" />
</set>
<set xmlns:android="http://schemas.android.com/apk/res/android"
 >
 <rotate
 android:duration="6000"
 android:fromDegrees="0"
 android:pivotX="50%"
 android:pivotY="50%"
 android:toDegrees="360" />
 <rotate
 android:duration="6000"
 android:fromDegrees="360"
 android:pivotX="50%"
 android:pivotY="50%"
 android:startOffset="5000"
 android:toDegrees="0" />
</set>

slide.xml:
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
 android:fillAfter="true">
 <scale
 android:duration="500"
 android:fromXScale="1.0"
 android:fromYScale="1.0"
 android:interpolator="@android:anim/linear_interpolator"
 android:toXScale="1.0"
 android:toYScale="0.0" />
</set>

rotate.xml:
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
 >
 <rotate
 android:duration="6000"
 android:fromDegrees="0"
 android:pivotX="50%"
 android:pivotY="50%"
 android:toDegrees="360" />
 <rotate
 android:duration="6000"
 android:fromDegrees="360"
 android:pivotX="50%"
 android:pivotY="50%"
 android:startOffset="5000"
 android:toDegrees="0" />
</set>

slide.xml:
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
 android:fillAfter="true">
 <scale
 android:duration="500"
 android:fromXScale="1.0"
 android:fromYScale="1.0"
 android:interpolator="@android:anim/linear_interpolator"
 android:toXScale="1.0"
 android:toYScale="0.0" />
</set>

zoom.xml:
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
 android:fillAfter="true">
 <scale
 android:duration="500"
 android:fromXScale="1.0"
 android:fromYScale="1.0"
 android:interpolator="@android:anim/linear_interpolator"
 android:toXScale="1.0"
 android:toYScale="0.0" />
</set>
 
 MainActivity.java
 
 package com.example.animation;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;
public class MainActivity extends AppCompatActivity {
 ImageView imageView;
 Button blinkBTN, rotateBTN, fadeBTN, moveBTN, slideBTN, zoomBTN, stopBTN;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 imageView = findViewById(R.id.imageview);
 blinkBTN = findViewById(R.id.BTNblink);
 rotateBTN = findViewById(R.id.BTNrotate);
 fadeBTN = findViewById(R.id.BTNfade);
 moveBTN = findViewById(R.id.BTNmove);
 slideBTN = findViewById(R.id.BTNslide);
 zoomBTN = findViewById(R.id.BTNzoom);
 stopBTN = findViewById(R.id.BTNstop);
 blinkBTN.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
R.anim.blink);
 imageView.startAnimation(animation);
 }
 });
 rotateBTN.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
R.anim.rotate);
 imageView.startAnimation(animation);
 }
 });
 fadeBTN.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
R.anim.fade);
 imageView.startAnimation(animation);
 }
 });
 moveBTN.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
R.anim.move);
 imageView.startAnimation(animation);
 }
 });
 slideBTN.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
R.anim.slide);
 imageView.startAnimation(animation);
 }
 });
 zoomBTN.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),
R.anim.zoom);
 imageView.startAnimation(animation);
 }
 });
 stopBTN.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 imageView.clearAnimation();
 }
 });
 }}
 
```

## OUTPUT

![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/489486d5-b38f-4747-96a4-f40690e2b1c8)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/5c8cd218-8500-401d-ada4-4f2bfa33d9c1)




## RESULT
Thus a Simple Android Application develop to add animation to
imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio is
developed and executed successfully.
