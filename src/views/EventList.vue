<template>
  <div class="events">
    <EventCard v-for="event in events" v-bind:key="event.id" v-bind:event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from '@/components/EventCard.vue';
import axios from 'axios';

export default {
  name: 'EventList',
  components: {
    EventCard
  },
  data() {
    return {
      events: null
    }
  },
  created() {
    axios.get(
      "https://my-json-server.typicode.com/Code-Pop/Real-World_Vue-3/events"
    )
    .then(response => {
      console.log("events", response.data)
    })
    .catch(error => {
      console.log(error);
    })
  }
};
</script>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
