![BBCODEBLOCK][BBCODEBLOCK]
```XML
<mui:BBCodeBlock BBCode="Simple rich text formatting using BBCode. Supporting [b]bold[/b], [i]italic[/i], [b][i]bold italic[/i][/b], [u]underline[/u], [color=#ff4500]colors[/color], [size=10]different[/size] [size=16]sizes[/size] and support for [url=http://xamlspy.com]navigable urls[/url].&#13;&#10;&#13;&#10;BBCode formatted text works great with MVVM.&#13;&#10;&#13;&#10;To learn more about link navigation see the [url=/Pages/Navigation.xaml|_top]navigation page[/url]." />
```
![MODERNBUTTON][BODERNBUTTON]
```XML
<mui:BBCodeBlock BBCode="Icons courtesy of [url=http://modernuiicons.com/]Modern UI Icons[/url]" Margin="0,0,0,16" />
    <mui:ModernButton Content="modern button" IconData="{StaticResource HomeIconData}" Margin="0,0,0,8" />
    <mui:ModernButton Content="disabled modern button" IconData="F1 M 24,13C 27.1521,13 29.9945,14.3258 32,16.4501L 32,11L 35,14L 35,22L 27,22L 24,19L 29.5903,19C 28.217,17.4656 26.2212,16.5 24,16.5C 20.1969,16.5 17.055,19.3306 16.5661,23L 13.0448,23C 13.5501,17.3935 18.262,13 24,13 Z M 24,31.5C 27.8031,31.5 30.945,28.6694 31.4339,25L 34.9552,25C 34.4499,30.6065 29.738,35 24,35C 20.8479,35 18.0055,33.6742 16,31.5499L 16,37L 13,34L 13,26L 21,26L 24,29L 18.4097,29C 19.783,30.5344 21.7787,31.5 24,31.5 Z" IsEnabled="False" Margin="0,0,0,16" />
```
![MODERNBUTTON-SIZE][MODERNBUTTON-SIZE]
```XML
  <mui:ModernButton EllipseDiameter="20" IconWidth="12" IconHeight="8"/>
  <mui:ModernButton />
  <mui:ModernButton EllipseDiameter="26" IconWidth="14" IconHeight="14" />
  <mui:ModernButton EllipseDiameter="32" IconWidth="20" IconHeight="20" />
  <mui:ModernButton EllipseDiameter="48" EllipseStrokeThickness="2" IconWidth="30" IconHeight="30" />
  <mui:ModernButton EllipseDiameter="64" EllipseStrokeThickness="2" IconWidth="42" IconHeight="42" />
```
![MODERNDIALOG-BUTTON][MODERNDIALOG-BUTTON]
```XML
<Button Content="common dialog" Margin="0,0,0,8" HorizontalAlignment="Left" Click="CommonDialog_Click"/>
```

![MODERNDIALOG-DIALOG][MODERNDIALOG-DIALOG]
```C#
private void CommonDialog_Click(object sender, RoutedEventArgs e)
        {
            var dlg = new ModernDialog {
                Title = "Common dialog",
                Content = new LoremIpsum()
            };
            dlg.Buttons = new Button[] { dlg.OkButton, dlg.CancelButton};
            dlg.ShowDialog();

            this.dialogResult.Text = dlg.DialogResult.HasValue ? dlg.DialogResult.ToString() : "<null>";
            this.dialogMessageBoxResult.Text = dlg.MessageBoxResult.ToString();
        }
```
![MESSAGEBOX][MESSAGEBOX]
```XML
<StackPanel Margin="0,0,0,8">
  <RadioButton x:Name="ok" Content="ok" IsChecked="True" Margin="0,0,0,2" />
  <RadioButton x:Name="okcancel" Content="ok, cancel" Margin="0,0,0,2"/>
  <RadioButton x:Name="yesno" Content="yes, no" Margin="0,0,0,2"/>
  <RadioButton x:Name="yesnocancel" Content="yes, no, cancel" Margin="0,0,0,2"/>
</StackPanel>
        
<Button Content="message dialog" Click="MessageDialog_Click" Margin="0,0,0,8"/>
  <TextBlock>
    <Run Text="MessageBox result:" />
    <Run x:Name="msgboxResult" FontWeight="Bold" />
  </TextBlock>
```
![MESSAGEBOX-DIALOG][MESSAGEBOX-DIALOG]
```C#
private void MessageDialog_Click(object sender, RoutedEventArgs e)
        {
            MessageBoxButton btn = MessageBoxButton.OK;
            if (true == ok.IsChecked) btn = MessageBoxButton.OK;
            else if (true == okcancel.IsChecked) btn = MessageBoxButton.OKCancel;
            else if (true == yesno.IsChecked) btn = MessageBoxButton.YesNo;
            else if (true == yesnocancel.IsChecked) btn = MessageBoxButton.YesNoCancel;

            var result = ModernDialog.ShowMessage("This is a simple Modern UI styled message dialog. Do you like it?", "Message Dialog", btn);

            this.msgboxResult.Text = result.ToString();
        }
```
![MODERNFRAME][MODERNFRAME]
```XML

```
![MODERNMENU][MODERNMENU]
```XML

```
![MODERNMENU-GROUP][MODERNMENU-GROUP]
```XML

```
=====
=====
###Progress Rings

####Pulse
```XML 
<mui:ModernProgressRing IsActive="True" Width="80" Height="80" Style="{StaticResource PulseProgressRingStyle}" />

```

![MODERNPROGRESSRING-PULSE][MODERNPROGRESSRING-PULSE] 
=====
####Double Bounce
```XML 
<mui:ModernProgressRing IsActive="True" Width="80" Height="80" Style="{StaticResource DoubleBounceProgressRingStyle}" />

```

