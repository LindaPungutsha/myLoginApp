# myLoginApp<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:background="@drawable/back"
    android:layout_height="match_parent"


       tools:context=".MainActivity">

<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:id="@+id/signIn"
    android:text="Sign in"
    android:textColor="@color/white"
    android:textSize="35dp"
    android:textStyle="bold"
    android:layout_margin="50dp"
    android:gravity="center"
    />

    <EditText
        android:id="@+id/username"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/signIn"
        android:layout_margin="10dp"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_marginEnd="10dp"
        android:layout_marginBottom="10dp"
        android:background="#30ffffff"
        android:hint="Username"
        android:padding="20dp"
        android:drawableLeft="@drawable/ic_baseline_person_pin_24"
        android:drawablePadding="20dp"
        android:textColor="@color/white"
        android:textColorHint="@color/white" />

    <EditText
        android:id="@+id/password"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/username"
        android:layout_margin="10dp"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_marginEnd="10dp"
        android:layout_marginBottom="10dp"
        android:background="#30ffffff"
        android:hint="password"
        android:padding="20dp"
        android:drawableLeft="@drawable/ic_baseline_info_24"
        android:drawablePadding="20dp"
        android:textColor="@color/white"
        android:textColorHint="@color/white"
        android:inputType="textPassword"/>


    <com.google.android.material.button.MaterialButton
        android:id="@+id/loginbtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/password"
         android:text="LOGIN"
        android:backgroundTint="@color/material_dynamic_secondary30"
        android:layout_centerHorizontal="true"
        android:layout_margin="20dp"
        />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/forgetpass"
        android:layout_below="@id/loginbtn"
        android:text="forgot password?"
        android:textColor="@color/white"
        android:layout_centerHorizontal="true"
        android:layout_margin="20dp"
        />
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/others"
        android:layout_above="@id/socialicons"

        android:text="or sign in with"
        android:layout_centerHorizontal="true"/>

    <LinearLayout

        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/socialicons"
        android:layout_alignParentBottom="true"
        android:gravity="center">

        <ImageView
            android:layout_width="48dp"
            android:layout_height="48dp"
            android:src="@drawable/fa"
            android:layout_margin="20dp"

            />
        <ImageView
            android:layout_width="48dp"
            android:layout_height="48dp"
            android:src="@drawable/twitter"

            />
    </LinearLayout>







</RelativeLayout>



package com.example.myloginapp;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

import com.google.android.material.button.MaterialButton;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        TextView username = (TextView) findViewById(R.id.username);
        TextView password = (TextView) findViewById(R.id.password);

        MaterialButton loginbtn = (MaterialButton) findViewById(R.id.loginbtn);

        loginbtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if (username.getText().toString().equals("admin") && password.getText().toString().equals("admin")) {
                    Toast.makeText(MainActivity.this,"Login Successful", Toast.LENGTH_SHORT).show();
                }else{

                   Toast.makeText(MainActivity.this, "Login failed !! ", Toast.LENGTH_SHORT).show();
                }
            }
        });
    }
}


