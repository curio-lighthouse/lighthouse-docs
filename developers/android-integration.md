---
description: Bring lighthouse to your next Android Project
---

# Android Integration

In just 7 lines of code, you can fully visualize the data from lighthouse.

### Get the library

1. Add the [JitPack](https://jitpack.io/#curio-lighthouse/lighthouse) repository to your root build.gradle at the end of repositories

   ```text
   allprojects {
   		repositories {
   			...
   			maven { url 'https://jitpack.io' }
   		}
   	}
   ```

2. Add the dependency

   ```text
   dependencies {
   	        implementation 'com.github.curio-lighthouse:lighthouse:Tag'
   	}
   ```

{% hint style="warning" %}
Don't forget to change the "Tag" placeholder with the build from JitPack.
{% endhint %}

### Time to use it

1. Create the LiDAR and LidarDisplay Objects

   ```text
   LIDAR myLidar;
   LidarDisplay lidarDisplay;
   ```

2. Pass the Activity to the LidarDisplay Constructor

   ```text
   lidarDisplay = new LidarDisplay(this);
   ```

3. Pass the Activity and LidarDisplay to the LDAR constructor

   ```text
   myLidar = new LIDAR(this, lidarDisplay);
   ```

4. Connect and Start lighthouse

   ```text
   if (myLidar.connectToLIDAR()) {
       myLidar.startLIDAR();
   }
   ```

### Boom! 

Put all together in the MainActivity

```text
public class MainActivity extends Activity {

    // lighthouse device
    LIDAR myLidar;

    // lighthouse view
    LidarDisplay lidarDisplay;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // This is the graphical plotting of the LIDAR data.
        lidarDisplay = new LidarDisplay(this);
        ConstraintLayout linearLayout = findViewById(R.id.constraint_layout);
        linearLayout.addView(lidarDisplay);

        myLidar = new LIDAR(this, lidarDisplay);

        // Connect to lighthouse.
        if (myLidar.connectToLIDAR()) {
            // If the connection was successful, then we will start lighthouse.
            myLidar.startLIDAR();
        }
    }
}
```

 

{% hint style="warning" %}
Don't forget to give your app Bluetooth permissions in the AndroidManifest.xml
{% endhint %}

```text
<uses-permission android:name="android.permission.BLUETOOTH" />
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
```

{% hint style="info" %}
A video walkthrough of the above process is available [**here**](https://www.youtube.com/watch?v=Ep4xlEgZQuU)\*\*\*\*
{% endhint %}



