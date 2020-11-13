---
layout: default
title: Tattoos
permalink: tattoos
description: A collection of tattoos that I&#039;ve created and applied over the years.
---
{% for i in (1..32) %}
![Photo of a Tattoo](/images/tattoos/{{ i }}.jpg){:loading="lazy"}
{% endfor %}

