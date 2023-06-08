# Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

step1:Create the first activity with a layout that includes an EditText for number input and a
Button for the Factorial action.

step2:Implement an OnClickListener for the Factorial button that retrieves the number from
the EditText, calculates its factorial, and creates an Intent to open the second activity.

step3:Pass the calculated factorial value as an extra data in the Intent.

step4:In the second activity, retrieve the factorial value from the Intent using
getIntent().getIntExtra() method.

step5:Update the layout of the second activity to display the factorial value.

step6:Declare the second activity in the AndroidManifest.xml file.

step7:Build and run the application to test the functionality of both screens.

## PROGRAM:
```
activity_main.xml:

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity"
 android:orientation="vertical"
 android:padding="20dp">
 <EditText android:id="@+id/etNumber"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:hint="@string/Enter_the_number"
 android:inputType="number"
 android:layout_marginTop="50dp"
 android:importantForAutofill="no" />
 <Button
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:text="factorial"
 android:onClick="displayFactorial" />
</LinearLayout>

activity_main2.xml:

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity2"
 android:padding="20dp">
 <TextView android:id="@+id/tv"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 android:text="@string/factorial_of_number_is"
 style="@style/TextAppearance.AppCompat.Large"/>
</RelativeLayout>

MainActivity.java:

package com.example.ieapp;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
public class MainActivity extends AppCompatActivity {
 EditText etNumber;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 etNumber=findViewById(R.id.etNumber);
 }
 public void displayFactorial(View view){
 Intent i = new Intent(MainActivity.this,MainActivity2.class);
 i.putExtra("number",etNumber.getText().toString());
 startActivity(i);
 }
}

MainActivity2.java:

package com.example.ieapp;
import androidx.appcompat.app.AppCompatActivity;
import android.annotation.SuppressLint;
import android.os.Bundle;
import android.widget.TextView;
public class MainActivity2 extends AppCompatActivity {
 TextView tv;
 @SuppressLint("SetTextI18n")
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main2);
 Bundle b=getIntent().getExtras();
 int no= Integer.parseInt(b.getString("number"));
 long f=1;
 for (int i=no;i>0;i--){
 f=f*i;
 }
 tv=findViewById(R.id.tv);
 tv.setText("Factorial of "+no+" is " +f);
 }
}
```

## OUTPUT

![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/b489e070-aee3-492f-bbaf-14f8c717d567)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/e405f980-bf5d-4b5b-be5c-0b58665be6a9)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/46cc5ebc-e86f-4eb4-8004-531ea41489bc)




## RESULT
