### What is .NET Dialog Service
This is the .NET library that aims to provide as simple as possible cross-platform system dialog interface for developers. 

### How to use
1. Add [DialogService.CrossPlatform](https://github.com/DialogService/DialogService.CrossPlatform) reference.
2. Add [DialogService](https://github.com/DialogService/DialogService) reference.
3. Follow this example:
```csharp
using DialogService;
using DialogService.Items;

var dialogService = CrossPlatform.DialogService.Get(); // get's implementation for current platform
var dialog = new Dialog("Test Dialog"); // create a dialog model with title

// use items from DialogService.Items namespace
dialog.Items.Add(new Button("Click me")); 
dialog.Items.Add(new Label("This is the label!"));

dialog.BottomPanel.Add(new Button("OK"));
dialog.BottomPanel.Add(new Button("Cancel"));

dialogService.Show(dialog);
```

### Platforms
 - ✔️ **Windows**: half-implemented with WPF
 
   ![image](https://user-images.githubusercontent.com/25367511/80859811-2dbdee00-8c6c-11ea-8ecc-558f96a3f692.png)
   
 - ⛔ **Linux**: not implemented
 - ⛔ **macOS**: not implemented

