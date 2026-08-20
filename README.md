# Ex.No:4 Develop a simple application to display the avaliable sensor in android mobile devices using Sensor Manager in android studio.


## AIM:

To develop a sensor application to use the sensor manager class to identify and get the list of available sensors on a device. in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min.required Giraffe)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as Sensor and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display avaliable sensor in android mobile devices.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the avaliable sensor in android mobile devices”.
Developed by: SOUNDARYA J
Registeration Number : 212223220108
*/
```
### MainActivity.java
```java
package com.example.sensors;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Context;
import android.hardware.Sensor;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.view.View;
import android.widget.TextView;

import java.util.List;

public class MainActivity extends AppCompatActivity {

    private SensorManager mgr;
    private TextView txtList;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        mgr = (SensorManager) getSystemService(Context.SENSOR_SERVICE);

        txtList = findViewById(R.id.sensorlist);

        List<Sensor> sensorList = mgr.getSensorList(Sensor.TYPE_ALL);

        StringBuilder strBuilder = new StringBuilder();

        for (Sensor s : sensorList) {
            strBuilder.append(s.getName()).append("\n");
        }

        txtList.setVisibility(View.VISIBLE);
        txtList.setText(strBuilder.toString());
    }
}
```
### activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="16dp">

        <TextView
            android:id="@+id/title"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Available Sensors"
            android:textSize="22sp"
            android:textStyle="bold"
            android:paddingBottom="10dp"/>

        <TextView
            android:id="@+id/sensorlist"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:textSize="16sp"/>

    </LinearLayout>

</ScrollView>
```
## OUTPUT
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d1a45bc8-3994-450a-8687-9d8fdc80c645" />


## RESULT
Thus a Simple Android Application to display the avaliable sensor in android mobile devices using Sensor Manager in Android Studio is developed and executed successfully.
