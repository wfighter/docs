=================
CandleStickSeries
=================

.. note:: This section is under construction. Please contribute!

A ``CandleStickSeries`` shows a set of points. The points can also have
a size and color value.

.. image:: CandleStickSeries.png


Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the x-axis
- ``{2}`` the x-value
- ``{3}`` the high value
- ``{4}`` the low value
- ``{5}`` the open value
- ``{6}`` the close value
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended
   format string syntax)

To show the close value with one digit, use the format string
``"{6:0.0}"``.

The default format string for ``CandleStickSeries`` is
``"{0}\n{1}: {2}\nHigh: {3:0.###}\nLow: {4:0.###}\nOpen: {5:0.###}\nClose: {6:0.###}"``


Example
-------

.. sourcecode:: csharp

    var model = new PlotModel{ Title = "CandleStickSeries", LegendSymbolLength = 24 };
    var s1 = new CandleStickSeries 
    {
        Title = "series 1",
        Color = OxyColors.Black
    };

    s1.Items.Add(new HighLowItem { X = 0, High = 12, Low = 10, Open = 11, Close = 10.5 });
    s1.Items.Add(new HighLowItem { X = 1, High = 22, Low = 10, Open = 11, Close = 20.5 });
    s1.Items.Add(new HighLowItem { X = 2, High = 32, Low = 15, Open = 27, Close = 30.5 });
    s1.Items.Add(new HighLowItem { X = 3, High = 22, Low = 13, Open = 15, Close = 18.5 });
    s1.Items.Add(new HighLowItem { X = 4, High = 52, Low = 30, Open = 33, Close = 30.5 });

    model.Series.Add(s1);
    model.Axes.Add(new LinearAxis{ MaximumPadding = 0.3, MinimumPadding = 0.3,Position = AxisPosition.Left  });

