---
layout: page  
title: Program
permalink: /program/
---

A list of data entry you want to manage for NIME papers and performances.

# Paper

<!-- weird list layout in markdown versus html. -->
{% for person in site.data.papers %}
- [{{person.full_name}}]({{ person.paper_name | datapage_url: 'program' }}.pdf)
{% endfor %}

 
# Performance (using Hierarchy Example)

<p>If your data is structured in a hierarhcy, specify the path to access your data in the <tt>data</tt> field.</p>

<p>See the file <tt>_data/hierarchy.yml</tt> for a working example.  The pages generated are the following:</p>

{% for person in site.data.hierarchy.people %}
- <a href="{{ person.full_name | datapage_url: 'hierarchy' }}">{{person.full_name}}</a>
    {% endfor %}