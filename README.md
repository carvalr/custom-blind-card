# Blind card

[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg?style=for-the-badge)](https://github.com/custom-components/hacs)

This card allows to open, close or set a blind to the opening rate you want.

![Blind card](https://raw.githubusercontent.com/carvalr/custom-blind-card/master/images/blind-anim.gif)

## Configuration

### General

| Name | Type | Required | Default | Description
| ---- | ---- | -------- | ------- | -----------
| type | string | True | - | Must be "custom:blind-card"
| title | string | False | - | Title of the card

### Entities

| Name | Type | Required | Default | Description
| ---- | ---- | -------- | ------- | -----------
| entity | string | True | - | The blind entity ID
| name | string | False | _Friendly name of the entity_ | Name to display for the blind
| buttons_position | string | False | `left` | Set buttons on `left`, `right`, `top` or `bottom` of the blind
| title_position | string | False | `top` | Set title on `top` or on `bottom` of the blind
| invert_percentage | boolean | False | `false` | Set it to `true` if your blind is 100% when it is closed, and 0% when it is opened
| can_tilt | boolean | False | `false` | Set it to `true` if your blinds support tilting.
| partial_close_percentage | int | False | `0` | Set it to a percentage (0-100) if you want to be able to quickly go to this "partially closed" state using a button.
| offset_closed_percentage | int | False | `0` | Set it to a percentage (0-100) of travel that will still be considered a "closed" state in the visualization.
| always_percentage | boolean | False | `false` | If set to `true`, the end states (opened/closed) will be also as numbers (0 / 100 % ) instead of a text
| blind_width_px | int | False | `153` | Set blind visualization width in px. You can make it thicker or narrower to fit your layout.
| disable_end_buttons | boolean | False | `false` | If set to `true`, the end states (opened/closed) will also deactivate the buttons for that direction (i.e. the "up" button will be disabled when the blinds are fully open)

_Remark : you can also just give the entity ID (without to specify `entity:`) if you don't need to specify the other configurations._

### Sample

```yaml
type: 'custom:blind-card'
title: My blinds
entities:
  - entity: cover.left_living_blind
    name: Left blind
    buttons_position: left
    title_position: bottom
  - cover.bedroom_blind
```

## Install

If you use HACS, the resources will automatically be configured with the needed file.

If you don't use HACS, you can download js file from [latest releases](https://github.com/carvalr/custom-blind-card/releases). Drop it then in `www` folder in your `config` directory. Next add the following entry in lovelace configuration:

```yaml
resources:
  - url: /local/custom-blind-card.js
    type: module
```
