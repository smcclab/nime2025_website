---
layout: page  
title: Schedule
permalink: /schedule/
---

<h1>People (generated from YAML)</h1>

<ul>
{% for person in site.data.members %}
  <li><a href="{{ person.full_name | datapage_url: 'people' }}">{{person.full_name}}</a></li>
{% endfor %}
</ul>

<h1>Filter Examples (generated from book in YAML)</h1>

<h2>Approach 1: Filter Links, Generate all pages</h2>

<p>In the page <a href="../book.html">books</a>, the books are organized in two lists: books I have read and those I have not.  However a page is still generated for each book. <b>This is not a filter on the pages being generated: it is only a filter on the links being generated.</b></p>

<h2>Approach 2: <tt>filter</tt> keyword</h2>

<p>If the yaml matter has a boolean field (for instance: <tt>filter</tt> or, more evocatively, <tt>publish</tt>), I can specify it in <tt>_config</tt> to select what pages have to be generated.</p>

<h2>Approach 3: <tt>filter_condition</tt> keyword</h2>

<p>I can use the <tt>filter_condition</tt> field in <tt>config.yml</tt>. The field takes as argument a string with ruby expression which should evaluate to a Boolean value.  The <tt>filter_condition</tt> is used as an additional selector on top of the <tt>filter</tt> condition.</p>

<p>See the documentation for more details.</p>

<h1>Hierarchy Example</h1>

<p>If your data is structured in a hierarhcy, specify the path to access your data in the <tt>data</tt> field.</p>

<p>See the file <tt>_data/hierarchy.yml</tt> for a working example.  The pages generated are the following:</p>

<ul>
    {% for person in site.data.hierarchy.people %}
    <li>
        <a href="{{ person.full_name | datapage_url: 'hierarchy' }}">{{person.full_name}}</a>
    </li>
    {% endfor %}
</ul>