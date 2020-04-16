/* eslint-disable */ 
<template>
	<div>
		<h1>Events Listings</h1>
		<EventCard></EventCard>
		<p>
			<router-link :to="{ name: 'event-show', params: { id: '1' } }">First Event</router-link>
		</p>
	</div>
</template>

<script>
import EventCard from "../components/EventCard";
export default { components: { EventCard: EventCard } };
</script>

