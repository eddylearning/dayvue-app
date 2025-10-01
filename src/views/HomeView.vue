<template>
  <section class="home">
    <div class="home-content">
      <h1>Vuejs Website</h1>
      <p>
        We build modern, responsive, and scalable web applications. Explore our
        services and learn more about what we can do for you.
      </p>
      <h1 v-if="IsLoggedIn">welcome back</h1>
      <h1 v-else> you are not logged in</h1>
      <a href="/service" class="btn">Explore Services</a>
    </div>
  </section>
</template>

<script lang="ts">
export default {
  name: "HomeView",
  data() {
    return{
      IsLoggedIn: true
    }
  },};

</script>

<style scoped>
.home {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 80vh;
  background: linear-gradient(135deg, #42b983, #2c8a63);
  color: white;
  text-align: center;
  padding: 40px 20px;
}

.home-content {
  max-width: 700px;
}

.home h1 {
  font-size: 42px;
  margin-bottom: 20px;
}

.home p {
  font-size: 18px;
  margin-bottom: 30px;
  line-height: 1.6;
}

.btn {
  display: inline-block;
  padding: 12px 24px;
  background: white;
  color: #42b983;
  font-weight: bold;
  border-radius: 6px;
  text-decoration: none;
  transition: all 0.3s;
}

.btn:hover {
  background: #e0e0e0;
  color: #2c8a63;
}
</style>
