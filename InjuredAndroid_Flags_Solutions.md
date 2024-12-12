Flag 1: Package Listing
Objective:
Find the app package and extract the APK file.

Steps:
Open Powershell or Terminal and run the following commands:

bash

adb shell pm list packages
adb shell pm list packages | Select-String injured
adb shell pm path b3nac.injuredandroid
Extract the APK file:

bash

adb pull /data/app/.../b3nac.injuredandroid-.../base.apk
Once the file is successfully downloaded, you’ve solved Flag 1.

Flag 2: Activity Enumeration
Objective:
Start a specific activity within the InjuredAndroid app.

Steps:
Run the following command in Powershell:
bash

adb shell am start -n b3nac.injuredandroid/b3nac.injuredandroid.b25lActivity
This command launches the required activity, solving Flag 2.

Flag 3: Broadcast Receiver Test
Objective:
Trigger a broadcast receiver to uncover the flag.

Steps:
Run the following command:
bash

adb shell am start -n b3nac.injuredandroid/.TestBroadcastReceiver
This command triggers the broadcast receiver and solves Flag 3.

Flag 4: Decompile APK
Objective:
Decompile the APK file and extract the necessary information.

Steps:
Open the previously downloaded base.apk file using Jadx GUI.
Explore the code structure to locate the flag, often stored as a string in a specific file.
Flag 5: SQL Injection
Objective:
Exploit a SQL Injection vulnerability in the app to retrieve the flag.

Steps:
Locate the SQL Injection test button within the InjuredAndroid app.

Enter the following payload:

sql

' OR '1'='1
