# How-to-maintain-a-particular-interval-on-axes-while-zooming-WPF-chart
This sample demonstrate how to maintain a particular interval on axes while zooming WPF chart.

To maintain a specific interval on the axis while zooming a WPF Chart, you can use the EnableAutoIntervalOnZooming property of the chart axis and set it to false.

Additionally, you can add the ChartZoomPanBehavior to the charts’ behavior collection and set the desired interval (in this case, 5) on the axis. This will ensure that the axis interval remains consistent during zoom operations. 

The following code sample demonstrates this implementation.

**[XAML]**

```
<chart:SfChart>

    <chart:SfChart.Behaviors>
        <chart:ChartZoomPanBehavior />
    </chart:SfChart.Behaviors>
            
    <chart:SfChart.PrimaryAxis>
        <chart:NumericalAxis Interval="5" EnableAutoIntervalOnZooming="False"/>
    </chart:SfChart.PrimaryAxis>

    <chart:SfChart.SecondaryAxis>
        <chart:NumericalAxis />
    </chart:SfChart.SecondaryAxis>

    <chart:ColumnSeries ItemsSource="{Binding Data}"
                        XBindingPath="XValue"
                        YBindingPath="YValue"/>
</chart:SfChart>

```
## Output:

Before zooming, the x-axis interval is 5, and the y-axis interval is 20.
![Before zooming a WPF Chart](https://user-images.githubusercontent.com/61832185/214261220-787f7eef-57b9-4c86-9c0d-823382411e42.png)

After zooming, the x-axis maintains the same interval, but the y-axis interval has changed.
![Maintain a particular interval on axes while zooming WPF Chart](https://user-images.githubusercontent.com/61832185/214261239-f249591f-457f-463f-a810-ccab391ae90d.png)

## <a name="troubleshooting"></a>Troubleshooting ##
### Path too long exception
If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.