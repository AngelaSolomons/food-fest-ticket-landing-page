<template>
  <HeaderSection />

  <section class="tickets">
    <TicketCard
      v-for="ticket in tickets"
      :key="ticket.id"
      :ticket="ticket"
    />
  </section>
</template>

<script setup>
import HeaderSection from './components/Header.vue'
import TicketCard from './components/TicketCard.vue'

const tickets = [
  {
    id: 1,
    name: 'General Admission',
    price: 250,
    featured: false,
    benefits: [
      'Food stalls',
      'Live music',
      'Family-zone'
    ]
  },

  {
    id: 2,
    name: 'Travel The World',
    price: 550,
    featured: true,
    benefits: [
      'Priority entry',
      'Get first priority at up to 5 eateries - no waiting!',
      'VIP lounge',
      'Exclusive gift bags'
    ]
  },

  {
    id: 3,
    name: 'Date Night',
    price: 750,
    featured: false,
    benefits: [
      'Entrance for 2',
      'Scenic route',
      'Reservation for any eatery at food fest'
    ]
  }
]
</script>

<style scoped>
.tickets {
  display: grid;
  grid-template-columns:
    repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: auto;
  padding: 4rem 2rem;
}
</style>