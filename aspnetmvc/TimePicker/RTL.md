---
layout: post
title: RTL | TimePicker | ASP.NET MVC | Syncfusion
description: rtl
platform: ejmvc
control: TimePicker
documentation: ug
---

# RTL

This feature supports to change the left-to-right alignment of the TimePicker widget to right-to-left when set the EnableRTL as true. By default EnableRTL value is set as “false”. The custom template TimePicker also supports RTL.

## Enabling Right-To-Left Support

The following steps explains you in enabling the right-to-left property for the TimePicker.

1. Add the following code to the corresponding view page to render the TimePicker.   


{% highlight CSHTML %}

@*Add the following code example to the corresponding CSHTML page to render TimePicker widget with right to left appearance*@

@Html.EJ().TimePicker("time").EnableRTL(true)

{% endhighlight %}

The following screenshot illustrates a TimePicker control when EnableRTL is set to “true”



![](RTL_images/RTL_img1.png)

TimePicker template with RTL support
{:.caption}

