---
layout: default
title: CIS 121 Lectures
active_tab: lectures
---

Subject to change as the term progresses.

<table class="table table-striped">
  <tbody>
    <tr>
      <th>Date</th>
      <th>Topic</th>
      <th>Readings</th>
    </tr>
    {% for lecture in site.data.lectures %}
      <tr>
        <td>{{ lecture.date | date: "%b %d" }}</td>
        <td>
          {% if lecture.profile %}
            Company Profile:
          {% endif %}
          {% if lecture.slides %}
            <a href="{{ lecture.slides }}">{{ lecture.title | markdownify }}</a>
          {% else %}
            {{ lecture.title | markdownify }}
          {% endif %}
          {% if lecture.speaker %}
            {% if lecture.speaker_url %} by <a href="{{ lecture.speaker_url }}">{{ lecture.speaker }}</a>
            {% else %}
              by {{ lecture.speaker }}
            {% endif %}
          {% endif %}
          {% if lecture.highlights %}
            <ul>
              {% for highlight in lecture.highlights %}
                <li class="text-muted">
                  {% if highlight.topic %}
                    <a href="{{ highlight.link }}">{{ highlight.topic }}</a>
                  {% else %}
                    {{ highlight }}
                  {% endif %}
                </li>
              {% endfor %}
            </ul>
          {% endif %}
        </td>
        <td>
          {% if lecture.reading %}
            <ul>
              {% for reading in lecture.reading %}
                <li>
                  {% if reading.topic %}
                    {% if reading.link %}
                      <a href="{{ reading.link }}">{{ reading.topic }}</a>
                    {% else %}
                      {{ reading.topic }}
                    {% endif %}
                    {% if reading.author %}
                      by {{ reading.author }}
                    {% endif %}
                    {% if reading.optional %}
                      (optional)
                    {% endif %}
                  {% else %}
                    {{ reading | markdownify }}
                  {% endif %}
                </li>
              {% endfor %}
            </ul>
          {% endif %}
        </td>
      </tr>
    {% endfor %}
  </tbody>
</table>
