<template>
  <div class="event-header">
    <h1>Merch</h1>
    <h5>All profits go to the following:</h5>
    <ul>
      <li>80% Community Fund</li>
      <li>10% freeCodeCamp.org</li>
      <li>5% Mentors Fund</li>
      <li>5% Code.Sydney's Opex</li>
    </ul>
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
  color: #245e94;
  text-align: center;
  text-decoration: none;
}
.event-header > h1 {
  font-family: "Montserrat", sans-serif;
  color: #1b4c79;
}

.event-header > h5 {
  font-family: "Montserrat", sans-serif;
  color: #1b4c79;
  margin-bottom: 1px;
}

.event-header > ul {
  font-family: "Montserrat", sans-serif;
  color: #1b4c79;
}
</style>
