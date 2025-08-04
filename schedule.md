---
layout: page
title: "&#x1f5d3; Schedule"
description: The weekly event schedule.
nav_order: 2
---

# **Weekly Schedule**

{% for schedule in site.schedules %}
{{ schedule }}
{% endfor %}
