---
title: Agenda
summary: Événements passés et à venir.
date: "2020-12-09T00:00:00Z"

reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?

# Optional header image (relative to `static/media/` folder).
header:
  caption: ""
  image: ""
---

<style>
  table {
    display: table;
    margin-bottom: 0;
  }
  #calendar {
    font-size: 0.7em;
  }
</style>

<div id="calendar-loading" style="display:none;"></div>
<div id="calendar"></div>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fullcalendar@5.4.0/main.min.css" integrity="sha256-uq9PNlMzB+1h01Ij9cx7zeE2OR2pLAfRw3uUUOOPKdA=" crossorigin="anonymous">
<script src="https://cdn.jsdelivr.net/npm/fullcalendar@5.4.0/main.min.js" integrity="sha256-oenhI3DRqaPoTMAVBBzQUjOKPEdbdFFtTCNIosGwro0=" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/fullcalendar@5.4.0/locales-all.min.js" integrity="sha256-o+Kyw2gfzvG9f4D8cJQ6Ffkt6ZroHCNbjGUHH9qwnxE=" crossorigin="anonymous"></script>

<script type="text/javascript">
  document.addEventListener('DOMContentLoaded', function() {
    var calendarEl = document.getElementById('calendar');
    var calendar = new FullCalendar.Calendar(calendarEl, {
      locale: 'fr',
      timeZone: 'Europe/Paris',
      nowIndicator: true,
      editable: false,
      navLinks: true,
      eventLimit: true,
      weekNumbers: true,
      fixedWeekCount: false,
      slotMinTime: '07:00:00',
      slotMaxTime: '21:00:00',
      businessHours: {
        daysOfWeek: [ 1, 2, 3, 4, 5 ], // lundi - vendredi
        startTime: '08:00',
        endTime: '20:00'
      },
      // tooltip : nécessite Bootstrap (+ Popper)
      //eventDidMount: function(info) {
      //  $(info.el).tooltip({
      //    title: info.event.extendedProps.description,
      //    placement: "top",
      //    trigger: "hover",
      //    container: "body"
      //  });
      //},
      events: [
        {
          "id": "1",
          "title": "Écriture scientifique et veille bibliographique",
          "allDay": false,
          "start": "2020-10-09T15:30:00",
          "end": "2020-10-09T17:00:00",
          "url": "",
          "extendedProps": {
              "category": "Discussion"
            },
          "description": "LaTeX, Markdown, RSS"
        },
        {
          "id": "2",
          "title": "Traitement d'image",
          "allDay": false,
          "start": "2020-10-20T15:30:00",
          "end": "2020-10-20T17:00:00",
          "url": "",
          "extendedProps": {
              "category": "Discussion"
            },
          "description": "ImageJ, Gimp..."
        },
        {
          "id": "3",
          "title": "Introduction à QGIS",
          "allDay": "false",
          "start": "2020-11-12T14:00:00",
          "end": "2020-11-12T17:00:00",
          "url": "",
          "extendedProps": {
              "category": "Atelier"
            },
          "description": "SIG, QGIS"
        },
        {
          "id": "4",
          "title": "Introduction à R",
          "allDay": "false",
          "start": "2021-02-05T14:00:00",
          "end": "2021-02-05T17:00:00",
          "url": "",
          "extendedProps": {
              "category": "Atelier"
            },
          "description": "R"
        }
      ],
      initialView: 'listYear',
      headerToolbar: {
        start: 'prevYear,prev,next,nextYear today',
        center: 'title',
        end: 'listYear,dayGridMonth,timeGridWeek'
      },
      loading: function(bool) {
        if (bool) $('#calendar-loading').show();
        else $('#calendar-loading').hide();
      },
    });
    calendar.render();
  });
</script>
