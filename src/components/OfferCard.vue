<template>
  <div class="offer-card">
    <h4>{{ event.name }}</h4>
    <span>{{ event.description }} on {{ event.date }}</span>
  </div>
</template>

<script>
export default {
  name: 'OfferCard',
  props: {
    event: {
      type: Object,
      default: () => ({})
    }
  }
}
</script>

<style scoped>
.offer-card {
  width: 13em;
  margin: 1em auto 1em auto;
  padding: 1em;
  border: solid 1px #2c3e50;
  cursor: pointer;
  transition: all 0.2s linear;
}
.offer-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2), 0 1px 15px 0 rgba(0, 0, 0, 0.19);
}
.offer-card h4 {
  font-size: 1.4em;
  margin-top: 0.5em;
  margin-bottom: 0.3em;
}
</style>
