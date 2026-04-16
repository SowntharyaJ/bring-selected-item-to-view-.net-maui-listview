# How to automatically scroll to bring the selected item into the view in .NET MAUI ListView

This example demonstrate how to automatically scroll to bring the selected item into the view in .NET MAUI ListView.

## Sample

```xaml
<ListView:SfListView x:Name="listView"
                             ItemSize="70" 
                             GroupHeaderSize="50"
                             HeaderSize="50"
                             SelectionMode="Single"
                             IsStickyGroupHeader="True"
                             ItemsSource="{Binding ContactsInfo}"
                             AllowGroupExpandCollapse="True"
                             SelectedItem="{Binding SelectedItem}">

    <ListView:SfListView.Behaviors>
        <local:ListViewBehavior/>
    </ListView:SfListView.Behaviors>

    <ListView:SfListView.GroupHeaderTemplate>
        <DataTemplate>
            <StackLayout BackgroundColor="#E4E4E4">
                <Label Text="{Binding Key}" FontSize="20" FontAttributes="Bold" TextColor="#4d4d4d" Padding="10,0,0,0" VerticalOptions="Center" HorizontalOptions="Start"/>
            </StackLayout>
        </DataTemplate>
    </ListView:SfListView.GroupHeaderTemplate>
    
    <ListView:SfListView.ItemTemplate>
        <DataTemplate>
            <Grid x:Name="grid" RowSpacing="0">

                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="70" />
                    <ColumnDefinition Width="*" />
                </Grid.ColumnDefinitions>

                <Image Grid.Column="0"
                            Source="{Binding ContactImage}"
                            VerticalOptions="Center"
                            HorizontalOptions="Center"
                            HeightRequest="50"
                            WidthRequest="50" />

                <Grid Grid.Row="0" Grid.Column="1" RowSpacing="2" Padding="10,0,0,0" VerticalOptions="Center">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="*" />
                        <RowDefinition Height="*" />
                    </Grid.RowDefinitions>
                    <Label LineBreakMode="NoWrap"
                                Grid.Row="0"
                                TextColor="#DE000000"
                                Text="{Binding ContactName}"
                                FontFamily="Roboto"
                                VerticalOptions="End"
                                VerticalTextAlignment="End"
                                FontSize="{OnPlatform Android={OnIdiom Phone=16, Tablet=18}, iOS=16, UWP=16}" />
                    <Label Grid.Row="1"
                                Grid.Column="0"
                                TextColor="#99000000"
                                FontFamily="Roboto"
                                LineBreakMode="NoWrap"
                                VerticalOptions="Start"
                                VerticalTextAlignment="Start"
                                Text="{Binding ContactNumber}"
                                FontSize="{OnPlatform Android={OnIdiom Phone=14, Tablet=14}, iOS=14, UWP=14}" />
                </Grid>
            </Grid>
        </DataTemplate>
    </ListView:SfListView.ItemTemplate>
</ListView:SfListView>
```

**[View document in Syncfusion .NET MAUI Knowledge Base](https://www.syncfusion.com/kb/13806/how-to-automatically-scroll-to-bring-the-selected-item-into-the-view-in-net-maui-listview)**

## Requirements to run the demo

* [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/) or [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)
* Xamarin add-ons for Visual Studio (available via the Visual Studio installer).

## Troubleshooting

### Path too long exception

If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.