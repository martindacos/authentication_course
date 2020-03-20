<template>
  <div>
    <h1>Ofertas de Trabajo</h1>
    <template v-if="events !== 'Cargando ofertas...'">
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
    return { events: 'Cargando ofertas...' }
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
