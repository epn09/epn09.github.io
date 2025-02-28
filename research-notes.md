---
layout: home
title: "Notes"
permalink: /research-notes/
---

# Research Notes

Some notes on how to do certain things.

{% for note in site.research_notes %}
1. [{{ note.title }}]({{ note.url }})
{% endfor %}
