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

The ANR dialog is displayed to the user based on two possible conditions. One is when there is **no response to an input event within 5 seconds**, and the other is when a **broadcast receiver is not done executing within 10 seconds.**

##  **What is a Fragment?**

A fragment is a part or portion of an activity. It is modular in a sense that you can move around or combine with other fragments in a single activity. Fragments are also reusable.