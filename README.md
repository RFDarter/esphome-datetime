# esphome-datetime

Adds a datime component to esphome. You will be able to pick a datetime, a date, or a time over the `web_server` frontened and Trigger automations based on the time provided by the user after compile time

This is the basic structure in the yaml config
```
datetime:
  - platform: template
    id: my_time_datetime
    name: Time to turn the switch on
    time_id: my_time
    optimistic: yes
    # valid formats are '%Y-%m-%d %H:%M:%S' - '%Y-%m-%d %H:%M' - '%H:%M:%S' - '%H:%M'
    initial_value: "16:45:20"
    on_time:
      - switch.turn_on:
          id: my_switch
```

`time_id` is needed if you provide an `on_time` automation and can be any time component

```
time:
  - platform: sntp
    id: my_time
```

## Installation
It is not part of esphome at this point and to be able to make it work some core files of esphope had to be changed.
So if you want to try it out you would need to build a custom version of esphome using this Github Fork of esphome
<a href="https://github.com/RFDarter/esphome/tree/Add-input_datetime" target="_blank">
rfdarter-add-input_datetime
</a>

You will also need a modified version of the `esphome-web_server` component, found here
<a href="https://github.com/RFDarter/esphome-webserver/tree/ha-styling-input_datetime-support" target="_blank">
rfdarter-esphome-webserver
</a>

Or simply use the build js file provided <a href="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/www.js" target="_blank">here</a> in this repository


## That's what it will look like on the front end
<a href="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-date-mobile.jpg" target="_blank">
<img src="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-date-mobile.jpg" width="50%">
</a>
<a href="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-date-pc-chrome.jpg" target="_blank">
<img src="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-date-pc-chrome.jpg" width="50%">
</a>
<a href="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-date-pc-ff.jpg" target="_blank">
<img src="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-date-pc-ff.jpg" width="50%">
</a>

<a href="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-datetime-mobile.jpg" target="_blank">
<img src="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-datetime-mobile.jpg" width="50%">
</a>
<a href="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-datetime-pc-chrome.jpg" target="_blank">
<img src="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-datetime-pc-chrome.jpg" width="50%">
</a>
<a href="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-datetime-pc-ff.jpg" target="_blank">
<img src="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-datetime-pc-ff.jpg" width="50%">
</a>

<a href="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-time-mobile.jpg" target="_blank">
<img src="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-time-mobile.jpg" width="50%">
</a>
<a href="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-time-pc-chrome.jpg" target="_blank">
<img src="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-time-pc-chrome.jpg" width="50%">
</a>
<a href="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-time-pc-ff.jpg" target="_blank">
<img src="https://raw.githubusercontent.com/rfdarter/esphome-datetime/main/images/pick-time-pc-ff.jpg" width="50%">
</a>

## Todo
add api support

