# Ex.No:9 Develop a simple calculator using android studio.

## AIM:

To develop a program to develop a simple calculator in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as calculator and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout using UI components in activity_main.xml.

Step 6: Display the calculator operation in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
activity_main:

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
 android:layout_width="match_parent"
 android:layout_height="111dp"
 android:layout_marginTop="25dp"
 app:srcCompat="@drawable/img" />
 <EditText
 android:id="@+id/txt1"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_marginLeft="20dp"
 android:layout_marginTop="20dp"
 android:layout_marginRight="20dp"
 android:ems="10"
 android:hint="First Number"
 android:inputType="numberDecimal"
 tools:ignore="TouchTargetSizeCheck,SpeakableTextPresentCheck" />
 <EditText
 android:id="@+id/txt2"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_marginLeft="20dp"
 android:layout_marginTop="20dp"
 android:layout_marginRight="20dp"
 android:ems="10"
 android:hint="Second Number"
 android:inputType="numberDecimal"
 tools:ignore="SpeakableTextPresentCheck,TouchTargetSizeCheck" />
 <Button
 android:id="@+id/btnadd"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_marginLeft="20dp"
 android:layout_marginTop="20dp"
 android:layout_marginRight="20dp"
 android:text="Add" />
 <Button
 android:id="@+id/btnsubs"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_marginLeft="20dp"
 android:layout_marginTop="20dp"
 android:layout_marginRight="20dp"
 android:text="Subtract" />
 <Button
 android:id="@+id/btndiv"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_marginLeft="20dp"
 android:layout_marginTop="20dp"
 android:layout_marginRight="20dp"
 android:text="Divide" />
 <Button
 android:id="@+id/btnmult"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_marginLeft="20dp"
 android:layout_marginTop="20dp"
 android:layout_marginRight="20dp"
 android:text="Multiply" />
 <TextView
 android:id="@+id/result"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_marginLeft="20dp"
 android:layout_marginTop="25dp"
 android:layout_marginRight="20dp" />
</LinearLayout>

MainActivity.java:

package com.example.calc42;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
 Button btnadd,btnsubs,btnmult,btndiv;
 EditText txt1,txt2;
 TextView result;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 btnadd=findViewById(R.id.btnadd);
 btnsubs=findViewById(R.id.btnsubs);
 btndiv=findViewById(R.id.btndiv);
 btnmult=findViewById(R.id.btnmult);
 txt1=findViewById(R.id.txt1);
 txt2=findViewById(R.id.txt2);
 result=findViewById(R.id.result);
 btnadd.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View view) {
 if (txt1.getText().toString().equals("")) {
 Toast.makeText(MainActivity.this, "Please Enter Number",
Toast.LENGTH_SHORT).show();
 } else if (txt2.getText().toString().equals("")) {
 Toast.makeText(MainActivity.this, "Please Enter Number",
Toast.LENGTH_SHORT).show();
 }
 else {
 float a, b, c;
 a = Float.parseFloat(txt1.getText().toString());
 b = Float.parseFloat(txt2.getText().toString());
 c = a + b; // Using Third Variable To Store Output Value
 result.setText("The Addition Result Is " + c);
 }
 }
 });
 btnsubs.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View view) {
 if (txt1.getText().toString().equals("")) {
 Toast.makeText(MainActivity.this, "Please Enter Number",
Toast.LENGTH_SHORT).show();
 } else if (txt2.getText().toString().equals("")) {
 Toast.makeText(MainActivity.this, "Please Enter Number",
Toast.LENGTH_SHORT).show();
 }
 else {
 float a, b, c;
 a = Float.parseFloat(txt1.getText().toString());
 b = Float.parseFloat(txt2.getText().toString());
 c = a - b; // Using Third Variable To Store Output Value
 result.setText("The Subtraction Result Is " + c);
 }
 }
 });
 btnmult.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View view) {
 if (txt1.getText().toString().equals("")) {
Toast.makeText(MainActivity.this, "Please Enter Number",
Toast.LENGTH_SHORT).show();
 } else if (txt2.getText().toString().equals("")) {
 Toast.makeText(MainActivity.this, "Please Enter Number",
Toast.LENGTH_SHORT).show();
 }
 else {
 float a, b, c;
 a = Float.parseFloat(txt1.getText().toString());
 b = Float.parseFloat(txt2.getText().toString());
 c = a*b; // Using Third Variable To Store Output Value
 result.setText("The Multiplication Result Is " + c);
 }
 }
 });
 btndiv.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View view) {
 // Checking Input First Is Blank Or Not
 if (txt1.getText().toString().equals("")) {
 // Showing Toast (Message)
 Toast.makeText(MainActivity.this, "Please Enter Number",
Toast.LENGTH_SHORT).show();
 } else if (txt2.getText().toString().equals("")) {
 Toast.makeText(MainActivity.this, "Please Enter Number",
Toast.LENGTH_SHORT).show();
 }
 else {
 float a, b, c;
 a = Float.parseFloat(txt1.getText().toString());
 b = Float.parseFloat(txt2.getText().toString());
 c = a/b; // Using Third Variable To Store Output Value
 result.setText("The Division Result Is " + c);
 }
 }
 });
 }
}
```

## OUTPUT

![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/8090211c-23e2-49a3-b6d4-e52edba64427)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/7b2455a9-1bbd-48be-a96a-38f7d7984d26)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/0d8f835e-22dd-4127-838f-b4e61eb1ebd7)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/fa2409ef-b754-45bf-bfd0-49cd56f702f5)



## RESULT
Thus a Simple Android Application develop a program to create simple calculator in Android Studio is developed and executed successfully.
