```eval_rst
.. include:: /header.rst 
:github_url: |github_link_base|/widgets/roller.md
```
# Roller (lv_roller)

## Overview

Roller allows you to simply select one option from more with scrolling. 

## Parts and Styles
- `LV_PART_MAIN` The background of the roller that uses all the typical background properties and the text style properties. `style_text_line_space` adjusts the space between the options. 
When the Roller is scrolled and doesn't stop exactly on an option it will scroll to the nearest valid option automatically in `anim_time` milliseconds as it's specified in the style.
- `LV_PART_SELECTED` The selected option in the middle. Besides the typical background properties it uses the text style properties to change the appearance of the text in the selected area.

## Usage

### Set options
The options are passed to the Roller as a string with `lv_roller_set_options(roller, options, LV_ROLLER_MODE_NORMAL/INFINITE)`. The options should be separated by `\n`. For example: `"First\nSecond\nThird"`.

`LV_ROLLER_MODE_INFINITE` make the roller circular.

You can select an option manually with `lv_roller_set_selected(roller, id, LV_ANIM_ON/OFF)`, where *id* is the index of an option.

### Get selected option
The get the currently selected option use `lv_roller_get_selected(roller)` it will return the *index* of the selected option.

`lv_roller_get_selected_str(roller, buf, buf_size)` copy the name of the selected option to `buf`.

### Visible rows
The number of visible rows can be adjusted with `lv_roller_set_visible_row_count(roller, num)`

## Events
- `LV_EVENT_VALUE_CHANGED` Sent when a new option is selected.

Learn more about [Events](/overview/event).

## Keys
- `LV_KEY_RIGHT/DOWN` Select the next option
- `LV_KEY_LEFT/UP` Select the previous option
- `LY_KEY_ENTER` Apply the selected option (Send `LV_EVENT_VALUE_CHANGED` event) 

## Example

```eval_rst

.. include:: ../../../examples/widgets/roller/index.rst

```

## API 

```eval_rst

.. doxygenfile:: lv_roller.h
  :project: lvgl
        
```
