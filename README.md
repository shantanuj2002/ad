Mpas api:AIzaSyCBlap-jqb0uC3vp7eBrzJn8iiTKJpxtgM

<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
    <uses-permission
        android:name="android.permission.ACCESS_COARSE_LOCATION"/>
    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-feature android:name="android.hardware.location.gps"/>


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <VideoView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/videoview"></VideoView>

</LinearLayout>



import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.widget.MediaController;
import android.widget.VideoView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        VideoView vv=findViewById(R.id.videoview);
        vv.setVideoPath("android.resource://"+getPackageName()+"/"+R.raw.intro);
        vv.start();
        MediaController mediaController=new MediaController(this);
        mediaController.setAnchorView(vv);
        vv.setMediaController(mediaController);
    }
}
