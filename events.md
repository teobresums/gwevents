---
layout: page
title: Events
permalink: /events/
---

| Event | Parfile | Data | Plot |
|---|---|---|---|
{% for e in site.events %}| {{ e.name }} | [`.*par`]({{site.url}}/assets/events/{{ e.name }}/{{ e.name }}.par) | [`*.tgz`]({{site.url}}/assets/events/{{ e.name }}/waveform.txt.tgz) | [`PNG`]({{site.url}}/assets/events/{{ e.name }}/{{ e.name }}_waveform.png) |
{% endfor %}





