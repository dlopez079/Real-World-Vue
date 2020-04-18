/* eslint-disable */
<template>
  <div>
    <h1>Events Listings</h1>
    <EventCard></EventCard>
  </div>
</template>

<script>
import EventCard from "../components/EventCard";
import axios from "axios";
export default {
  components: { EventCard: EventCard },
  data() {
    return {
      events: [],
    };
  },
  created() {
    axios
      .get("http://localhost:3000/events")
      .then((response) => {
        this.events = response.data;
      })
      .catch((error) => {
        console.log("There was an error:", error.response);
      });
  },
};
</script>
