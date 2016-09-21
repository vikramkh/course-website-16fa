---
layout: default
title: Lectures
active_tab: lectures
---

<!-- Create a HTML anchor for the most recent lecture -->
{% assign anchor_created = false %}
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
<!-- End create a HTML anchor for the most recent lecture -->

The lecture schedule is subject to change as the term progresses.

<table class="table table-striped"> 
  <thead>
    <tr>
      <th>Date</th>
      <th>Topic</th>
      <th>Required Readings</th>
    </tr>
  </thead>
  <tbody>
    {% for lecture in site.data.lectures %}

    <!-- Create a HTML anchor for the most recent lecture -->
    {% capture lecture_date %}{{lecture.date | date: '%s'}}{% endcapture %}
    {% assign lecture_date = lecture_date | plus: 0 %}
    {% assign now = now | minus: 14400 %}

    <tr
    {% if anchor_created != true and lecture_date >= now %}
      {% assign anchor_created = true %}
      id="now" 
    {% endif %}
    
    {% if lecture.type %}
      {% if lecture.type and lecture.type == 'exam' %}
        class="info" 
      {% else if lecture.type and lecture.type == 'deadline' %}
        class="warning"
      {% else if lecture.type and lecture.type == 'no_lecture' %}
        class="success"
      {% endif %}
    {% endif %}
    >

    <!-- End create a HTML anchor for the most recent lecture -->
      <td>{{ lecture.date | date: '%a, %b %-d, %Y' }}</td>
      <td>
        {% if lecture.slides %}
          <a href="{{ lecture.slides }}">{{ lecture.title }}</a>
        {% else %}
          {{ lecture.title }}
        {% endif %}



	    {% if lecture.speaker %}
          {% if lecture.speaker_url %}
            by <a href="{{ lecture.speaker_url }}">{{ lecture.speaker }}</a>
          {% else %} 
          by {{ lecture.speaker }}
          {% endif %}
	    {% endif %}

	    {% if lecture.highlights %}
	      <ul>
	      {% for highlight in lecture.highlights %}	
	      <span class="text-muted"><li>{{ highlight }}</li></span>
	      {% endfor %}
	      </ul>
	    {% endif %}
        {% if lecture.chalk_talk %}
	      In class notes on  <a href="{{ lecture.chalk_talk }}">{{ lecture.chalk_talk_title }}</a>
        {% endif %}
      </td>
      <td>
        {% if lecture.reading %}
          <ul class="fa-ul">
          {% for reading in lecture.reading %}
            <li>
            {% if reading.optional %}<i class="fa-li fa fa-star"> </i>
            {% else %}<i class="fa-li fa"> </i> {% endif %}
            {% if reading.url %}
            <a href="{{ reading.url }}">{{ reading.title }}</a>
            {% else %}
            {{ reading.title }} 
            {% endif %}
	        {% if reading.author %}
              by {{ reading.author }}
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

