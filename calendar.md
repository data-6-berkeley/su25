---
layout: page
title: "&#x1f3e0; Home"
description: Listing of course modules and topics.
nav_order: 1
permalink: /
---

# **Data 6: Introduction to Computational Thinking with Data Science and Society &#x1f4ca;**

{: .mb-2 }
UC Berkeley, Summer 2025
{: .mb-2 .fs-6}

[Ed](https://edstem.org/us/courses/80458/discussion){: .btn .btn-ed}
[Gradescope](https://www.gradescope.com/courses/1064926){: .btn .btn-gradescope}
[Lecture Recordings](https://bcourses.berkeley.edu/courses/1546002/external_tools/90481){: .btn .btn-bcourses}
[Jump to Current Week](https://data6.org/su25/#week-5-project-work-and-llms){: .btn .btn-currweek}

## Instructor

{% assign instructors = site.staffers | where: 'role', 'InstructorFront' %}

<div class="role flex">
{% for staffer in instructors %}
{{ staffer }}
{% endfor %}
</div>

{% include announcements-navigation.html %}

{% assign mods = site.modules | where: 'class', 'Berkeley' %}
{% assign active-mods = '' | split: '' %}

{% for mod in mods %}
  {% if mod.status == 'Active' %}
    {% assign active-mods = active-mods | push: mod %}
  {% endif %}
{% endfor %}

{% for module in active-mods %}
  {{ module }}
{% endfor %}

<script src="{{ '/assets/scripts/announcement-navigation.js' | relative_url }}"></script>