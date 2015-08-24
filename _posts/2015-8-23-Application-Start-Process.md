---
layout: post
title: How Application Start - iOS
---

### Your App's Entry Point
Regardless of whether you write your own main.swift file or you rely on the swift @UIApplicationMain attribute, you are calling UIApplicationMain
How a customized main.swift file looks like:

```swift
import UIKit
UIApplicationMain(Process.argc, Process.unsafeArgv, nil, NSStringFromClass(AppDelegate))
```

### What UIApplicationMain does:
- UIApplication creates your app's first instance: the shared application instance:
    ```swift
    UIApplication.sharedApplication()
    ```
- UIApplicationMain also creates your app's second instance: the application's delegate
- If the Info.plist file specifies a main storyboard file, UIApplicationMain loads it and looks inside it to find the view controller that is designated as this storyboard's _initial_ _view_ _controller_, and it instantiates this view controller (third instance)
- If there was a main storyboard file, UIApplicationMain now creates your app's window (fourth instance)
	* It assigns this window instance as the app delegate's **window** property
	* It also assigns the initial view controller instance as the window instance's root view controller **rootViewController** property
	- UIApplicationMain now turns to the app delegate instance and starts calling some of its code (application:willFinishLaunchingWithOptions:)
- If there was a main storyboard, UIApplicationMain now causes your app's interface to appear, by calling the UIWindow instance method _makeKeyAndVisible_.
- The window is about to appear. This causes the window to turn to its root view controller and tell it to obtain its main view, which will occupy and appear in the window. 
	* If this view controller gets its view from a _.storyboard_ file or _.xib_ file, the corresponding nib is now loaded.
	* Its objects are instantiated and initialized

### Initial Instances When App Loaded
- the shared application instance 
- the window 
- the initial view controller
- the initial view controller's view and its subviews
