## Layout

#### Basic 
The basic layout uses all the available content space. All that needs to be done is to set the Style of the page root to **ContentRoot**, this ensures the content is properly aligned. Use a **ScrollViewer** control to ensure all content is accessible.

![Basic Layout][basic]
```XML
<Grid Style="{StaticResource ContentRoot}">
  <ScrollViewer>
    <StackPanel>
      <TextBlock Text="LOREM IPSUM" Style="{StaticResource Heading2}" />
    </StackPanel>
  </ScrollViewer>
</Grid>
```
=====
#### Split

The split layout divides the page content into two columns. Resources **SplitLeft** and **SplitRight** provide the correct margins.

![Split Layout][split]
```XML
<Grid Style="{StaticResource ContentRoot}">
  <Grid.ColumnDefinitions>
    <ColumnDefinition Width="*"/>
    <ColumnDefinition Width="6"/>
    <ColumnDefinition Width="*"/>
  </Grid.ColumnDefinitions>

  <ScrollViewer Margin="{StaticResource SplitLeft}">
    .. left content ..
  </ScrollViewer>
  <GridSplitter Grid.Column="1" />
  <ScrollViewer Grid.Column="2 " Margin="{StaticResource SplitRight}">
    .. right content ..
  </ScrollViewer>
</Grid>
```
=====
#### List

The list layout features a list selection on the left-side of the page and the selected page content is shown in a **ModernFrame** on the right. Use the **ModernTab** control and specify a list of links. Make sure the ModernTab.Layout is set to **List**.

![List Layout][list]
```XML
<Grid Style="{StaticResource ContentRoot}">
  <mui:ModernTab SelectedSource="/Content/LoremIpsum.xaml#1" Layout="List">
    <mui:ModernTab.Links>
      <mui:Link DisplayName="Lorem Ipsum 1" Source="/Content/LoremIpsum.xaml#1" />
      <mui:Link DisplayName="Lorem Ipsum 2" Source="/Content/LoremIpsum.xaml#2" />
    </mui:ModernTab.Links>
  </mui:ModernTab>
</Grid>
```
=====
#### Tab
The tab layout renders tab items at the right side of the page. It uses the exact same **ModernTab** control as the List layout, the only difference is that the Layout must be set to **Tab**. You can use the tab layout to host pages that have a basic, split or list layout as is demonstrated in the image below.

![Tab Layout][tab]
```XML
<Grid Style="{StaticResource ContentRoot}">
  <mui:ModernTab SelectedSource="/Content/LoremIpsum.xaml#1" Layout="Tab">
    <mui:ModernTab.Links>
      <mui:Link DisplayName="Lorem Ipsum 1" Source="/Content/LoremIpsum.xaml#1" />
      <mui:Link DisplayName="Lorem Ipsum 2" Source="/Content/LoremIpsum.xaml#2" />
    </mui:ModernTab.Links>
  </mui:ModernTab>
</Grid>
```


=================================================================================================================
[wireframe]: https://cloud.githubusercontent.com/assets/13318413/10109476/fa60f412-637b-11e5-9413-26fed82a1e2d.PNG
[basic]: https://cloud.githubusercontent.com/assets/13318413/10109477/fa62740e-637b-11e5-826d-195d257db0c8.PNG
[split]: https://cloud.githubusercontent.com/assets/13318413/10109478/fa643456-637b-11e5-9f01-96889784c243.PNG
[list]: https://cloud.githubusercontent.com/assets/13318413/10109479/fa6983b6-637b-11e5-92f2-0d2c5998d7db.PNG
[tab]: https://cloud.githubusercontent.com/assets/13318413/10109475/fa5ff472-637b-11e5-801f-fe8c1260ef42.PNG
