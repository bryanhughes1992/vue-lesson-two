
<template>
  <router-link v-bind:to="{ name: 'EventDetails', params: { id: event.id }}">
    <div class="event-card">
      <!-- Display Event Data -->
      <span>@ {{ event.time }} on {{ event.date }}</span>
      <h4>{{ event.title }}</h4>
      <p><strong>Location:</strong> {{ event.location }}</p>
      <p><strong>Organizer: </strong>{{ event.organizer }}</p>
      <p><strong>Description: </strong>{{ event.description }}</p>
    </div>
  </router-link>
</template>

<script>
export default {
  name: 'EventCard',
  props: {
    event: Object
  }
};
</script>

<style scoped>
.event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}
.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>
