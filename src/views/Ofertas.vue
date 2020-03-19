<template>
  <div>
    <h1>Dashboard</h1>
    <template v-if="events !== 'Loading events...'">
      <OfferCard v-for="event in events" :key="event.id" :event="event" />
    </template>
  </div>
</template>

<script>
import axios from 'axios'
import OfferCard from '../components/OfferCard'

export default {
  components: { OfferCard },
  data () {
    return { events: 'Loading events...' }
  },
  created () {
    axios
      .get('//localhost:8082/offers')
      .then(response => {
        console.log(response)
        this.events = response.data
      })
  }
}
</script>
