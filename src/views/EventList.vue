/* eslint-disable */
<template>
  <div>
    <h1>Events Listings</h1>
    <EventCard
      v-for="event in events"
      :key="event.id"
      :event="event"
    ></EventCard>
  </div>
</template>

<script>
import EventCard from "../components/EventCard";
import EventService from "../services/EventService.js";

export default {
  components: { EventCard: EventCard },
  data() {
    return {
      events: [],
    };
  },
  created() {
    EventService.getEvents()
      .then((response) => {
        this.events = response.data;
      })
      .catch((error) => {
        console.log("There was an error:", error.response);
      });
  },
};
</script>
