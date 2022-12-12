# paho.mqtt.android
Paho Mqtt Android package for sdk version 31 or above.

### Issue made
paho.mqtt.android package from eclipse currently has issue at sdk version upper than 31. <br>
This is because, PendingIntent class from Android has been changed according to: <br>
https://developer.android.com/about/versions/12/behavior-changes-12#pending-intent-mutability <ar>

### Current status
The error is still opened as: https://github.com/eclipse/paho.mqtt.android/issues/485,
so if you want to retrieve any .jar from the package, refer followings.

- Reference is here: https://github.com/eclipse/paho.mqtt.android/issues/485#issue-1384943553 <br>
- I've modified more build configurations to build package rather than copying whole codes.

# How to build
## Build from source before use
### 1. Clone following repositories at the same path
- https://github.com/doorooful/paho.mqtt.android
- https://github.com/eclipse/paho.mqtt.java

### 2. Move to paho.mqtt.android directory from terminal

### 3. Run following script from terminal:
- windows: `.\gradlew.bat clean org.eclipse.paho.android.service:assemble org.eclipse.paho.android.service:publish`

### 4. Find .jar file from build output directory:
- Location: `~/paho.mqtt.android/org.eclipse.paho.android.service/build/libs/`
- File: `org.eclipse.paho.android.service-1.1.1.jar`
(.aar outputs are under `~/paho.mqtt.android/org.eclipse.paho.android.service/build/outputs/aar`)

# How to apply from Android Studio
### 1. add .jar file upder the app/lib from project view
### 2. add implementation files dependencies:
```
dependencies {
    ...
    implementation files('lib/org.eclipse.paho.client.mqttv3-1.2.5.jar')
    implementation files('lib/org.eclipse.paho.android.service-1.1.1.jar')
    ...
}
```
### 3. Finally, you can change sdk version! -> 31 or above!
