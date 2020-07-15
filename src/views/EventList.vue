<template>
  <div class="event-header">
    <h1 class="title">Merch</h1>
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
import EventCard from "@/components/EventCard.vue";
import EventService from "@/services/EventService.js";

export default {
  components: {
    EventCard
  },
  data() {
    return {
      events: []
    };
  },
  created() {
    EventService.getEvents()
      .then(response => {
        this.events = response.data;
      })
      .catch(error => {
        console.log("There was an error:", error.response);
      });
  }
};
</script>
<style scoped>
.event-header > .title {
  font-family: "Montserrat", sans-serif;
  font-weight: 700;
  font-size: 2.5em;
  color: #53708b;
  text-decoration: none;
}
</style>
