---
layout: default
title: CIS 121 Labs
active_tab: labs
---

<table class="table table-striped">
  <thead>
    <tr>
      <th>Week of</th>
      <th>Name</th>
      <th>Materials</th>
      <th>Solutions</th>
    </tr>
  </thead>
  
  <tbody>
    {% for lab in site.data.labs %}
    
      <tr style="text-align: left">
        <td>{{ lab.date | date: "%b %d" }}</td>
        <td><span>{{ lab.name }}</span></td>
        <td>
          <ul class="list-unstyled">
            {% if lab.problems %}
              {% for problems in lab.problems %}
                {% if problems.link %}
                <li>
                  <a href="{{ problems.link }}">{{ problems.name }}</a>
                </li>
                {% else %}
                <li>
                  {{ problems.name }}
                </li>
                {% endif %}
              {% endfor %}
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
