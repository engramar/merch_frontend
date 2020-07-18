<template>
  <div class="event-card -shadow">
    <span class="title">{{ event.stockname }}</span>
    <br />
    <span class="eyebrow">
      <a :href="`${event.spreadshirtlink}`" target="_blank">
        <img :src="require(`@/assets/${event.imagename}`)" alt class="icon" />
      </a>
    </span>
  </div>
</template>

<script>
export default {
  props: {
    event: Object
  }
};
</script>

<style scoped>
.event-card {
  padding: 20px;
  margin-bottom: 24px;
  transition: all 0.2s linear;
  cursor: pointer;
}
.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2), 0 1px 15px 0 rgba(0, 0, 0, 0.19);
}
.event-card > .title {
  margin: 0;
  font-family: "Montserrat", sans-serif;
  font-weight: 700;
  font-size: 1.5em;
  color: #133352;
  text-decoration: none;
}
.event-link {
  color: black;
  text-decoration: none;
  font-weight: 100;
}
</style>
