<template>
  <section class="contact">
    <div class="contact-content">
      <h2>Contact Us</h2>
      <form>
        <input type="text" placeholder="Your Name" required />
        <input type="email" placeholder="Your Email" required />
        <textarea placeholder="Your Message" rows="5" required></textarea>
        <button type="submit">Send Message</button>
      </form>
    </div>
  </section>
</template>

<script lang="ts">
export default {
  name: "ContactView",
};
</script>

<style scoped>
.contact {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 80vh;
  padding: 40px 20px;
  background: #f9f9f9;
}

.contact-content {
  max-width: 600px;
  width: 100%;
  text-align: center;
}

.contact h2 {
  font-size: 32px;
  margin-bottom: 20px;
  color: #42b983;
}

form {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

input,
textarea {
  padding: 12px;
  border: 1px solid #ddd;
  border-radius: 6px;
  font-size: 16px;
  width: 100%;
}

button {
  padding: 12px;
  background: #42b983;
  color: white;
  border: none;
  border-radius: 6px;
  font-size: 16px;
  cursor: pointer;
  transition: background 0.3s;
}

button:hover {
  background: #2c8a63;
}
</style>
