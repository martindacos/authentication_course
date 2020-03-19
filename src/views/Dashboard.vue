<template>
  <div>
    <h1>Dashboard</h1>
    <template v-if="events !== 'Loading events...'">
      <EventCard v-for="event in events" :key="event.id" :event="event" />
    </template>
  </div>
</template>

<script>
import axios from 'axios'
import EventCard from '../components/EventCard'

export default {
  components: { EventCard },
  data () {
    return { events: 'Loading events...' }
  },
  created () {
    axios
      .get('//localhost:8082/offers/list')
      .then(response => {
        console.log(response)
        this.events = response.data
      })
  }
}
</script>
