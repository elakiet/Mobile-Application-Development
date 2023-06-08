# Ex.No:10 To create a option menu to display menu items.


## AIM:

To create a option menu to display menu items using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step1: Start the program

Step2: Create a new Android project in Android Studio or open an existing project.

Step3: Open the XML layout file for the activity where you want to display the options menu
(usually named activity_main.xml).

Step4: Add a Toolbar widget to the layout file to act as the action bar for the activity.

Step5: In the Java file for the activity (usually named MainActivity.java):

Step6: Override the onCreateOptionsMenu() method to inflate the menu resource file and
display the options menu.

Step7: Implement the onOptionsItemSelected() method to handle the selected menu item's
actions.

Step8: Create an XML file in the res/menu directory to define the menu items.

Step9: Specify the menu items in the XML file, including their IDs, titles, and other
attributes.

Step10: Handle the selected menu item's actions in the onOptionsItemSelected() method
based on its ID.

Step11: Customize the menu items and their behavior as per your requirements.

Step12: Run the Android application to see the options menu displayed in the activity's action
bar.

Step13: Implement the desired actions for each menu item by adding the necessary code
within the onOptionsItemSelected() method.

Step14: End the program

## PROGRAM:
```
my_menu.xml:

<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 tools:context=".MainActivity">
 <item
 android:id="@+id/message"
 android:icon="@android:drawable/ic_menu_send"
 android:title="message"
 app:showAsAction="always" />
 <item
 android:id="@+id/picture"
 android:icon="@android:drawable/ic_menu_gallery"
 android:title="picture"
 app:showAsAction="always|withText" />
 <item
 android:id="@+id/mode"
 android:icon="@android:drawable/ic_menu_call"
 android:title="mode"
 app:showAsAction="always" />
 <item
 android:id="@+id/about"
 android:icon="@android:drawable/ic_dialog_info"
 android:title="calculator"
 app:showAsAction="never|withText" />
 <item
 android:id="@+id/exit"
 android:title="exit"
 app:showAsAction="never" />
</menu>

MainActivity.java:

package com.example.optionmenu_42;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuItem;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
 private Intent i2;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 }
 public boolean onCreateOptionsMenu(Menu menu) {
 getMenuInflater().inflate(R.menu.my_menu, menu);
 return true;
 }
 public boolean onOptionsItemSelected(MenuItem item) {
 switch (item.getItemId()) {
 case R.id.message:
 Toast.makeText(getApplicationContext(), "Shows share icon",
Toast.LENGTH_SHORT).show();
 return true;
 case R.id.picture:
 Toast.makeText(getApplicationContext(), "Shows image icon",
Toast.LENGTH_SHORT).show();
 startActivity(i2);
 return (true);
 case R.id.mode:
 Toast.makeText(getApplicationContext(), "Shows call icon",
Toast.LENGTH_SHORT).show();
 return (true);
 case R.id.about:
 Toast.makeText(getApplicationContext(), "calculator menu",
Toast.LENGTH_SHORT).show();
 return (true);
 case R.id.exit:
 finish();
 return (true);}
 return (super.onOptionsItemSelected(item)); }}
```

## OUTPUT

![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/7b933d39-df75-491b-8fbd-78c54c0a54ca)
![image](https://github.com/elakiet/Mobile-Application-Development/assets/133135881/9a0e0d1a-992c-4349-b427-eae189ca467a)



## RESULT
Thus a Simple Android Application to create a option menu to display menu items using Android Studio is developed and executed successfully.


