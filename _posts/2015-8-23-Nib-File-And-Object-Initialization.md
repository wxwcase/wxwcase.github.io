---
layout: post
title: Nib File and Object Initialization
---

#### Nib-Based Initialization

(nib: NeXTStep Interface Builder)

A nib file consists of the names of classes along with instructions for instantiating and initializing them. The running app ends up generating instances based on what you originally drew in the ._storyboard_ file or ._xib_ file.

For example, if you create a button at a position in a ._xib_ or in the ._storyboard_, the equivalent code looks like this:

```swift
CGRect frame = CGRectMake(100, 100, 52, 30);
UIButton b = UIButton(frame: frame);
b.titleLabel?.text = "SomeText"
self.view.addSubview(b)
```
    
#### Nib File
- Nib files are a source of instances, and those instances are brought into existence as the nib file is loaded.
- A nib file is generated during the build process by compilation either from a ._xib_ file, which results in a single nib file, or from a ._storyboard_ file, which results in a .storyboardc bundle containing multiple nib files.
