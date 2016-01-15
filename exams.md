---
layout: default
title: CIS 121 Exams
active_tab: exams
---

<table class="table table-striped">
  <tbody>
    <tr>
      <th></th>
      <th>Exam Date</th>
      <th>Exam Location</th>
      <th>Exam Review Date</th>
      <th>Practice Problems</th>
    </tr>
    {% for exam in site.data.exams %}
      <tr style="text-align: left">
        <!-- Homework Name -->
        <td><span>{{ exam.assignment }}</span></td>
        <!-- Dates -->
        <td>{{ exam.exam_date | date: "%b %d" }}</td>
        <td>{{ exam.exam_location }}</td>
        <td>{{ exam.review_date | date: "%b %d" }}</td>
        <!-- Materials -->
        <td>
          <ul class="list-unstyled">
            {% if exam.active %}
              {% if exam.writeup %}<li><a href="{{ exam.writeup }}">Write-up</a></li>{% endif %}
              {% if exam.zip %}<li><a href="{{ exam.zip }}">Files (zip)</a></li>{% endif %}
              {% if exam.problem_set %}<li><a href="{{ exam.problem_set }}">Problem set</a></li>{% endif %}
              {% if exam.problem_set_zip %}<li><a href="{{ exam.problem_set_zip }}">Problem set (zip)</a></li>{% endif %}
              {% if exam.problem_set_tex %}<li><a href="{{ exam.problem_set_tex }}">Problem set (tex)</a></li>{% endif %}
            {% else %}
               <li>Coming soon!</li>
            {% endif %}
          </ul>
        </td>

      </tr>
    {% endfor %}
  </tbody>
</table>
