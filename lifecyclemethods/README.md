# Ex.No:1 To create a HelloWorld Activity using all lifecycles methods to display messages.


## AIM:

To create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as HelloWorld and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity">
 <TextView
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="Hello World!\nThis is Divya here!!!"
 android:textSize="20dp"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintStart_toStartOf="parent"
 app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>

MainActivity.java

package com.example.myapp1;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 Toast.makeText(this, "onCreate Called", Toast.LENGTH_SHORT).show();
 }
 @Override
 protected void onRestart(){
 Toast.makeText(this, "onRestart Called", Toast.LENGTH_SHORT).show();
 super.onRestart();
 }
 @Override
 protected void onStart(){
 Toast.makeText(this, "onStart Called", Toast.LENGTH_SHORT).show();
 super.onStart();
 }
 @Override
 protected void onResume(){
 Toast.makeText(this, "onResume Called", Toast.LENGTH_SHORT).show();
 super.onResume();
 }
 @Override
 protected void onPause(){
 Toast.makeText(this, "onPause Called", Toast.LENGTH_SHORT).show();
 super.onPause();
 }
 @Override
 protected void onStop(){
 Toast.makeText(this, "onStop Called", Toast.LENGTH_SHORT).show();
 super.onStop();
 }
 @Override
 protected void onDestroy(){
 Toast.makeText(this, "onDestroy Called", Toast.LENGTH_SHORT).show();
 super.onDestroy();
}
}
```

## OUTPUT

![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/8f308746-eea8-4d24-94d4-6590b29d7cf7)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/cf82ad1e-2b3d-405d-97d3-46f230fa18ea)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/0753096f-e6d0-4e36-bef2-37fee5c97c3c)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/aa219bf6-40fe-46e7-95ad-ba79eb5b4b48)



## RESULT
Thus a Simple Android Application create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio is developed and executed successfully.
