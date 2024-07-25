# Instructions

1. Install Magisk delta on your emulator (enable root in the settings of course).
2. Choose the "Direct Install (modify /system directly)" option (DON'T REBOOT).
3. Mount the system as read and write (If you know how, skip the following sub-steps).
    1. Go to android settings > About Phone > Build Number, Press on Build number around 5 times (it'll tell you how many times to press).
    2. Go to android settings > System > Developer Options and make sure USB debugging is enabled.
    3. Go to your Computer's cmd and change directory into the nox installation directory (```cd "C:\Program Files (x86)\Nox\bin"``` by default).
    4. Make sure the device is connected using ```nox_adb.exe connect 127.0.0.1:62001```.
    5. Open adb shell using ```nox_adb.exe shell``` and run ```mount -o rw,remount /system``` (if it requires supersuser permission, use ```su``` first then mount).
4. Make a new folder in the root directory called ```sbin``` (Can be done in shell using ```mkdir sbin```).
5. Delete the original ```bootanim.rc``` in ```/system/etc/init``` and replace it with the one provided.
6. Restart your device.

# Tips

- You can delete the original ```bootanim.rc``` using adb shell. After step 3.5. run ```rm -r bootanim.rc```.
- To copy ```bootanim.rc``` or any file from your pc into the emulator, you can use the ```push``` command. Example: ```nox_adb.exe push C:\Path\to\bootanim.rc /system/etc/init```.
