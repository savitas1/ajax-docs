---
title: OnRowHeaderClick
page_title: OnRowHeaderClick | UI for ASP.NET AJAX Documentation
description: OnRowHeaderClick
slug: calendar/client-side-programming/events/onrowheaderclick
tags: onrowheaderclick
published: True
position: 10
---

# OnRowHeaderClick



## 

The __OnRowHeaderClick__ client-side event handler is called when the user is about to select a row of dates by clicking on a row header. The event occurs only if the __ShowRowHeaders__ and __UseRowHeadersAsSelectors__ properties are set to __true__.

>note The __OnRowHeaderClick__ event is supported by: __RadCalendar__ .
>


The event handler receives two arguments:

1. the [RadCalendar object]({%slug calendar/client-side-programming/radcalendar-object%}) that fired the event.

1. an event arguments object that exposes the following methods:OnRowHeaderClick event arguments object


| Name | Return Type | Arguments | Description |
| ------ | ------ | ------ | ------ |
| __get_index()__ |int||Returns the 1-based index of the column that was clicked.|
| __get_domElement()__ |HTML element||Returns the DOM element for the row header that was clicked.|
| __set_cancel(value)__ ||bool|Lets you prevent the click from selecting the row of dates.|

The following example uses the __OnRowHeaderClick__ event to confirm the selection:

````ASPNET
	<script type="text/javascript">
	    function ConfirmRowSelection(sender, eventArgs) {
	        var msg = "Do you want to change the selection for row " + eventArgs.get_index();
	        var title = eventArgs.get_domElement().title;
	        if (title != "")
	            msg = msg + " (" + title + ")";
	        msg = msg + "?";
	        eventArgs.set_cancel(!confirm(msg));
	    }
	</script>
	<telerik:RadCalendar ID="RadCalendar1" runat="server">
	    <ClientEvents OnRowHeaderClick="ConfirmRowSelection" />
	</telerik:RadCalendar>
````



# See Also

 * [OnColumnHeaderClick]({%slug calendar/client-side-programming/events/oncolumnheaderclick%})

 * [OnViewSelectorClick]({%slug calendar/client-side-programming/events/onviewselectorclick%})

 * [OnDateClick]({%slug calendar/client-side-programming/events/ondateclick%})