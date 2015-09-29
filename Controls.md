## Controls
=====
#### Buttons
![Button][Button]
```XML
<StackPanel HorizontalAlignment="Left" Width="140">
  <Button Content="standard button" Margin="0,0,0,8" />
  <Button Content="disabled button" IsEnabled="False" Margin="0,0,0,32" />
</StackPanel>
```
![Checkbox][Checkbox]
```XML
<CheckBox Content="standard checkbox" Margin="0,0,0,4"  />
<CheckBox Content="three state checkbox" IsThreeState="True" Margin="0,0,0,4"  />
<CheckBox Content="disabled checkbox" IsEnabled="False" Margin="0,0,0,4" />
<CheckBox Content="disabled checked checkbox" IsChecked="True" IsEnabled="False" Margin="0,0,0,32" />
```
![Radio button][Radio-button]
```XML
<RadioButton Content="option 1" Margin="0,0,0,4"  />
<RadioButton Content="option 2" Margin="0,0,0,4" />
<RadioButton Content="option 3, disabled" IsEnabled="False" Margin="0,0,0,4"/>
<RadioButton Content="another option, disabled and checked" IsEnabled="False" IsChecked="True" GroupName="Foo" />
```
=====
#### Data Grid

![Data Grid][Data-grid]
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
#### Date

![Calendar][Calendar]
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
![Date picker][Datepicker]
```XML
<StackPanel HorizontalAlignment="Left">
  <DatePicker Margin="0,0,0,8" />
  <DatePicker IsEnabled="False" />
</StackPanel>
```

=====
#### Items Control

![Combo Box][Combobox-dropdown]
```XML
<ComboBox Margin="0,0,0,8" HorizontalAlignment="Left" MinWidth="100">
  <ComboBoxItem Content="Item 1" />
  <ComboBoxItem Content="Item 2" />
  <ComboBoxItem Content="Item 3" />
  <ComboBoxItem Content="Item 4" />
  <ComboBoxItem Content="Item 5" />
</ComboBox>
```
![combo Box (Editable)][combobox-editable]
```XML
<ComboBox IsEditable="True" Margin="0,0,0,32" HorizontalAlignment="Left" MinWidth="100">
  <ComboBoxItem Content="Item 1" />
  <ComboBoxItem Content="Item 2" />
  <ComboBoxItem Content="Item 3" />
  <ComboBoxItem Content="Item 4" />
  <ComboBoxItem Content="Item 5" />
</ComboBox>
```
![Context Menu][Context-menu]
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
![List Box][List-box]
```XML
<ListBox Margin="0,0,0,32">
  <ListBoxItem Content="Item 1" />
  <ListBoxItem Content="Item 2" />
  <ListBoxItem Content="Item 3" />
  <ListBoxItem Content="Item 4" />
  <ListBoxItem Content="Item 5" />
</ListBox>
```
![List View][List-view]
```XML
<ListView Margin="0,0,0,16">
  <ListViewItem Content="Item 1" />
  <ListViewItem Content="Item 2" />
  <ListViewItem Content="Item 3" />
  <ListViewItem Content="Item 4" />
  <ListViewItem Content="Item 5" />
</ListView>
```
![List View Columns][Columns]
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
![Tree View][Tree-view]
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
#### Progress Bar

![][]
```XML

```


=====
#### Sliders

![][]
```XML

```


=====
#### Text

![][]
```XML

```
![][]
```XML

```
![][]
```XML

```


=====
#### Sample Form

![][]
```XML

```


=======================================================================================================================
[Button]: https://cloud.githubusercontent.com/assets/13318413/10148949/5a99e5a2-65eb-11e5-8294-1fb76c948122.png
[Checkbox]: https://cloud.githubusercontent.com/assets/13318413/10148951/5d984528-65eb-11e5-91c9-00ec46fb6eac.png
[Radio-button]: https://cloud.githubusercontent.com/assets/13318413/10148955/67698d6e-65eb-11e5-9bff-423d5ed0198c.png
[Data-grid]: https://cloud.githubusercontent.com/assets/13318413/10148957/67906d30-65eb-11e5-8b6e-e9f43be5eea1.png
[Calendar]: https://cloud.githubusercontent.com/assets/13318413/10148956/678cd27e-65eb-11e5-99d1-8462b74340cd.png
[Datepicker]: https://cloud.githubusercontent.com/assets/13318413/10148958/67956dda-65eb-11e5-97d8-abe5b257ff0c.png
[Combobox-dropdown]: https://cloud.githubusercontent.com/assets/13318413/10148961/67a73f42-65eb-11e5-8bd3-816dd8e50c10.png
[Combobox-editable]: https://cloud.githubusercontent.com/assets/13318413/10148960/67a5a8b2-65eb-11e5-85dc-9783e6ccbb7c.png
[Context-menu]: https://cloud.githubusercontent.com/assets/13318413/10148962/67b64f3c-65eb-11e5-8020-ebd2f68d5545.png
[List-box]: https://cloud.githubusercontent.com/assets/13318413/10148964/67ba8516-65eb-11e5-9fca-7e53e539f07b.png
[List-view]: https://cloud.githubusercontent.com/assets/13318413/10148965/67be58a8-65eb-11e5-9349-904acc0f18a8.png
[Columns]: https://cloud.githubusercontent.com/assets/13318413/10148966/67c1c894-65eb-11e5-9dcd-4fd816e4deb3.png
[Tree-view]: https://cloud.githubusercontent.com/assets/13318413/10148967/67c7ad68-65eb-11e5-80b3-5482bfa945f9.png
[Progress-bar]: https://cloud.githubusercontent.com/assets/13318413/10148968/67c8ed0e-65eb-11e5-8c9d-ea357676ba72.png
[Slider]: https://cloud.githubusercontent.com/assets/13318413/10148969/67cc1bd2-65eb-11e5-8c80-57e50f54d7ff.png
[Text-styling]: https://cloud.githubusercontent.com/assets/13318413/10148970/67cf33bc-65eb-11e5-8977-d5cd1ada0ba8.png
[Text-and-password-box]: https://cloud.githubusercontent.com/assets/13318413/10148971/67d71636-65eb-11e5-9add-1c628fdebb2e.png
[Label]: https://cloud.githubusercontent.com/assets/13318413/10148972/67e7f654-65eb-11e5-9d92-857de38f18fd.png
[Sample-form]: https://cloud.githubusercontent.com/assets/13318413/10148973/67eacc76-65eb-11e5-8086-990f2c830b05.png
