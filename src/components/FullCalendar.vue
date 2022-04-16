<script>
import '@fullcalendar/core/vdom' // Selon la doc c'est important de l'importer en premier car cela règle des problèmes avec Vite
import FullCalendar from '@fullcalendar/vue3'
import dayGridPlugin from '@fullcalendar/daygrid' // sont des vues préconfigurées pour le calendrier
import interactionPlugin from '@fullcalendar/interaction' //Requis pour détecter les actions dateClick, les actions sélectionnables et les événements glisser-déposer et redimensionner.
import frLocale from '@fullcalendar/core/locales/fr'

export default {
  components: {
    FullCalendar, // rend le tag <FullCalendar> disponible à l'import
  },
  data() {
    return {
      calendarOptions: {
        plugins: [dayGridPlugin, interactionPlugin],
        initialView: 'dayGridMonth',
        locale: frLocale,
        headerToolbar: { //modifie le header du calendrier
          left: 'prev next today',
          center: 'title',
          right: 'dayGridMonth dayGridWeek dayGridDay'


        },
        weekends: false, //true -> affiche les weekends
        editable: true,
        selectable: true,
        dateClick: this.handleDateClick,
      },
    }
  },
}
</script>
<template>
  <FullCalendar :options="calendarOptions" />
</template>


