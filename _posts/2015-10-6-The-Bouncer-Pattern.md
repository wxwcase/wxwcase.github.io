---
layout: post
title: The Bouncer Pattern
--- 

### Original post 
<a href="http://rikschennink.nl/thoughts/the-bouncer-pattern/" target="_blank">The original post about the Bouncer Pattern</a>

### What can be done in Swift
```swift
func parseServerData(data: NSData?, response: NSURLResponse?, error: NSError?) {
  guard error == nil else {
    print("ERROR: Unable to connect to server: \(error!.localizedDescription)")
    return
  }
  
  guard let data = data else {
    // Obtain information from response 
    print("Failed to download data from server.")
  }
  
  do {
    let something = try parseJSONData(data, options: []) as! SomeType
    // ... your code
  } catch {
    print("Unexpected data format provided by server.")
  }
}
```
