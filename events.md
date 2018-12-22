---
layout: page
title: Events
permalink: /events/
---

| Name | Masses [Mo] | Spins [Sz/M^2] | Distance [Mpc] | Lambda's | Data |
|---|---|---|---|
{% for e in site.events %}| {{ e.name }} | {{e.masses}} | {{e.spins}} | {{e.distance}} | {{e.lambdas}} | [![Download]({{site.url}}/assets/images/download-from-cloud.png){:height="20px" class="img-responsive"}]({{site.url}}/assets/events/{{ e.name }}/) |
{% endfor %}





