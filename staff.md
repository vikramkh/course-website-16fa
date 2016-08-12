---
layout: default
title: CIS 121 Staff
active_tab: staff
---

<div class="container-fluid">
  <div class="row">
  {% for staff in site.data.staff %}
      <div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px; height: 350px;">
        <ul class="list-unstyled">
          <li>
            {% if staff.pic %}
              <img src="assets/img/staff/{{ staff.pic }}" class="img-circle" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px">
            {% else %}
              <img src="assets/img/kermit.png" class="img-circle" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px">
            {% endif %}
          </li>
          <li><b>{{ staff.name }}</b></li>
          {% if staff.extra_title %}<li><em>{{ staff.extra_title }}</em></li>{% endif %}
          <li><code>{{ staff.email }}</code></li>
       	  {% if staff.lab %}<li>Lab: {{ staff.lab | inline_markdownify }}</li>{% endif %}
       	  {% if staff.office_hours %}<li>Office Hours: {{ staff.office_hours | inline_markdownify }}</li>{% endif %}
        </ul>
      </div>
    {% endfor %}
  </div>
</div>
