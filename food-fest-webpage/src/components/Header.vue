<template>
  <header class="hero">
    <h1>Food Fest 2026</h1>

    <p>
      <span class="p-container">
      Experience amazing food, live entertainment,
      and unforgettable memories.
      </span>
    </p>
  </header>
</template>

<style scoped>
.hero {
    min-height: 65vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    color: white;
    padding: 2rem;
    background:
        linear-gradient(rgba(0, 0, 0, 0.6),
            rgba(0, 0, 0, 0.6)),
        url('../assets/hero-img.jpg');

    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
}

.hero h1 {
    font-size: 4rem;
    margin-bottom: 1rem;
    text-shadow: 2px 2px 10px black;
}

.hero p {
    max-width: 700px;
    font-size: 1.3rem;
    line-height: 1.8;
}
</style>