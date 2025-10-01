<!-- <template>
  <div class="app">
    <h1 class="title"> Vue App</h1>

    <nav class="navbar">
      <router-link to="/" class="nav-link">Home</router-link>
      <router-link to="/about" class="nav-link">About</router-link>
      <router-link to="/service" class="nav-link">Services</router-link>
      <router-link to="/contact" class="nav-link">Contact</router-link>
    </nav>

    <main class="content">
      <router-view />
    </main>
  </div>
</template>

<script lang="ts">
export default {
  name: "App",
};
</script>

<style scoped>
.app {
  font-family: Arial, Helvetica, sans-serif;
  color: #333;
}

.title {
  text-align: center;
  font-size: 28px;
  font-weight: bold;
  margin: 20px 0;
  color: #42b983;
}

.navbar {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-bottom: 30px;
}

.nav-link {
  text-decoration: none;
  font-size: 18px;
  color: #333;
  padding: 8px 12px;
  border-radius: 4px;
  transition: background 0.3s, color 0.3s;
}

.nav-link:hover {
  background: #42b983;
  color: white;
}

.content {
  padding: 20px;
}
</style> -->


<template>
  <div class="app" :class="currentTheme">
    <h1 class="title">Vue App</h1>

    <nav class="navbar">
      <router-link to="/" class="nav-link">Home</router-link>
      <router-link to="/about" class="nav-link">About</router-link>
      <router-link to="/service" class="nav-link">Services</router-link>
      <router-link to="/contact" class="nav-link">Contact</router-link>
    </nav>

    <div class="theme-switcher">
      <label for="theme">Theme:</label>
      <select v-model="currentTheme" id="theme">
        <option value="light">Light</option>
        <option value="dark">Dark</option>
        <option value="blue">Blue</option>
        <option value="green">Green</option>
        <option value="purple">Purple</option>
      </select>
    </div>

    <main class="content">
      <router-view />
    </main>
  </div>
</template>


<script lang="ts">
export default {
  name: "App",
  data() {
  return {
    currentTheme: 'dark' as 'dark' | 'dark' | 'blue' | 'green' | 'purple',
  };
}

};

</script>

<style scoped>
.app {
  font-family: Arial, Helvetica, sans-serif;
  color: #333;
}

.title {
  text-align: center;
  font-size: 28px;
  font-weight: bold;
  margin: 20px 0;
  color: #42b983;
}

.navbar {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-bottom: 30px;
}

.nav-link {
  text-decoration: none;
  font-size: 18px;
  color: #333;
  padding: 8px 12px;
  border-radius: 4px;
  transition: background 0.3s, color 0.3s;
}

.nav-link:hover {
  background: #42b983;
  color: white;
}

.content {
  padding: 20px;
}
  /*styling for color switch */
.theme-switcher {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  gap: 10px;
}

.theme-switcher label {
  font-size: 16px;
  font-weight: bold;
  color: #555;
}

.theme-switcher select {
  padding: 6px 12px;
  font-size: 15px;
  border: 1px solid #ccc;
  border-radius: 4px;
  outline: none;
  background-color: white;
  color: #333;
  transition: border-color 0.3s, box-shadow 0.3s;
}

.theme-switcher select:focus {
  border-color: #42b983;
  box-shadow: 0 0 5px rgba(66, 185, 131, 0.5);
}


.light {
  background-color: #ffffff;
  color: #333333;
}

.dark {
  background-color: #1e1e1e;
  color: #ffffff;
}

/* .blue {
  background-color: #e0f0ff;
  color: #003366;
} */

/* Blue theme styles */
.blue {
  /* Create a diagonal gradient background from light to darker blues */
  background: linear-gradient(135deg, #cce7ff, #99cfff, #66b8ff, #339fff);

  /* Increase the background size to allow for animated movement */
  background-size: 400% 400%;

  /* Apply a smooth infinite animation to move the gradient */
  animation: gradientMove 10s ease infinite;

  /* Text color that works well on blue background */
  color: #003366;
}

/* Keyframes to animate the gradient background */
@keyframes gradientMove {
  0% {
    background-position: 0% 50%; /* Start from left */
  }
  50% {
    background-position: 100% 50%; /* Move to the right */
  }
  100% {
    background-position: 0% 50%; /* Return to start for looping */
  }
}


.green {
  background-color: #e6f4ea;
  color: #2e7d32;
}

.purple {
  background-color: #f3e5f5;
  color: #6a1b9a;
}

</style> 