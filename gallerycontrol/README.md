# Ex.No:8 To create a gallery control using android studio to display images or photos.


## AIM:

To create a gallery control using android studio to display images or photos.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step1:Create a new Android Studio project.

Step2:Open the layout file "activity_main.xml".

Step3:Add a container layout to hold the gallery images (e.g., GridLayout, RecyclerView, or
ViewPager).

Step4:Within the container layout, add ImageView elements to display the images. You can
set the image source using the android:src attribute or programmatically in the code.

Step5:If using a GridLayout, specify the number of columns using the android:columnCount
attribute.

Step6:Customize the layout and appearance of the ImageView elements as desired.

Step7:Add any necessary attributes or listeners to handle user interactions, such as clicks on
the images.

Step8:Optionally, create a data source to store the images (e.g., a list or an array of image
references).

Step9:Bind the data source to the gallery control to populate the images dynamically.

Step10:Implement any additional functionality, such as zooming, sliding, or image
transitions, if desired.

Step11:Build and run the application to see the gallery control displaying the images.

## PROGRAM:
```
activity_main.xml:

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity"
 android:orientation="vertical">
 <ImageView
 android:id="@+id/imageView"
 android:layout_width="fill_parent"
 android:layout_height="288dp"
 android:scaleType="fitXY" />
 <Gallery
 android:id="@+id/languagesGallery"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_marginTop="100dp"
 android:animationDuration="2000"
 android:padding="10dp"
 android:spacing="5dp"
 android:unselectedAlpha="50" />
</LinearLayout>

MainActivity.java:

package com.example.galary;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.Gallery;
import android.os.Bundle;
import android.widget.Gallery;
import android.widget.ImageView;
public class MainActivity extends AppCompatActivity {
 Gallery simpleGallery;
 CustomizedGalleryAdapter customGalleryAdapter;
 ImageView selectedImageView;
 int[] images = {
 R.drawable.img, R.drawable.img_1,R.drawable.img_7,
R.drawable.img_2,R.drawable.img_8,
 R.drawable.img_3, R.drawable.img_4, R.drawable.img_5, R.drawable.img_6,
R.drawable.img_3,
 R.drawable.img_4, R.drawable.img, R.drawable.img_1,R.drawable.img_7,
R.drawable.img_2, R.drawable.img_5,};
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 simpleGallery = (Gallery) findViewById(R.id.languagesGallery);
 selectedImageView = (ImageView) findViewById(R.id.imageView);
 customGalleryAdapter = new CustomizedGalleryAdapter(getApplicationContext(),
images);
 simpleGallery.setAdapter(customGalleryAdapter);
 simpleGallery.setOnItemClickListener((parent, view, position, id) -> {
 selectedImageView.setImageResource(images[position]);
 });
 }
}
```

## OUTPUT
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/be661e7f-4992-4676-af3c-f0b9aed7acb3)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/2e52a1a4-05d6-46da-830b-c0b640cef8d7)




## RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.


