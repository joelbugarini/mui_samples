## Controls
### Buttons
![Button](https://cloud.githubusercontent.com/assets/13318413/10148949/5a99e5a2-65eb-11e5-8294-1fb76c948122.png)
```XML
<StackPanel HorizontalAlignment="Left" Width="140">
  <Button Content="standard button" Margin="0,0,0,8" />
  <Button Content="disabled button" IsEnabled="False" Margin="0,0,0,32" />
</StackPanel>
```
![Checkbox](https://cloud.githubusercontent.com/assets/13318413/10148951/5d984528-65eb-11e5-91c9-00ec46fb6eac.png)
```XML
<CheckBox Content="standard checkbox" Margin="0,0,0,4"  />
<CheckBox Content="three state checkbox" IsThreeState="True" Margin="0,0,0,4"  />
<CheckBox Content="disabled checkbox" IsEnabled="False" Margin="0,0,0,4" />
<CheckBox Content="disabled checked checkbox" IsChecked="True" IsEnabled="False" Margin="0,0,0,32" />
```
![Radio-button](https://cloud.githubusercontent.com/assets/13318413/10148955/67698d6e-65eb-11e5-9bff-423d5ed0198c.png)
```XML
<RadioButton Content="option 1" Margin="0,0,0,4"  />
<RadioButton Content="option 2" Margin="0,0,0,4" />
<RadioButton Content="option 3, disabled" IsEnabled="False" Margin="0,0,0,4"/>
<RadioButton Content="another option, disabled and checked" IsEnabled="False" IsChecked="True" GroupName="Foo" />
```
=====
### Data Grid

![Data-grid](https://cloud.githubusercontent.com/assets/13318413/10148957/67906d30-65eb-11e5-8b6e-e9f43be5eea1.png)
```XML
<DataGrid Name="DG1" ItemsSource="{Binding}" AutoGenerateColumns="False" >
  <DataGrid.Columns>
    <mui:DataGridTextColumn Header="First Name"  Binding="{Binding FirstName}"/>
    <mui:DataGridTextColumn Header="Last Name" Binding="{Binding LastName}" />
    <mui:DataGridTextColumn Header="Email" Binding="{Binding Email}"/>
    <mui:DataGridCheckBoxColumn Header="Member" Binding="{Binding IsMember}" />
    <mui:DataGridComboBoxColumn Header="Order Status" SelectedItemBinding="{Binding Status}" ItemsSource="{Binding Source={StaticResource myEnum}}" />
  </DataGrid.Columns>
</DataGrid>
```
=====
### Date

![Calendar](https://cloud.githubusercontent.com/assets/13318413/10148956/678cd27e-65eb-11e5-99d1-8462b74340cd.png)
```XML
<StackPanel Orientation="Horizontal">
  <Calendar Margin="0,0,8,0">
    <Calendar.BlackoutDates>
      <CalendarDateRange Start="1/1/2013" End="6/1/2013" />
    </Calendar.BlackoutDates>
  </Calendar>
  <Calendar Margin="0,0,0,32" IsEnabled="False" />
</StackPanel>
```
![Datepicker](https://cloud.githubusercontent.com/assets/13318413/10148958/67956dda-65eb-11e5-97d8-abe5b257ff0c.png)
```XML
<StackPanel HorizontalAlignment="Left">
  <DatePicker Margin="0,0,0,8" />
  <DatePicker IsEnabled="False" />
</StackPanel>
```

=====
### Items Control

![Combobox-dropdown](https://cloud.githubusercontent.com/assets/13318413/10148961/67a73f42-65eb-11e5-8bd3-816dd8e50c10.png)
```XML
<ComboBox Margin="0,0,0,8" HorizontalAlignment="Left" MinWidth="100">
  <ComboBoxItem Content="Item 1" />
  <ComboBoxItem Content="Item 2" />
  <ComboBoxItem Content="Item 3" />
  <ComboBoxItem Content="Item 4" />
  <ComboBoxItem Content="Item 5" />
</ComboBox>
```
![Combobox-editable](https://cloud.githubusercontent.com/assets/13318413/10148960/67a5a8b2-65eb-11e5-85dc-9783e6ccbb7c.png)
```XML
<ComboBox IsEditable="True" Margin="0,0,0,32" HorizontalAlignment="Left" MinWidth="100">
  <ComboBoxItem Content="Item 1" />
  <ComboBoxItem Content="Item 2" />
  <ComboBoxItem Content="Item 3" />
  <ComboBoxItem Content="Item 4" />
  <ComboBoxItem Content="Item 5" />
</ComboBox>
```
![Context-menu](https://cloud.githubusercontent.com/assets/13318413/10148962/67b64f3c-65eb-11e5-8020-ebd2f68d5545.png)
```XML
<Button Content="show context menu" Click="ShowContextMenu_Click" Margin="0,0,0,32" HorizontalAlignment="Left"/>
```
```C#
private void ShowContextMenu_Click(object sender, RoutedEventArgs e)
        {
            var contextMenu = new ContextMenu();
            
            contextMenu.Items.Add(new MenuItem { Header = "Item" });
            contextMenu.Items.Add(new MenuItem { Header = "Item with gesture", InputGestureText="Ctrl+C" });
            contextMenu.Items.Add(new MenuItem { Header = "Item, disabled", IsEnabled = false });
            contextMenu.Items.Add(new MenuItem { Header = "Item, checked", IsChecked = true });
            contextMenu.Items.Add(new MenuItem { Header = "Item, checked and disabled", IsChecked = true, IsEnabled = false });
            contextMenu.Items.Add(new Separator());
            contextMenu.Items.Add(CreateSubMenu("Item with submenu"));

            var menu = CreateSubMenu("Item with submenu, disabled");
            menu.IsEnabled = false;
            contextMenu.Items.Add(menu);
            
            contextMenu.IsOpen = true;
        }
```
![List-box](https://cloud.githubusercontent.com/assets/13318413/10148964/67ba8516-65eb-11e5-9fca-7e53e539f07b.png)
```XML
<ListBox Margin="0,0,0,32">
  <ListBoxItem Content="Item 1" />
  <ListBoxItem Content="Item 2" />
  <ListBoxItem Content="Item 3" />
  <ListBoxItem Content="Item 4" />
  <ListBoxItem Content="Item 5" />
</ListBox>
```
![List-view](https://cloud.githubusercontent.com/assets/13318413/10148965/67be58a8-65eb-11e5-9349-904acc0f18a8.png)
```XML
<ListView Margin="0,0,0,16">
  <ListViewItem Content="Item 1" />
  <ListViewItem Content="Item 2" />
  <ListViewItem Content="Item 3" />
  <ListViewItem Content="Item 4" />
  <ListViewItem Content="Item 5" />
</ListView>
```
![Columns](https://cloud.githubusercontent.com/assets/13318413/10148966/67c1c894-65eb-11e5-9dcd-4fd816e4deb3.png)
```XML
<ListView Margin="0,0,0,32">
  <ListView.View>
    <GridView>
      <GridViewColumn Header="Column 1" />
      <GridViewColumn Header="Column 2" />
      <GridViewColumn Header="Column 3" />
    </GridView>
  </ListView.View>

  <ListViewItem Content="Item 1" />
  <ListViewItem Content="Item 2" />
  <ListViewItem Content="Item 3" />
  <ListViewItem Content="Item 4" />
  <ListViewItem Content="Item 5" />
  </ListView>
```
![Tree-view](https://cloud.githubusercontent.com/assets/13318413/10148967/67c7ad68-65eb-11e5-80b3-5482bfa945f9.png)
```XML
<TreeView>
  <TreeViewItem Header="Item 1">
    <TreeViewItem Header="Item 1.1" />
    <TreeViewItem Header="Item 1.2" />
    <TreeViewItem Header="Item 1.3" />
  </TreeViewItem>
  <TreeViewItem Header="Item 2">
    <TreeViewItem Header="Item 2.1" />
    <TreeViewItem Header="Item 2.2" />
    <TreeViewItem Header="Item 2.3" />
  </TreeViewItem>
  <TreeViewItem Header="Item 3">
      <TreeViewItem Header="Item 3.1" />
      <TreeViewItem Header="Item 3.2" />
      <TreeViewItem Header="Item 3.3" />
  </TreeViewItem>
  <TreeViewItem Header="Item 4" />
  <TreeViewItem Header="Item 5" />
</TreeView>
```
=====
### Progress Bar

![Progress-bar](https://cloud.githubusercontent.com/assets/13318413/10148968/67c8ed0e-65eb-11e5-8c9d-ea357676ba72.png)
```XML
<ProgressBar Minimum="0" Maximum="1" Height="16" IsIndeterminate="True" Margin="0,0,0,16" />
<ProgressBar Minimum="0" Maximum="1" Value=".7" Height="16" IsIndeterminate="False" Margin="0,0,0,16" />
```

=====
### Sliders

![Slider](https://cloud.githubusercontent.com/assets/13318413/10148969/67cc1bd2-65eb-11e5-8c80-57e50f54d7ff.png)
```XML
<Slider Margin="0,0,0,16" />
  <Slider IsEnabled="False" Value="3" TickPlacement="Both" Margin="0,0,0,16" />
  <Slider IsSelectionRangeEnabled="True" SelectionStart="4" SelectionEnd="7" TickPlacement="Both" Margin="0,0,0,16" />

<StackPanel Orientation="Horizontal" Height="200">
  <Slider Orientation="Vertical" />
  <Slider Orientation="Vertical" IsEnabled="False" Value="3" TickPlacement="Both" Margin="16,0,0,0" />
  <Slider Orientation="Vertical" IsSelectionRangeEnabled="True" SelectionStart="4" SelectionEnd="7" TickPlacement="Both" Margin="16,0,0,0" />
</StackPanel>
```

=====
### Text

![Text-styling](https://cloud.githubusercontent.com/assets/13318413/10148970/67cf33bc-65eb-11e5-8977-d5cd1ada0ba8.png)
```XML
<TextBlock Text="HEADING1" Style="{StaticResource Heading1}" Margin="0,0,0,8" />
<TextBlock Text="HEADING2" Style="{StaticResource Heading2}" Margin="0,0,0,8"/>
<TextBlock Text="title" Style="{StaticResource Title}" Margin="0,0,0,8"/>
<TextBlock Text="Normal" Margin="0,0,0,8"/>
<TextBlock Text="small" Style="{StaticResource Small}" Margin="0,0,0,8"/>
<TextBlock Text="EMPHASIS" Style="{StaticResource Emphasis}" Margin="0,0,0,8"/>
<TextBlock Text="Fixed" Style="{StaticResource Fixed}" Margin="0,0,0,32"/>
```
![Text-and-password-box](https://cloud.githubusercontent.com/assets/13318413/10148971/67d71636-65eb-11e5-9add-1c628fdebb2e.png)
```XML
<TextBox Text="textbox" Margin="0,0,0,8"/>
<TextBox Text="readonly textbox" IsReadOnly="True" Margin="0,0,0,8"/>
<TextBox Text="disabled textbox" IsEnabled="False" Margin="0,0,0,8"/>
<PasswordBox Password="12345" Margin="0,0,0,32"/>
```
![Label](https://cloud.githubusercontent.com/assets/13318413/10148972/67e7f654-65eb-11e5-9d92-857de38f18fd.png)
```XML
<Label Content="label" Margin="0,0,0,8"/>
<Label Content="disabled label" IsEnabled="False" />
```
=====
### Sample Form

![Sample-form](https://cloud.githubusercontent.com/assets/13318413/10148973/67eacc76-65eb-11e5-8086-990f2c830b05.png)
```XML
<StackPanel MinWidth="200">


            <TextBlock Text="SAMPLE FORM" Style="{StaticResource Heading2}" Margin="0,0,0,8" />
            <mui:BBCodeBlock BBCode="A sample form demonstrating various controls with support for validation and focus visualization." Margin="0,0,0,16"/>

            <!-- actual form starts here -->
            <StackPanel x:Name="Form" Orientation="Vertical">

                <!-- create viewmodel -->
                <StackPanel.DataContext>
                    <app:SampleFormViewModel />
                </StackPanel.DataContext>

                <StackPanel.Resources>
                    <Style TargetType="StackPanel">
                        <Setter Property="Orientation" Value="Horizontal" />
                        <Setter Property="Margin" Value="0,0,0,4" />
                    </Style>
                    <Style TargetType="Label" BasedOn="{StaticResource {x:Type Label}}">
                        <Setter Property="Width" Value="100" />
                        <Setter Property="VerticalAlignment" Value="Center" />
                    </Style>
                    <Style TargetType="CheckBox" BasedOn="{StaticResource {x:Type CheckBox}}">
                        <Setter Property="Padding" Value="0,3" />
                    </Style>
                    <Style TargetType="RadioButton" BasedOn="{StaticResource {x:Type RadioButton}}">
                        <Setter Property="Padding" Value="0,3" />
                    </Style>
                </StackPanel.Resources>

                <StackPanel>
                    <Label Content="First name" Target="{Binding ElementName=TextFirstName}"/>
                    <TextBox x:Name="TextFirstName" Width="150" Text="{Binding FirstName, Mode=TwoWay, ValidatesOnDataErrors=True}" />
                </StackPanel>
                <StackPanel>
                    <Label Content="Last name" Target="{Binding ElementName=TextLastName}"/>
                    <TextBox x:Name="TextLastName" Width="150" Text="{Binding LastName, Mode=TwoWay, ValidatesOnDataErrors=True}"/>
                </StackPanel>
                <StackPanel>
                    <Label Content="Gender" Target="{Binding ElementName=RadioGendeMale}"/>
                    <RadioButton x:Name="RadioGendeMale" Content="Male" />
                    <RadioButton Content="Female" Margin="8,0,0,0" />
                </StackPanel>
                <StackPanel>
                    <Label Content="Birth date" Target="{Binding ElementName=DateBirth}" />
                    <DatePicker x:Name="DateBirth" />
                </StackPanel>
                <StackPanel>
                    <Label Content="Address" Target="{Binding ElementName=TextAddress}"/>
                    <TextBox x:Name="TextAddress" Width="150" />
                </StackPanel>
                <StackPanel>
                    <Label Content="City" Target="{Binding ElementName=TextCity}"/>
                    <TextBox x:Name="TextCity" Width="150" />
                </StackPanel>
                <StackPanel>
                    <Label Content="State" Target="{Binding ElementName=ComboState}"/>
                    <ComboBox x:Name="ComboState" Width="150">
                        <ComboBoxItem>Alabama</ComboBoxItem>
                        <ComboBoxItem>Alaska</ComboBoxItem>
                                        •
                                        •
                                        •
                        <ComboBoxItem>Washington</ComboBoxItem>
                        <ComboBoxItem>West Virginia</ComboBoxItem>
                        <ComboBoxItem>Wisconsin</ComboBoxItem>
                        <ComboBoxItem>Wyoming</ComboBoxItem>
                    </ComboBox>
                </StackPanel>
                <StackPanel>
                    <Label Content="Zip code" Target="{Binding ElementName=TextZipCode}"/>
                    <TextBox x:Name="TextZipCode" Width="150" />
                </StackPanel>
                <StackPanel >
                    <Label />
                    <CheckBox Content="I agree to the terms of use" />
                </StackPanel>

                <Button Content="Submit" Margin="100,16,0,0" HorizontalAlignment="Left" />
            </StackPanel>
        </StackPanel>
```

