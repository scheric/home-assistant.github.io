---
layout: page
title: "iFrame Card"
sidebar_label: iFrame
description: "Iframe cards are useful to embed outside websites in your dashboard with little effort. One such example is a grafana view."
date: 2018-07-01 10:28 +00:00
sidebar: true
comments: false
sharing: true
footer: true
---

Iframe cards are useful to embed outside websites in your dashboard with little effort. One such example is a grafana view. You can also embed files stored in your `config/www` folder and reference them using `/local/<file>`.

<p class='img'>
<img width="500" src='/images/lovelace/lovelace_iframe.png' alt='Screenshot of the iframe card'>
Screenshot of the iframe card.
</p>

> Make sure the URL you're embedding has the right protocol and allows to be embedded in an iframe on a different domain. For example if your Home Assistant setup uses https you won't be able to embed http URLs

{% linkable_title Options %}

{% configuration %}
type:
  required: true
  description: iframe
  type: string
url:
  required: true
  description: iframe source url
  type: string
aspect_ratio:
  required: false
  description: Iframe height-width-ratio
  type: string
  default: "50%"
title:
  required: false
  description: Card title
  type: string
  default: none
{% endconfiguration %}

{% linkable_title Examples %}

```yaml
      - type: iframe
        url: https://worldpingdemo.grafana.net/d/000000027/worldping-endpoint-summary?var-endpoint=www_amazon_com&var-probe=All&panelId=2&fullscreen&orgId=3&theme=light
        aspect_ratio: 100%
```

Local html for custom content. Place `example.html` in your `config/www` folder and reference it as below:
```yaml
      - type: iframe
        url: /local/example.html
        title: Sample local file
```
