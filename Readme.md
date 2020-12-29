# **Android Interview Questions**



## **What is the Android Architecture?**

Android Architecture is made up of 4 key components:

- Linux Kernel
- Libraries
- Android Framework
- Android Applications

## **What is AAPT?**

AAPT is short for **Android Asset Packaging Tool**. This tool provides developers with the ability to deal with zip-compatible archives, which includes creating, extracting as well as viewing its contents.

## **What items are important in every Android project?**

These are the essential items that are present each time an Android project is created:

- AndroidManifest.xml
- build.xml
- bin/
- src/
- res/
- assets/

## **What is adb?**

Adb is short for **Android Debug Bridge**. It allows developers the power to execute remote shell commands. Its basic function is to allow and control communication towards and from the emulator port.

## **What is ANR?**

ANR is short for **Application Not Responding**. This is actually a dialog that appears to the user whenever an application have been unresponsive for a long period of time.

## **When does ANR occur?**

The ANR dialog is displayed to the user based on **two possible conditions.** One is when there is **no response to an input event within 5 seconds**, and the other is when a **broadcast receiver is not done executing within 10 seconds.**

##  **What is a Fragment?**

A fragment is a part or portion of an activity. It is modular in a sense that you can move around or combine with other fragments in a single activity. Fragments are also reusable.

## **Is it possible to use or add a fragment without using a user interface?**

Yes, it is possible to do that, such as when you want to create a background behavior for a particular activity. You can do this by using add(Fragment,string) method to add a fragment from the activity.

## **Tell all the Android application components.**

App components are the essential building blocks of an Android app. Each component is an entry point through which the system or a user can enter your app. Some components depend on others.

There are four different types of app components:

- Activities
- Services
- Broadcast receivers
- Content providers

Each type serves a distinct purpose and has a distinct lifecycle that defines how the component is created and destroyed. The following sections describe the four types of app components.



## **What is `Context`? How is it used?**

The Context in Android is actually the context of what we are talking about and where we are currently present. This will become more clear as we go along with this. A `Context` is **Interface to global information about an application environment**

Few important points about the context:

- It is the context of the current state of the application.
- It can be used to get information regarding the activity and application.
- It can be used to get access to resources, databases, and shared preferences, and etc.
- Both the Activity and Application classes extend the Context class.

## **What is `AndroidManifest.xml`?**

**The manifest file describes essential information about your app to the Android build tools**, the Android operating system, and Google Play. Among many other things, the manifest file is required to declare the following:

- **The app's package name, which usually matches your code's namespace**. The Android build tools use this to determine the location of code entities when building your project. When packaging the app, the build tools replace this value with the application ID from the Gradle build files, which is used as the unique app identifier on the system and on Google Play. [Read more about the package name and app ID](https://developer.android.com/guide/topics/manifest/manifest-intro#package-name).
- **The components of the app, which include all activities, services, broadcast receivers, and content provider**s. Each component must define basic properties such as the name of its Kotlin or Java class. It can also declare capabilities such as which device configurations it can handle, and intent filters that describe how the component can be started. [Read more about app components](https://developer.android.com/guide/topics/manifest/manifest-intro#components).
- **The permissions** that the app needs in order to access protected parts of the system or other apps. It also declares any permissions that other apps must have if they want to access content from this app. [Read more about permissions](https://developer.android.com/guide/topics/manifest/manifest-intro#perms).
- **The hardware and software features the app requires**, which affects which devices can install the app from Google Play. [Read more about device compatibility](https://developer.android.com/guide/topics/manifest/manifest-intro#compatibility).