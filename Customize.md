## Customize

#### Modern UI Themes 
There are two built in themes for MUI, dark and light themes that can be easely changed modifying the file:



**App.xaml**

```xml
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="/FirstFloor.ModernUI;component/Assets/ModernUI.xaml" />
                <ResourceDictionary Source="/FirstFloor.ModernUI;component/Assets/ModernUI.White.xaml"/>
            </ResourceDictionary.MergedDictionaries>
        </ResourceDictionary>
```

Changing  `White` to `Dark`, 

this

![white](https://cloud.githubusercontent.com/assets/4912547/10302029/2b91219e-6bbd-11e5-90a0-31e89ff189ef.PNG)
```xml
<ResourceDictionary Source="/FirstFloor.ModernUI;component/Assets/ModernUI.White.xaml"/>
```
to


![black](https://cloud.githubusercontent.com/assets/4912547/10302027/2949e1fa-6bbd-11e5-9f63-1dea7fc1423f.PNG)
```xml
<ResourceDictionary Source="/FirstFloor.ModernUI;component/Assets/ModernUI.Dark.xaml"/>
```

#### 

#### Modern UI Navigation Application Settings
The MUI Navigation Template comes pre-configured with a settings page for the user to choose the window color, font size and selection color of the app. It's a very nice feature but once the app is closed the **settings are lost**. Here we will make this configuration persist with the help of a `settings` file, load settings when App start and save when it Ends.

First we will create the `settings` file to store the theme name, source of the theme, accent color and font size:

![addsettings](https://cloud.githubusercontent.com/assets/4912547/10302026/268b80a4-6bbd-11e5-9b6f-46ec699c7f91.PNG)

Then we will add the following parametters (it's easier to write the namespace instead of searching in the tree view):


![settings](https://cloud.githubusercontent.com/assets/4912547/10302028/2a5e63ae-6bbd-11e5-9fcb-30306aca81d1.PNG)
![write](https://cloud.githubusercontent.com/assets/4912547/10302030/2d025340-6bbd-11e5-903b-b232c7c9a005.PNG)


| Name                     | Type                       | Scope  | Value     |
| ------------------------ |:-------------------------- | ------ | ----------- | 
| SelectedAccentColor      | System.Windows.Media.Color |  User  |  #FF1BA1E2     |
| SelectedThemeSource      | System.Uri                 |  User  | ...Assets/ModernUI.Dark.xaml |
| SelectedThemeDisplayName | strng                      |  User  | dark |
| SelectedFontSize         | string                     |  User  | large |


To get those settings just write `var a = [filename].Settings.Default.[param];` and `[filename].Settings.Default.Save();` to all modified parametters (more about settings [MSDN](https://msdn.microsoft.com/en-us/library/aa730869(v=vs.80).aspx) and [DotNetPerls](http://www.dotnetperls.com/settings) )

In the Main Window we can load our settings this way, using `AppearanceViewModel` to apply it:
cs
```csharp
private AppearanceViewModel settings = new AppearanceViewModel();

public MainWindow()
{
    InitializeComponent();
    
    settings.SelectedTheme = new Link{
        DisplayName = AppSettings.Default.SelectedThemeDisplayName,
        Source = AppSettings.Default.SelectedThemeSource
    };
    settings.SelectedAccentColor = AppSettings.Default.SelectedAccentColor;
    settings.SelectedFontSize = AppSettings.Default.SelectedFontSize;            
}
```

Notice we also added a private property of AppearanceViewModel.

Now, to save the settings we can add a `Closing="Window_Closing"` event to our window:
xml
```xml
<mui:ModernWindow x:Class="App.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:mui="http://firstfloorsoftware.com/ModernUI"
        Title="App Title" IsTitleVisible="True"
        ContentSource="/Pages/Home.xaml"
        Closing="Window_Closing">
        -
        -
        -
```

cs
```csharp
private void Window_Closing(object sender, System.ComponentModel.CancelEventArgs e)
{
    AppSettings.Default.SelectedThemeDisplayName = settings.SelectedTheme.DisplayName;
    AppSettings.Default.SelectedThemeSource = settings.SelectedTheme.Source;
    AppSettings.Default.SelectedAccentColor = settings.SelectedAccentColor;
    AppSettings.Default.SelectedFontSize = settings.SelectedFontSize;
    AppSettings.Default.Save();
}
```

Now all changes will be saved in the settings file of your app, it's a very nice feature to have. To read more about themes look at the [mui wiki](https://github.com/firstfloorsoftware/mui/wiki/Create-a-custom-theme).
