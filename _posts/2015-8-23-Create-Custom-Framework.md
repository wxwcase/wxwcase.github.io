---
layout: post
title: How to create custom framework
---

1. Edit the target and choose Editor -> Add Target 
2. On the left of the dialog, under iOS, select Framework & Library, on the right, select Cocoa Touch Framework, Next.
3. Give your framework a name (_xxx_), then Finish
4. you can add a _.swift_ file to the _xxx_ target, and inside it define an object type and declare it _public_, and if you _import_ _xxx_ back in one of 
your main app target's file, such as AppDelegate.swift, that file will be able to see the public members of the _xxx_ framework

*Embedded frameworks of this kind are not backward-compatible to iOS 7*
