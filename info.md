{% if prerelease %}
## **This is a pre-release version!**
{% endif %}

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs) 

# Custom brand icons
Akentner icons for Home Assistant


# Install

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

# Use
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

A system restart is required after this step
