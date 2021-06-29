[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs)

# Custom brand icons

Custom brand icons for Home Assistant

![2FA](https://res.cloudinary.com/dcongin7u/image/upload/v1620853194/example_pwvozi.jpg)


At the moment I have integrated only the main icons of Philips Hue products!

 ---
## Animals

| Icon | Name |
|------|:--------------:|
| ![Preview](./icon-svg/snake.svg) | snake |
---

# Install

## HACS

We recommend installing Akentner brand icons card via [Home Assistant Community Store](https://hacs.xyz)
 
 1. Add the folowing to the `frontend` section of your `configuration.yaml`

  ```yaml
frontend:
  extra_module_url:
    - /local/community/hass-akentner-icons/hass-akentner-icons.js
```
2. (optional) Or add the following to your lovelace configuration using the Raw Config editor under Configure UI or ui-lovelace.yaml if using YAML mode.

```yaml
resources:
  - type: js
    url:  /local/community/hass-akentner-icons/hass-akentner-icons.js
```

 ##  Manual Installation

To add custom repositories please follow [this guide](https://hacs.xyz/docs/faq/custom_repositories/). Set URL to `https://github.com/akentner/hass-akentner-icons` and category to `Lovelace`.
1. Download `hass-akentner-icons.js` file from the [latest release](https://github.com/akentner/hass-akentner-icons/releases/latest).
2. Copy the `hass-akentner-icons.js` file into `<config>/www/` the directory where your `configuration.yaml` resides.

3. Add the folowing to the `frontend` section of your `configuration.yaml`

```yaml
frontend:
  extra_module_url:
    - /local/hass-akentner-icons.js
```

Or add the following to your lovelace configuration using the Raw Config editor under Configure UI or ui-lovelace.yaml if using YAML mode.

```yaml
resources:
  - type: js
    url: /local/hass-akentner-icons.js
```

Restart home-assistant.

## Use
you can use icons by entering the prefix `akentner:`

Example of integration in the card

```yaml
entities:
  - entity: light.lampada_entrance
    icon: 'akentner:snake'
    name: Snake
show_header_toggle: false
title: Custom brand icons
type: entities
```
# Customize the prefix

In case you want to create your own perfix you can edit the last line of the `hass-akentner-icons.js`

```js
  window.customIconsets["yourprefix"] = getIcon;
```
# Don't see the icon?

It probably depends on the cache. Open Home assistant from an incognito window and check that the icon loads if yes then it depends on the cache, otherwise double check the installation

# Help me insert more icons!

***Attention I remind you that the icons must be in svg format***

If you like, you can help me expand the number of icons available. Just add to the variable  `var icons`

let's take the first string for example:

```js
"Bollard": [0, 0, 32.0, 32.0, "string"]
```
* `Bollard` = icon name

* `0, 0, 32.0, 32.0` = this data can be recovered from the svg file `transform="scale(0, 0, 32.0, 32.0)` ***If this data is not present in the file you can leave the one indicated by me***

* `String` = this data can be recovered from the svg file  `<path d="M21,12.5 C21,13.33 18.76,...."`

