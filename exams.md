---
layout: default
title: CIS 121 Exams
active_tab: exams
---

All exams will be closed-book and closed-notes.

<table class="table table-striped">
  <thead>
    <tr>
      <th>Name</th>
      <th>Date</th>
      <th>Location</th>
      <th>Information</th>
      <th>Practice Problems</th>
    </tr>
  </thead>
  
  <tbody>
    {% for exam in site.data.exams %}
      <tr style="text-align: left">
        <td><span>{{ exam.assignment }}</span></td>
        <td>{{ exam.exam_date | date: "%a, %b %-d" }}</td>
        <td>
          <ul class="list-unstyled">
            {% if exam.location %}
              {% for loc in exam.location %}
                <li>{{ loc | inline_markdownify }}</li>
              {% endfor %}
            {% else %}
              Coming soon!
            {% endif %}
          </ul>
        </td>
        
        <td>
          <ul class="list-unstyled">
          {% if exam.topics %}
            <li>Topics</li>
              <ul>
              {% for topic in exam.topics %}
                <li>{{ topic }}</li>
              {% endfor %}
              </ul>
          {% endif %}
          </ul>
            
          {% if exam.review %}
            <li>Review session on {{ exam.review.date | date: "%a, %b %-d" }}, {{ exam.review.time | inline_markdownify }} in {{ exam.review.location }}</li>
          {% endif %}
        </td>
        
        <td>
          <ul class="list-unstyled">
            {% if exam.practice and exam.practice.active %}
              <li><a href="{{ exam.practice.problems }}">Practice Problems</a></li>
              {% if exam.practice.solutions %}
                {% for sample_solution in exam.practice.solutions %}
                <li><a href="{{ exam.practice.solutions }}">Sample Solutions</a></li>
                {% endfor %}
              {% endif %}
            {% else %}
              <li>Coming soon!</li>
            {% endif %}
          </ul>
        </td>
      </tr>
    {% endfor %}
    
  </tbody>
</table>
