### What is this
This is the .NET library that aims to provide as simple as possible cross-platform system dialog interface for developers. 

### How to use
1. Add [``DialogService``](https://www.nuget.org/packages/DialogService/) NuGet package to your project.

```
dotnet add package DialogService
```

2. Add references to implementations. 

```
dotnet add package DialogService.Win32
dotnet add package DialogService.Linux
dotnet add package DialogService.MacOS
```

There may be other implementations or your own

3. Create a builder class, register implementations and get the required implementation.

```csharp
using DialogService.Items;
...
// Using DialogPlatformBuilder to register all platforms and get a required one.
var dsBuilder = new DialogPlatformBuilder();
dsBuilder.AddPlatform<Win32.PlatformImplementation>();
dsBuilder.AddPlatform<Linux.PlatformImplementation>();
dsBuilder.AddPlatform<MacOS.PlatformImplementation>();
var dialogService = dsBuilder.GetService();

// Creating a dialog model with items.
var dialog = new Dialog();
dialog.Title = "The Dialog";

dialog.Items.Add(new Button("Click me"));
dialog.Items.Add(new Label("This is the label!"));

dialog.BottomPanel.Add(new Button("OK"));
dialog.BottomPanel.Add(new Button("Cancel"));

// Show the model
dialogService.Show(dialog);
```

### Platforms
 - ✔️ **Windows**: half-implemented with WPF
 
   ![image](https://user-images.githubusercontent.com/25367511/80859811-2dbdee00-8c6c-11ea-8ecc-558f96a3f692.png)
   
 - ⛔ **Linux**: not implemented
 - ⛔ **macOS**: not implemented

