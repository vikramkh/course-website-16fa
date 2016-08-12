---
layout: default
title: CIS 121 Labs
active_tab: labs
---

<table class="table table-striped">
  <tbody>
    
    <tr>
      <th>Week of</th>
      <th>Name</th>
      <th>Materials</th>
      <th>Solutions</th>
    </tr>
    
    {% for lab in site.data.labs %}
    
      <tr style="text-align: left">
        <td>{{ lab.date | date: "%b %d" }}</td>
        <td><span>{{ lab.name }}</span></td>
        <td>
          <ul class="list-unstyled">
            <li>
            {% if lab.problems.link %}}
                <a href="{{ lab.problems.link }}">{{ lab.problems.name }}</a>
            {% else %}
                {{ lab.problems.name }}
            </li>
            {% endif %}
            {% if lab.extra %}
              <li><a href="{{ lab.extra.link }}">{{ lab.extra.name }}</a></li>
            {% endif %}
          </ul>
        </td>
        <td>
          {% if lab.solutions %}
            <a href="{{ lab.solutions }}">Solutions</a>
          {% else %}
            Coming soon!
          {% endif %}
        </td>
      </tr>
    
    {% endfor %}
  
  </tbody>
</table>
