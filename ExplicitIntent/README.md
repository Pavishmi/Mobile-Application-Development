# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step 1:Create the first activity with a layout that includes an EditText for number input and a 
Button for the Factorial action.

Step 2:Implement an OnClickListener for the Factorial button that retrieves the number from 
the EditText, calculates its factorial, and creates an Intent to open the second activity.

Step 3:Pass the calculated factorial value as an extra data in the Intent.

Step 4:In the second activity, retrieve the factorial value from the Intent using 
getIntent().getIntExtra() method.

Step 5:Update the layout of the second activity to display the factorial value.

Step 6:Declare the second activity in the AndroidManifest.xml file.

Step 7:Build and run the application to test the functionality of both screens.

## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by: Pavishmi S R
Registeration Number : 212221040118
*/
```
### activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical"
    android:padding="20dp">
    <EditText android:id="@+id/etNumber"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="enter_the_number"
        android:inputType="number"
        android:layout_marginTop="50dp"
        android:importantForAutofill="no" />
    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="factorial"
        android:onClick="displayFactorial"/>
</LinearLayout>
```
### MainActivity.java
```
package com.example.exintent;

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
        Intent i=new Intent(MainActivity.this,MainActivity2.class);
        i.putExtra("number",etNumber.getText().toString());
        startActivity(i);
    }
}
```
### activity_main2.xml
```
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
        android:text="Factorial of number is"
        style="@style/TextAppearance.AppCompat.Large"/>
</RelativeLayout>
```
### MainActivity2.java
```
package com.example.exintent;

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
        int no=Integer.parseInt(b.getString("number"));
        long f=1;
        for(int i=no;i>0;i--)
        {
            f=f*i;
        }
        tv=findViewById(R.id.tv);
        tv.setText("Factorial of "+no+" is "+f);
    }
}
```
## OUTPUT

![image](https://github.com/Pavishmi/Mobile-Application-Development/assets/136091280/ac8a09bb-19e4-4fae-8344-96c76d0b2625)

![image](https://github.com/Pavishmi/Mobile-Application-Development/assets/136091280/db188577-ba1e-44cd-82cb-4212edc13969)

## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.


