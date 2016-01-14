---
layout: default
title: CIS 121 Office Hour Schedule
active_tab: schedule
js_onready: |
  if ($(window).width() < 768) {
    $('#calendar-schedule').attr('src', 'https://www.google.com/calendar/embed?src=6r6upjjvqfjh3rb72bpprpsuos%40group.calendar.google.com&ctz=America/New_York&mode=AGENDA');
  } else {
    $('#calendar-schedule').attr('src', 'https://www.google.com/calendar/embed?src=6r6upjjvqfjh3rb72bpprpsuos%40group.calendar.google.com&ctz=America/New_York');
  }

---
All office hours will be held in Moore 100A.

<div class="embed-responsive embed-responsive-4by3">
  <iframe id="calendar-schedule" class="embed-responsive-item" scrolling="no"></iframe>
</div>