![MODERNPROGRESSRING-DOUBLE][MODERNPROGRESSRING-DOUBLE]
=====
####Rotating Plane
```XML 
<mui:ModernProgressRing IsActive="True" Width="80" Height="80" Style="{StaticResource RotatingPlaneProgressRingStyle}" /> 

```

![MODERNPROGRESSRING-PLANE][MODERNPROGRESSRING-PLANE]
=====
####Three Bounce
```XML 
<mui:ModernProgressRing IsActive="True" Width="80" Height="80" Style="{StaticResource ThreeBounceProgressRingStyle}" /> 

```

![MODERNPROGRESSRING-THREE][MODERNPROGRESSRING-THREE]
=====
####Wandering Cubes
```XML 
<mui:ModernProgressRing IsActive="True" Width="80" Height="80" Style="{StaticResource WanderingCubesProgressRingStyle}" /> 

```

![MODERNPROGRESSRING-CUBES][MODERNPROGRESSRING-CUBES]
=====
####Wave
```XML 
<mui:ModernProgressRing IsActive="True" Width="80" Height="80" Style="{StaticResource WaveProgressRingStyle}" />

```

![MODERNPROGRESSRING-WAVE][MODERNPROGRESSRING-WAVE]
=====
####Chasing Dots
```XML 
<mui:ModernProgressRing IsActive="True" Width="80" Height="80" Style="{StaticResource ChasingDotsProgressRingStyle}" /> 

```

![MODERNPROGRESSRING-CHASING][MODERNPROGRESSRING-CHASING]
=====
####Circle
```XML 
<mui:ModernProgressRing IsActive="True" Width="80" Height="80" Style="{StaticResource CircleProgressRingStyle}" /> 

```

![MODERNPROGRESSRING-CIRCLE][MODERNPROGRESSRING-CIRCLE]
=====
```XML

```
![MODERNWINDOW-SETTINGS][MODERNWINDOW-SETTINGS]
![MODERNWINDOW][MODERNWINDOW]

=========================================================================================================================

[BBCODEBLOCK]:https://cloud.githubusercontent.com/assets/13318413/10554741/2e10a1a4-741b-11e5-84e6-4d6734e6edee.png
[BODERNBUTTON]:https://cloud.githubusercontent.com/assets/13318413/10495278/ff9faaec-726f-11e5-8db1-6f91edf0533f.png
[MODERNBUTTON-SIZE]:https://cloud.githubusercontent.com/assets/13318413/10495275/ff9d93ce-726f-11e5-9b8b-46da9f53d6fa.png
[MODERNDIALOG-BUTTON]:https://cloud.githubusercontent.com/assets/13318413/10495276/ff9e2f1e-726f-11e5-942f-58f7becf3a8f.png
[MODERNDIALOG-DIALOG]:https://cloud.githubusercontent.com/assets/13318413/10495277/ff9ed86a-726f-11e5-85da-9fa9ac6bc87e.png
[MESSAGEBOX]:https://cloud.githubusercontent.com/assets/13318413/10495279/ffa27060-726f-11e5-869a-9ed63c377e64.png
[MESSAGEBOX-DIALOG]:https://cloud.githubusercontent.com/assets/13318413/10495280/ffa83e64-726f-11e5-86ad-02148c259749.png
[MODERNFRAME]:https://cloud.githubusercontent.com/assets/13318413/10554743/2e122c4a-741b-11e5-8954-a4485bfdede0.PNG
[MODERNMENU]:https://cloud.githubusercontent.com/assets/13318413/10495282/ffb851d2-726f-11e5-87fe-2930120e5a7e.PNG
[MODERNMENU-GROUP]:https://cloud.githubusercontent.com/assets/13318413/10554742/2e10bf72-741b-11e5-9a0f-541ab4509f15.PNG
[MODERNPROGRESSRING-PULSE]:https://cloud.githubusercontent.com/assets/13318413/10495285/ffc05df0-726f-11e5-8538-ee66c30bfcb3.PNG
[MODERNPROGRESSRING-DOUBLE]:https://cloud.githubusercontent.com/assets/13318413/10495284/ffbe9a7e-726f-11e5-925e-3b0c469daac4.PNG
[MODERNPROGRESSRING-PLANE]:https://cloud.githubusercontent.com/assets/13318413/10495286/ffc1b240-726f-11e5-82e7-a647cdb090f7.PNG
[MODERNPROGRESSRING-THREE]:https://cloud.githubusercontent.com/assets/13318413/10495287/ffc6ffe8-726f-11e5-8e41-5e70e638fb36.PNG
[MODERNPROGRESSRING-CUBES]:https://cloud.githubusercontent.com/assets/13318413/10495288/ffd05a2a-726f-11e5-929f-e8fda61befd2.PNG
[MODERNPROGRESSRING-WAVE]:https://cloud.githubusercontent.com/assets/13318413/10495289/ffd3dfe2-726f-11e5-82c8-f81c16448645.PNG
[MODERNPROGRESSRING-CHASING]:https://cloud.githubusercontent.com/assets/13318413/10495290/ffd3f40a-726f-11e5-89d6-0fe29ccdd4c0.PNG
[MODERNPROGRESSRING-CIRCLE]:https://cloud.githubusercontent.com/assets/13318413/10495292/ffd7ba18-726f-11e5-992c-74bf275d712d.PNG
[MODERNWINDOW-SETTINGS]:https://cloud.githubusercontent.com/assets/13318413/10495758/58abcd58-7272-11e5-9a84-71f955c4b488.PNG
[MODERNWINDOW]:https://cloud.githubusercontent.com/assets/13318413/10495291/ffd66640-726f-11e5-98fe-f29ec438f0d0.PNG
