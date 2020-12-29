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

## What are the two types of context?

- **Application Context:** It is the application and we are present in Application. For example - MyApplication(which extends Application class). It is an instance of MyApplication only.
- **Activity Context:** It is the activity and we are present in Activity. For example - MainActivity. It is an instance of MainActivity only.

## **What is `Application` class?**

The Application class in Android is the base class within an Android app that contains all other components such as activities and services. The Application class, or any subclass of the Application class, is instantiated before any other class when the process for your application/package is created.

**Base class for maintaining global application state.** You can provide your own implementation by creating a subclass and specifying the fully-qualified name of this subclass as the `"android:name"` attribute in your AndroidManifest.xml's `<application>` tag. The Application class, or your subclass of the Application class, is instantiated before any other class when the process for your application/package is created.

## **What is `Activity` and its lifecycle?** 

To navigate transitions between stages of the activity lifecycle, the Activity class provides a core set of six callbacks: `onCreate()`, `onStart()`, `onResume()`, `onPause()`, `onStop()`, and `onDestroy()`. The system invokes each of these callbacks as an activity enters a new state.

![img](https://developer.android.com/guide/components/images/activity_lifecycle.png)

## Lifecycle callbacks

* `onCreate()`: fires when the system first creates the activity. On activity creation, the activity enters the *Created* state. In the `onCreate()` method, you perform basic application startup logic that should happen only once for the entire life of the activity. 

* `onStart()`: The `onStart()` call makes the activity visible to the user, as the app prepares for the activity to enter the foreground and become interactive

* `onResume()`: When the activity enters the Resumed state, it comes to the foreground, and then the system invokes the `onResume()` callback. This is the state in which the app interacts with the user. The app stays in this state until something happens to take focus away from the app.

* `onPause()`:The system calls this method as the first indication that the user is leaving your activity (though it does not always mean the activity is being destroyed); it indicates that the activity is no longer in the foreground (though it may still be visible if the user is in multi-window mode). Use the [`onPause()`](https://developer.android.com/reference/android/app/Activity#onPause()) method to pause or adjust operations that should not continue (or should continue in moderation) while the [`Activity`](https://developer.android.com/reference/android/app/Activity) is in the Paused state, and that you expect to resume shortly. There are several reasons why an activity may enter this state. For example:

  - Some event interrupts app execution, as described in the [onResume()](https://developer.android.com/guide/components/activities/activity-lifecycle#onresume) section. This is the most common case.

  - In Android 7.0 (API level 24) or higher, multiple apps run in multi-window mode. Because only one of the apps (windows) has focus at any time, the system pauses all of the other apps.

  - A new, semi-transparent activity (such as a dialog) opens. As long as the activity is still partially visible but not in focus, it remains paused.

	You can also use the [`onPause()`](https://developer.android.com/reference/android/app/Activity#onPause()) method to release system resources, handles to sensors (like GPS), or any resources that may affect battery life while your activity is paused and the user does not need them. However, as mentioned above in the onResume() section, a Paused activity may still be fully visible if in multi-window mode. As such, you should consider using onStop() instead of onPause() to fully release or adjust UI-related resources and operations to better support multi-window mode.
	
* `
  onStop()
  `:  When your activity is no longer visible to the user, it has entered the *Stopped* state, and the system invokes the `onStop()` callback. This may occur, for example, when a newly launched activity covers the entire screen. The system may also call `onStop()` when the activity has finished running, and is about to be terminated.
  
  In the `onStop()` method, the app should release or adjust resources that are not needed while the app is not visible to the user. For example, your app might pause animations or switch from fine-grained to coarse-grained location updates. Using `onStop()` instead of `onPause()` ensures that UI-related work continues, even when the user is viewing your activity in multi-window mode.
  
  You should also use `onStop()` to perform relatively CPU-intensive shutdown operations. For example, if you can't find a more opportune time to save information to a database, you might do so during `onStop()`
  
* `onDestroy()`: [`onDestroy()`](https://developer.android.com/reference/android/app/Activity#onDestroy()) is called before the activity is destroyed. The system invokes this callback either because:

  1. the activity is finishing (due to the user completely dismissing the activity or due to [`finish()`](https://developer.android.com/reference/android/app/Activity#finish()) being called on the activity), or
  2. the system is temporarily destroying the activity due to a configuration change (such as device rotation or multi-window mode)

  Instead of putting logic in your Activity to determine why it is being destroyed you should use a [`ViewModel`](https://developer.android.com/reference/androidx/lifecycle/ViewModel) object to contain the relevant view data for your Activity. If the Activity is going to be recreated due to a configuration change the ViewModel does not have to do anything since it will be preserved and given to the next Activity instance. If the Activity is not going to be recreated then the ViewModel will have the [`onCleared()`](https://developer.android.com/reference/androidx/lifecycle/ViewModel#onCleared()) method called where it can clean up any data it needs to before being destroyed.

## What is the order of life cycles callbacks to go from activity A to Activity B?

The order of lifecycle callbacks is well defined, particularly when the two activities are in the same process (app) and one is starting the other. Here's the order of operations that occur when Activity A starts Activity B:

1. Activity A's `onPause()` method executes.
2. Activity B's `onCreate()`, `onStart()`, and `onResume()` methods execute in sequence. (Activity B now has user focus.)
3. Then, if Activity A is no longer visible on screen, its `onStop()` method executes.

This predictable sequence of lifecycle callbacks allows you to manage the transition of information from one activity to another.

## **When only onDestroy is called for an activity without onPause() and onStop()?**

**onPause() and onStop() will not be invoked if finish() is called from within the onCreate() method.** This might occur, for example, if you detect an error during onCreate() and call finish() as a result. In such a case, though, any cleanup you expected to be done in onPause() and onStop() will not be executed.

Although onDestroy() is the last callback in the lifecycle of an activity, it is worth mentioning that this callback may not always be called and should not be relied upon to destroy resources. There are situations where the system will simply kill the activity's hosting process without calling this method (or any others) in it, so it should not be used to do things that are intended to remain around after the process goes away.It is better have the resources created in onStart() and onResume(), and have them destroyed in onStop() and onPause, respectively.

## **Why do we need to call `setContentView()` in `onCreate()` of Activity class?**

Since `onStart()` and `onResume()` are called several times, is highly inefficient create UI objects in these methods, that is an action should be done only once in the entire activity life cycle 

## **What is `Fragment` and its lifecycle.**

**A [`Fragment`](https://developer.android.com/reference/androidx/fragment/app/Fragment) represents a reusable portion of your app's UI**. A fragment defines and manages its own layout, has its own lifecycle, and can handle its own input events. Fragments cannot live on their own--they must be *hosted* by an activity or another fragment. The fragment’s view hierarchy becomes part of, or *attaches to*, the host’s view hierarchy.



![fragment lifecycle states and their relation both the fragment's             lifecycle callbacks and the fragment's view lifecycle](https://developer.android.com/images/guide/fragments/fragment-view-lifecycle.png)

When fragment come up on the screen:-

1. `onAttach()` — This method called first, To know that our fragment has been attached to an activity. We are passing the Activity that will host our fragment.
2. `onCreate()` —  This method called when a fragment instance initializes, just after the onAttach where fragment attaches to the host activity.
3. `onCreateView()` —  The method called when it’s time for the fragment to draw its user interface for the first time. To draw a UI for your fragment, you must return a View component from this method that is the root of your fragment’s layout. You can return null if the fragment does not provide a UI.
4. `onActivityCreated()` — This method called when Activity completes its onCreate() method
5. `onStart() `— This method called when a fragment is visible.
6. `onResume()` — This method called when a fragment is visible and allowing the user to interact with it. Fragment resumes only after activity resumes.

When fragment goes out off the screen:-

1. `onPause()` — This method called when a fragment is not allowing the user to interact; the fragment will get change with other fragment or it gets removed from activity or fragment’s activity called a pause.
2. `onStop() `— This method called when the fragment is no longer visible; the fragment will get change with other fragment or it gets removed from activity or fragment’s activity called stop.
3. `onDestroyView()`—  This method called when the view and related resources created in onCreateView() are removed from the activity’s view hierarchy and destroyed.
4. `onDestroy() `—  This method called when the fragment does its final clean up.
5. `onDetach()` —  This method called when the fragment is detached from its host activity.

## **What are "launch modes"?** 

Launch modes allow you to define how a new instance of an activity is associated with the current task. You can define different launch modes in two ways:

- Using the manifest file

  When you declare an activity in your manifest file, you can specify how the activity should associate with tasks when it starts.

- Using Intent flags

  When you call `startActivity()`, you can include a flag in the `Intent` that declares how (or whether) the new activity should associate with the current task.

The Launch modes are:

* `android:launchMode=”standard”`: Start Activity B with standard mode. A new instance of Activity B in the task will be created.

  ![Image for post](https://miro.medium.com/max/1439/1*kaShwhObzgW_4IrvkjdY7g.png)

  Below diagram explain that if Activity B already has one instance then to start the Activity B again will create new instance of it on the same task.

![Image for post](https://miro.medium.com/max/1625/1*ef6MzPZKwRgLypakjI4CCg.png)

* `android:launchMode=”singleTop”`: Start Activity D with singleTop mode. A new instance of Activity D in the task will be created.

![Image for post](https://miro.medium.com/max/1521/1*bDAA43abHHQ8TRRYHIndSA.png)

​	Below diagram explain that if Activity D already has one instance then to start the Activity D again will not create new instance for it rather system will forward call via onNewIntent() method.



![Image for post](https://miro.medium.com/max/1653/1*hEF5oj9D-JK4vfxAGrXYcg.png)

* `android:launchMode=”singleTask”`: Start Activity B with singleTask mode. A new task will be created and a new instance will be created.

![Image for post](https://miro.medium.com/max/1690/1*yFt-SXT-AUDgfIa8jxF0hA.png)

Below diagram explain that if Activity B already has one instance then to start the Activity B again will not create new instance for it rather system will forward call via onNewIntent() method. Here you can observe that Activity B has cleared activity record on top of it and is now root of the task.

![Image for post](https://miro.medium.com/max/60/1*z4a6Z7Vvm9dcXe-C879ygA.png?q=20)

![Image for post](https://miro.medium.com/max/2096/1*z4a6Z7Vvm9dcXe-C879ygA.png)

* `android:launchMode=”singleInstance”`: Start Activity D with standard mode. A new instance will be created in different task.

![Image for post](https://miro.medium.com/max/1731/1*2BUTymbcGxaL3zl1wrR5KQ.png)

Below diagram explain that if Activity D starts the Activity E then it will be created in the previous task. Activity D will always remain root Activity of the task.

![Image for post](https://miro.medium.com/max/1920/1*Ixhr7ZDWgRbj91CCxae8Sg.png)

Below diagram explain that if Activity D already has one instance then to start the Activity D again (In our case stared again from Activity E) will not create new instance for it rather system will forward call via onNewIntent() method.

![Image for post](https://miro.medium.com/max/1920/1*crHTqI8t5xU5oITJmDevTg.png)