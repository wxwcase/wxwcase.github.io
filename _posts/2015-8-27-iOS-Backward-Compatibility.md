---
layout: post
title: Backward Compatibility - iOS
---

There are various ways you can write your app's code conditionally based on the runtime environment:

- Explicit environment test: The **UIDevice** class

```swift
let v = UIDevice.currentDevice().systemVersion // get system version as a string
```

- Member safety: NSObject's respondsToSelector: method

```swift
if self.respondsToSelector("someMethodName") {
    let value = self.someMethodName()
}
```

- Class safefy: Use NSClassFromString function

```swift
if NSClassFromString("SomeClassYouWant2Cast") != nil {
    // statements
}
```

