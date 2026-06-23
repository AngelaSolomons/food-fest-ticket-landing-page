
<!-- Template -->

<template>
  <div
    class="ticket-card"
    :class="{ featured: ticket.featured }"
  >
    <span
      v-if="ticket.featured"
      class="badge"
    >
      Featured
    </span>

    <h2>{{ ticket.name }}</h2>

    <h3>{{ displayPrice }}</h3>

    <ul>
      <li
        v-for="benefit in ticket.benefits"
        :key="benefit"
      >
        {{ benefit }}
      </li>
    </ul>

    <button @click="toggleFavourite">
      {{ isFavourite ? '❤️' : '🤍' }}
    </button>
  </div>
</template>


<!-- Script -->


<script setup>
import { ref, computed } from 'vue'

const props = defineProps({
  ticket: Object
})

const isFavourite = ref(false)
const favouriteCount = ref(0)

const displayPrice = computed(() => {
  return `R${props.ticket.price}`
})

const toggleFavourite = () => {

  if (!isFavourite.value) {
    favouriteCount.value++
  } else {
    favouriteCount.value--
  }

  isFavourite.value = !isFavourite.value
}
</script>


<!-- Style -->


<style scoped>
.ticket-card {
  background: white;

  border-radius: 16px;

  padding: 2rem;

  box-shadow:
    0 10px 30px rgba(0,0,0,0.1);

  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease;

  position: relative;
}

.ticket-card:hover {
  transform: translateY(-8px);

  box-shadow:
    0 15px 40px rgba(0,0,0,0.15);
}

.featured {
  border: 4px solid #FF630F;

  transform: scale(1.05);

  background:
    linear-gradient(
      to bottom,
      #fff,
      #fff9f5
    );
}

.badge {
  position: absolute;

  top: 15px;
  right: 15px;

  background: #FF630F;

  color: white;

  padding: 8px 14px;

  border-radius: 50px;

  font-size: 0.8rem;

  font-weight: bold;
}

h2 {
  margin-bottom: 1rem;
  color: #222;
}

h3 {
  color: #FF630F;

  font-size: 2rem;

  margin-bottom: 1rem;
}

ul {
    list-style: none;
    padding-left: 0;
    margin-bottom: 1.5rem;
}

li {
  margin-bottom: 0.75rem;
}

button {
  width: 100%;

  padding: 12px;

  border: none;

  border-radius: 10px;

  background: #61ABE4;

  color: white;

  font-size: 1rem;

  cursor: pointer;

  transition: 0.3s;
}

button:hover {
  background: #3e92d4;
}
</style>