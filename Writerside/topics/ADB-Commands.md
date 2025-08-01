# ADB Commands

## Command to kill an app using the app name

adb shell kill `adb shell pgrep kitchensink`

## Command to open an app's Permission management screen

`adb shell am start -a "android.intent.action.MANAGE_APP_PERMISSIONS" --es "android.intent.extra.PACKAGE_NAME" "package name"`

## Command to kill an running app

`adb shell am force-stop com.android.car.settings`

## Command to Start an app using its package name from ADB

`adb shell am start -n com.android.car.settings/com.android.car.settings.Settings_Launcher_Homepage`

## Command to uninstall an app using its package name from ADB

`adb uninstall com.android.car.settings`

## Command to disable a app using ADB

`adb shell pm disable --user 0 com.android.car.settings`

## Command to enable a app using ADB

`adb shell pm enable --user 10 com.android.car.settings`

## Command to force push or downgrade the version of an app in android from ADB

`adb install -r -d com.android.car.settings`

## Command to find the recently opened activities inside an android emulator from ADB

`adb shell dumpsys window windows | grep 'mActivityRecord'`

## Command to record screen from ADB

`adb emu screenrecord start <path to save the file>`

## Command to save a screenshot of an emulator screen from ADB

`adb emu screenshot <path to save the file>`

## Command to record logs from ADB

`adb logcat > file_name.txt`

## Command to restart an emulator from ADB

`adb reboot`

## Command to list apps which are system apps from ADB

`adb shell pm list packages -s`

## Command to list out packages or apps which are disabled

`adb shell pm list packages -d`

## Command to switch from user 10 to user 0 through ADB

`adb shell am switch-user 0`

## Command to know current user through ADB

`adb shell am get-current-user`

## Command to switch from user 0 to user 10 through ADB

`adb shell am switch-user 10`

## Command to list out number of android devices connected to local system through ADB

`adb devices`

## ADB Command to start an app based on package name if activity name is not available

`adb shell monkey -p com.android.calendar 1`

## ADB Command to list out number of apps which are used to overlay target apks with RRO process

`adb shell cmd overlay list --user current`

## Dumpsys Commands

## ADB command to get list of all protected broadcasts

`adb shell dumpsys package protected-broadcasts`

## ADB command to know the Android OS of current running device

`adb shell getprop ro.build.version.release`
https://stackoverflow.com/questions/29968096/get-android-os-version-of-device-connected-via-adb

## ADB command to know the current version of a specific app

`adb shell dumpsys package | 
awk '/^[ ]*Package \[.*\] (.*)/ { i = index($0, "[") + 1; pkg = substr($0, i, index($0, "]") - i); printf "\n%s", pkg; } /[ ]*versionName=/ { { printf "\t%s", $0; } }  /[ ]*versionCode=/ { { printf  "\t%s", $0; } } ' | 
grep packageName`
https://stackoverflow.com/questions/11942762/get-application-version-name-using-adb

## ADB command to get the list of packages from running emulator

`pm list packages [-f] [-d] [-e] [-s] [-3] [-i] [-u]`
`-f: see their associated file.
 -d: filter to only show disbled packages.
 -e: filter to only show enabled packages.
 -s: filter to only show system packages.
 -3: filter to only show third party packages.
 -i: see the installer for the packages.
 -u: also include uninstalled packages.`
`https://stackoverflow.com/questions/8784505/how-do-i-check-if-an-app-is-a-non-system-app-in-android`



## ADB command to kill the current running Activity 
`adb shell input keyevent 4`
https://stackoverflow.com/questions/52293687/can-i-call-finish-of-an-activity-through-adb-shell-command

## ADB command to check which is the root activity for a specific app in android

`adb shell dumpsys activity activities | grep com.android.car.settings | grep Hist`
`adb shell dumpsys activity activities | grep Hist`
https://stackoverflow.com/questions/2442713/view-the-tasks-activity-stack 

## ADB commands to get dumpsys details related to android components
`adb shell dumpsys activity`
`dumpsys activity allowed-associations`
`dumpsys activity intents`
`dumpsys activity broadcasts`
`dumpsys activity providers`
`dumpsys activity permissions`
`dumpsys activity services`
`dumpsys activity recents`
`dumpsys activity lastanr`
`dumpsys activity starter`
`dumpsys activity containers`
`dumpsys activity activities`
`dumpsys activity users`


## ADB command to pull an apk from non-rooted device 
`adb shell pm list packages`
`adb shell pm path packagename`
`adb pull path-from-above-command`

https://gist.github.com/ctrl-freak/24ac0e61b7cf550a6945 

## ADB command to enable layout bounds in a emulator
`adb shell setprop debug.layout true`
`adb shell service call activity 1599295570`

## ADB command to open the language screen in settings app
`adb shell am start -a android.settings.LOCALE_SETTINGS`









