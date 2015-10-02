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
```xml
                <ResourceDictionary Source="/FirstFloor.ModernUI;component/Assets/ModernUI.White.xaml"/>
```
to
```xml
                <ResourceDictionary Source="/FirstFloor.ModernUI;component/Assets/ModernUI.Dark.xaml"/>
```

#### 

#### Modern UI Navigation Application Settings
When creating a MUI project from Navigation Template you can choose bet
