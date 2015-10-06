---
layout: post
title: Add UITextField to UIAlertController
--- 

### Add UITextField
#### Code Snippet:
```swift
@IBAction func addName(sender: AnyObject) {
  let alert = UIAlertController(title: "New Name", message: nil, preferredStyle: .Alert)
        
  let saveAction = UIAlertAction(title: "Save", style: .Default, handler: {
    (action: UIAlertAction) -> Void in
    let textField = alert.textFields!.first
    self.names.append(textField!.text!)
    self.tableView.reloadData()
  })
        
  let cancelAction = UIAlertAction(title: "Cancel", style: .Default, handler: {
    (action: UIAlertAction) -> Void in
  })
        
  alert.addTextFieldWithConfigurationHandler({
    (textField: UITextField) -> Void in
    textField.placeholder = "add a new name"
  })
        
  alert.addAction(saveAction)
  alert.addAction(cancelAction)
        
  presentViewController(alert, animated: true, completion: nil)
}
```
