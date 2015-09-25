# mui_samples
Moder UI WPF Samples Reference.

### Instalation

In Visual Studio:

* Go to **Tools** ── **Extensions and Updates**
* Select **Online** and Search on **Visual Studio Gallery** for _mui wpf_
* That will give you this result: 

    ![Result][logo]

* Click **Download** and you are done.

### Create an App

In Visual Studio: *(again)*
Create a new **Visual C#** > **Windows** project and select **Modern UI WPF Navigation**.

Your new Application includes a MainWindow with two pages (**Home.xaml** and **SettingsPage.xaml**) stored in the Pages project folder. 

The App's basic structure is:

    └──Solution
      └── Project
        ├── Properties
        ├── References
        ├── App.xml
        |   └── App.xml.cs
        ├── MainWindow.xml
        |   └── MainWindow.xml.cs  
        └── packages.config

After installing mui for WPF in Visual Studio (https://github.com/firstfloorsoftware/mui) you may want to use this code samples as a reference building Zune-like apps.
    
All the samples were taked from the App provided by kozw in the application Demo FirstFloor in https://github.com/firstfloorsoftware/mui/releases

[logo]: https://cloud.githubusercontent.com/assets/13318413/10085538/a67dc8ce-62be-11e5-8637-c696709a67ce.PNG "Search Result"
