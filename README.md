# Timeline - Custom Visualization app

This app is a customization of the Timeline - Custom Visualization app.

Splunkbase URL : https://splunkbase.splunk.com/app/3120/

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Customization Details

The FDSE Team @ Splunk came up with the following augmentations to provide additional functionality to the app. Below are the modifications:

1. Axis Labels and Tooltip Labels contain 3 additional options:
    * YYYY-mm-dd HH:MM:SS (%Y-%m-%d %H:%M:%S)
    * YYYY-mm-dd (%Y-%m-%d)
    * Ability to add any strftime variables in a text box.
2. The mouseover popup displays more than columns two and three of the underlying search.
3. Provided users the ability, on a dashboard, to have the time range be dictated by the time picker and the underlying _time in the search.

### Solution #1

1. Download and install the app and navigate to the Timeline Gallery page.
2. Edit the dashboard > Click on Format > Select Time format.
3. Notice options 1.a and 1.b in both axis and tooltip dropdowns.
4. Notice option 1.c, the date/time format override, in text boxes below the dropdowns (If the typed value is invalid, the box will turn red).

### Solution #2

1. Navigate to the Timeline Gallery page.
2. Hover over each timeline marker to view the tooltips with additional fields.
3. Syntax : 
```
... | table _time <resource_field> [<color_field>] [<duration_field>] [<additional fields>]
```

### Solution #3

1. Navigate to the Timeline Custom page (from the navigation bar).
2. Edit the dashboard > Click on Format > Select the "Time reference” Option.
3. Choose the time range for the specific chart (dataset or picker).
    * Dataset : This option would ensure the labels on the visualization are driven by the _time variable within the dataset.
    * Picker : This option would ensure the labels on the visualization are driven by the time range picker token that the visualization is dependent on.
4. By selecting other intervals with the Time Picker, check the timeline viz changing accordingly.
5. Syntax : 
```
... | table _time <resource_field> [<color_field>] [<duration_field>] [<n_additional_fields>] [$<time_range_picker_token>.earliest$]
```
6. IMPORTANT TO NOTE : 
    * The duration, if specified, might expand the visualization into the “future”.
    * For the time being, custom Timeline visualizations driven by a time range picker, is only supported within a dashboard and cannot be implemented in an independent search window.

## Contributors

* **Erica Pescio** 
* **Karthika Krishnan**
* **Joe Welsh** 
* **Mayur Pipaliya** 
* **Sandeep Vasani** 

## EOF 

* **:heart: it?** Tweet here : [`@splunk`](https://twitter.com/splunk) or email us at [`fdse [@] s p l u n k {.} C O M`](mailto:fdse@splunk.com?subject=[Splunk-CustomTimelineApp]%20Hi%20there!).

* Want to **contribute**? Great! Feel free to create a [PR](https://github.com/welshSplunker/timeline_app/pulls).

* **Found a bug?** [Open an issue](https://github.com/welshSplunker/timeline_app/issues/new)
