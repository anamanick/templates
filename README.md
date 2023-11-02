<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#Local Dev. Env. Setup">Installation</a></li>
      </ul>
    </li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project
DistroKid now has mobile app for iOS. The purpose of the project is to be able to automate the mobile app iOS as well as Android using open source technology such as WebdriverIO and Appium. There is no alternative to the manual testing, but Automated testing certainly can saves time and effort in great deal. While automation can be run anytime, we can spot critical issue as early as possible by achiving automated testing.

Here's why:
* We can run automation while all CodeceptKids are busy listening cool music.
* Manual effort can be used for edge case, while Automation can run for sanity check
* Distrokids love Automation :smile:

<p align="right">(<a href="#readme-top">back to top</a>)</p>


### Built With

This section should list any major frameworks/libraries used to bootstrap your project. Leave any add-ons/plugins for the acknowledgements section. Here are a few examples.

* WebdriverIO
* Appium
* Mocha
* javascript


<!-- GETTING STARTED -->
## Getting Started
* npm install
```sh
npm install
or
npm install --force
```
* To Run Test

```sh
npx wdio
```

### Prerequisites

Followings are the list of Softwares/Tools will be needed;
* Nodejs
* XCode (for iOS)
* Android Studio (Android, adb, apk analyzer, emulator, ANDROID_HOME) (for android)
* Java (JAVA_HOME)
* Appium 2.0
* Appium Drivers (UIAutomator2(for android), XCUITest(for iOS))
* Appium-Doctor
* Carthage (for iOS only)
* Apple Developers account (for iOS only)

### Local Dev. Env. Setup

In order to setup local environment; 
Download and Install Node js LTS version
- https://nodejs.org/en/download

Install Appium
- npm install -g appium (this should install appium v2 latest version)

Install appium doctor
-npm install -g appium-doctor

Install drivers to run the test; we need UIAutomator2 for Android, XCUITest for ios
-appium driver install uiautomator2
-appium driver install xcuitest

Install Android Studio
Download Install android studio from online
-https://developer.android.com/studio

Once Android Studio is Installed; we need to install following components within Android Studio

Launch Android Studio -> Click on Androidn Studio menu option at the top -> Click Settings -> Under Languages & frameworks click Android SDK
- Click on SDK "Platfrorms" in the Middle Paan
- Turn ON Android API 34 and Android 13.0 Tiramisu
- Click Apply (This should install those two components)

Once Complete Navigate to the next Tab -> SDK Tools

- Turn OFF "Hide Obsolute Packages" from the bottom above cancel button so we can see all packages

Install Following Components from SDK Tools
- Turn ON Android SDK Build-Tools 34
- Turn ON Android SDK Command Line tools (Latest)
- Turn ON Android SDK Tools (Obsolete)
- Turn ON Android SDK Platform-Tools 
- Android Emulator
Click apply button and let it install all these components.

Install Appium Inspector in order to manually Inspect the Application
Download the .dmz if you use mac, and install it. When you launch first time, you may have to allow this software to be launched from privacy and security under settings
-https://github.com/appium/appium-inspector/releases/

Environment Variables for Android SDK/emulator/tools and platform-tools
export ANDROID_HOME=/Users/{your username}/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/platform-tools

Java Setup
here is the documentation will help you download and install jdk
https://docs.oracle.com/en/java/javase/11/install/installation-jdk-macos.html#GUID-2FE451B0-9572-4E38-A1A5-568B77B146DE


Java Home Setup
Now we need to add JAVA_HOME env. variable
Open terminal and hit the following command
```sh
- nano ~/.zshenv
```
Add following lines
```sh
-export JAVA_HOME=$(/usr/libexec/java_home)
```
#Save and Exit; run following command;
```sh
-source ~/.zshenv
```

## Misceleniuous Appium-doctor command
- appium-doctor --android : to see the appium setup for android
- appium-doctor --ios : to see setup for ios

## Capabelities to connectoto a phone from appium inspector i.e. for android
```sh
{
  'appium:platformName': 'Android',
  'appium:platformVersion': '13.0',
  'appium:deviceName': 'Device Name',
  'appium:automationName': 'UiAutomator2',
  'appium:appWaitActivity': '*',
  "appium:autoGrantPermissions": true,
  //'appium:app':'path of you apk file'
  'appium:appPackage' : 'com.distrokid.dk.staging',
  //'appium:appPackage' : 'com.distrokid.dk',
  'appium:appActivity' : 'com.distrokid.dk.MainActivity'
}
```

## Various useful command

-adb devices : To see what device you are connected to (for android only)
-xcrun simctl : To see what simulator is booted in you mac (iOS only)
-npm cache clean --force : to clean npm cache
-npm cache verify : to verify nom cache
-npm ls -g : to see what npm package is installed globally in your system
