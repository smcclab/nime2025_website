---
layout: page  
title: Program
permalink: /program/
---

# Papers

<!-- weird list layout in markdown versus html. -->
{% for person in site.data.papers %}
- [{{person.full_name}}]({{ person.paper_name | datapage_url: 'program' }}.pdf)
{% endfor %}
