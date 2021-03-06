---
layout: post
title: Getting Started | ColorPicker  | ASP.NET MVC | Syncfusion
description: getting started
platform: ejmvc
control: ColorPicker
documentation: ug
---

# Getting Started

This section explains briefly about how to create a ColorPicker in your application with, ASP.NET MVC.

## Create your first ColorPicker in ASP.NET MVC

The Essential ASP.NET MVCColorPicker control provides support for selecting the colors in different sources such as palettes, picker or custom palettes. You can also render the color value from control in three formats such as RGB, HSV and HEXCODE. 

In this example, you can learn how to customize ColorPicker control in a category Application. 

![](Getting-Started_images/Getting-Started_img1.png)

ColorPicker Control
{:.caption}

In the following sections you can learn, How to:

* Create ColorPicker control
* Initialize the other widgets
* Add Value to ListBox Control

### Create ColorPicker Control

Use the following steps to create the ColorPicker control.

1. You can create a MVC Project and add necessary Dll’s and Scripts with the help of the given [MVC-Getting Started](https://help.syncfusion.com/aspnetmvc/getting-started) Documentation.
2. Add the following code example to the corresponding view page for rendering the ColorPicker window.

   ~~~ cshtml

		@Html.EJ().ColorPicker("CategoryColor").Value("#278787")

   ~~~
 

3. Run this code to render the resultant output of the above steps.

![](Getting-Started_images/Getting-Started_img2.png)



### Initialize the other widgets

To add the priority value to the ListBox, the text value is obtained from the input element and color for each priority is received by ColorPicker control. To add each new priority value to ListBox control, click the Add button.

You can refer to the following link for more information on creation on ListBox

<http://help.syncfusion.com>



1. The following code example is used to create the Priority form using ListBox control and ColorPicker control.

   ~~~ html



		<div class="content-container-fluid">

				<div class="row">

					<div class="sample-area">

						<div class="frame">

							<div id="control">

								<ul id="ColorValues">

									<li><span class="color high"></span>High</li>

									<li><span class="color normal"></span>Normal</li>

									<li><span class="color low"></span>Low</li>

								</ul>

								@Html.EJ().ListBox("selectPriority").TargetID("ColorValues")

							</div>

						</div>

					</div>

					<div id="Properties">

						<table class="prop-grid">

							<tr class="row">

								<td class="column">Name

								</td>

								<td class="column">

									<input type="text" id="categoryName" />

								</td>

							</tr>

							<tr class="row">

								<td class="column">Color

								</td>

								<td class="column">

									<!--Colorpicker element-->

									@Html.EJ().ColorPicker("CategoryColor").Value("#278787")

								</td>

								<td class="column">

									<!--Add button for add the new category-->                                @Html.EJ().Button("AddCategory").Text("Add").Width("82px").Height("28px").Type(ButtonType.Button).ClientSideEvents(events => events.Click("addCategoryValue"))

								</td>

							</tr>

							<tr class="row">

							</tr>

						</table>

					</div>

				</div>

			</div>

   ~~~
 

2. Add the following style section to align form fields. 

   ~~~ css

		<style>

			.content-container-fluid > .row {

				width: 410px;

				border: 1px solid #bbbcbb;

				padding: 16px;

			}



			.color.high {

				background-color: red;

			}



			.color.normal {

				background-color: green;

			}



			.color.low {

				background-color: blue;

			}



			.sample-area {

				width: 205px;

			}



			.sample-area, #Properties {

				display: inline-block;

				float: left;

			}



			#Properties #categoryName {

				width: 140px;

				height: 20px;

			}



			#Properties .column {

				display: inline-block;

				width: 45px;

				margin: 10px 0 0;

			}



			#Properties .row {

				padding: 10px 0px 5px 0px;

			}



			.color {

				width: 13px;

				height: 13px;

				border: 1px solid;

				display: inline-block;

				margin-right: 6px;

				margin-bottom: -3px;

			}

		</style>

   ~~~
 

3. Initialize the element in <script> tag.

   ~~~ js

		<script>

			var listBoxObj, colorObj;

			jQuery(function ($) {

				//initialize the listbox with object creation

				listBoxObj = $("#selectPriority").data('ejListBox');

				//initialize the colorpicker with object creation

				colorObj = $("#CategoryColor").data('ejColorPicker');        

			});

		</script>

   ~~~
 

4. Run the above code to render the following output.



![](Getting-Started_images/Getting-Started_img3.png)

Color Picker control
{:.caption}

### Add value to ListBox Control 

You can add the value to ListBox with selected color by performing the button click event. The following script section define the click event for the button element.

1. Initialize the click event to button element in <script> tag.

   ~~~ js

		<script>

				jQuery(function ($) {

				//reuse the previous section script block            

				 //The following function used to add the new value to the listbox control

				function addCategoryValue() {

					if ($("#categoryName").val() !== "") {

						//To get the selected color from the colorpicker by using getValue()

						listBoxObj.addItem("<span class='color' style='background-color: " + colorObj.getValue() + "' ></span>" + $("#categoryName").val());

						$("#categoryName").val("");

					}

				}

		</script>

   ~~~
 


2. The following screenshot illustrates the resultant output after you click Add button.



![](Getting-Started_images/Getting-Started_img4.png)

Value from Color Picker control
{:.caption}
