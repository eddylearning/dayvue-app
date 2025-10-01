<template>
  <section class="about">
    <div class="about-content">
      <h2>About Us</h2>
      <p>
        We are a passionate team dedicated to delivering modern and responsive
        digital solutions. Our mission is to create experiences that empower
        people and businesses to achieve more.
      </p>
    </div>
  </section>
</template>

<script lang="ts">
export default {
  name: "AboutView",
};
</script>

<style scoped>
.about {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 80vh;
  padding: 40px 20px;
  background: #f9f9f9;
  color: #333;
  text-align: center;
}

.about-content {
  max-width: 700px;
}

.about h2 {
  font-size: 32px;
  margin-bottom: 20px;
  color: #42b983;
}

.about p {
  font-size: 18px;
  line-height: 1.6;
}
</style>
