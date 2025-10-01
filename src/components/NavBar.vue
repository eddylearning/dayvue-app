<template>
  <nav class="navbar">
    <div class="logo">MyWebsite</div>
    <div class="nav-links">
      <a href="#">Home</a>
      <a href="#">About</a>
      <a href="#">Services</a>
      <a href="#">Events</a>
      <a href="#">Contact</a>
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 30px;
  background: #42b983; /* Vue green */
  color: white;
}

.logo {
  font-size: 22px;
  font-weight: bold;
}

.nav-links a {
  margin-left: 20px;
  text-decoration: none;
  color: white;
  font-size: 16px;
  transition: color 0.3s;
}

.nav-links a:hover {
  color: #e0e0e0;
}
</style>
