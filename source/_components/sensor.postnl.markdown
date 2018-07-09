---
layout: page
title: PostNL Sensor
description: "Instructions on how to set up PostNL sensors within Home Assistant."
date: 2017-04-22 08:00
sidebar: true
comments: false
sharing: true
footer: true
logo: postnl.png
ha_category: Sensor
ha_release: 0.69
ha_iot_class: "Cloud Polling"
---

The `postnl` platform allows one to track packeges an letters by [PostNL](https://www.postnl.nl) (Dutch Postal Services). To use this sensor, you need a [PostNL Account](https://jouw.postnl.nl). It is possible to add multiple accounts to your Home Assistant configuration.

The packege sensor value shows the number of packages to be delivered. Each of the packages is available as an attribute.
The letters sensor value shows the number of packages to be deliverd.

## {% linkable_title Configuration %}

To enable this sensor, add the following lines to your `configuration.yaml`:

```yaml
sensor:
  - platform: postnl
    username: POSTNL_USERNAME
    password: POSTNL_PASSWORD
    letter: 
```

{% configuration %}
name:
  description: Sensor name
  required: false
  default: "postnl"
  type: string
username:
  description: Account username of jouw.postnl.nl
  required: true
  type: string
password:
  description: Account password of jouw.postnl.nl
  required: true
  type: string
letter:
  description: Enable ore disable the letters entity
  required: false
  type: boolean
{% endconfiguration %}

<p class='note warning'>
This component is not affiliated with PostNL and retrieves date from the endpoints of the mobile application. Use at your own risk.
</p>
