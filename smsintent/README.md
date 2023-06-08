
# Ex.No:6 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

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
 android:gravity="center"
 android:background="@color/teal_200">
 <EditText
 android:id="@+id/editText"
 android:layout_width="316dp"
 android:layout_height="48dp"
 android:ems="10"
 android:hint="Name"
 android:inputType="textPersonName"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintHorizontal_bias="0.368"
 app:layout_constraintStart_toStartOf="parent"
 app:layout_constraintTop_toTopOf="parent"
 app:layout_constraintVertical_bias="0.173" />
 <EditText
 android:id="@+id/editText2"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:ems="10"
 android:hint="phoneNo"
 android:inputType="phone"
 android:minHeight="48dp"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintHorizontal_bias="0.434"
 app:layout_constraintStart_toStartOf="parent"
 app:layout_constraintTop_toTopOf="parent"
 app:layout_constraintVertical_bias="0.295" />
 <Button
 android:id="@+id/sendMessage"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="Send"
 android:textSize="30sp"
 android:padding="10dp"/>
</LinearLayout>

MainActivity.java:

package com.example.smsintent;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
public class MainActivity extends AppCompatActivity {
Button sendMessage;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 sendMessage=findViewById(R.id.sendMessage);
 sendMessage.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 Intent intent= new
Intent(Intent.ACTION_VIEW,Uri.fromParts("sms","7695897739",null));
 intent.putExtra("sms_body","Hello");
 startActivity(intent);
 }
 });
 }}
```

## OUTPUT

![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/1b1ceb1b-4489-418a-9c5f-f2196399d4b9)


## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
