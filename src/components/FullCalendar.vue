<script>
import '@fullcalendar/core/vdom' // Selon la doc c'est important de l'importer en premier car cela règle des problèmes avec Vite
import FullCalendar from '@fullcalendar/vue3'
import frLocale from '@fullcalendar/core/locales/fr'
import dayGridPlugin from '@fullcalendar/daygrid' // sont des vues préconfigurées pour le calendrier
import interactionPlugin from '@fullcalendar/interaction' //Requis pour détecter les actions dateClick, les actions sélectionnables et les événements glisser-déposer et redimensionner.
import listPlugin from '@fullcalendar/list' //permet d'important la liste de récupération des évènements

export default {
  components: {
    FullCalendar, // rend le tag <FullCalendar> disponible à l'import
  },
  data() {
    return {
      calendarOptions: {
        plugins: [dayGridPlugin, interactionPlugin, listPlugin], //On importe les plugins ici, sinon ça ne marche pas !
        initialView: 'dayGridMonth',
        locale: frLocale,
        headerToolbar: {
          //modifie le header du calendrier
          left: 'prev next today',
          center: 'title',
          right: 'dayGridMonth,dayGridWeek,dayGridDay,listWeek',
        },
        weekends: true, //true -> affiche les weekends
        weekNumbers: true, //ajoute les numéros des semaines
        editable: true, //permet l'edition des évenements (drag/drop / resize)
        selectable: true, //Permet à un utilisateur de mettre en surbrillance plusieurs jours ou plages horaires en cliquant et en faisant glisser.
        dateClick: function (info) {
          alert('Clicked on: ' + info.dateStr)
          /*
          alert('Coordinates: ' + info.jsEvent.pageX + ',' + info.jsEvent.pageY)
          alert('Current view: ' + info.view.type)
          */
          info.dayEl.style.backgroundColor = 'red' //change le fond d'écran une fois cliqué
        },
        events: [ //test de création d'évenement à la main pour tester le résultat
          { title: 'Pop School', date: '2022-04-04T08:15:00' },
          { title: 'Soutien Pop School', date: '2022-04-06' },
        ],
      },
    }
  },
  methods: { //Gestion des évènements
    handleDateClick: function (arg) { //Fonction qui gère le clic sur la date et affiche une alerte
      alert('date click! ' + arg.dateStr)
    },
  },
}
</script>
<template>
  <FullCalendar :options="calendarOptions" />
</template>
<style></style>
