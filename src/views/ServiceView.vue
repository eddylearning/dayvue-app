<!-- <template>
  <div class="parent">
    <h1 class="title">Our Services</h1>

    <div class="card-grid">
      <div class="card" v-for="post in posts" :key="post.id">
        <h3>{{ post.id }}. {{ post.title }}</h3>
        <p>{{ post.body }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ServiceView",

  mounted(){
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then(response => response.json())
      .then(data => this.posts = data)
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "Web Development",
          body: "We build modern, responsive, and SEO-friendly websites tailored to your needs.",
        },
        {
          id: 2,
          title: "Mobile Applications",
          body: "Custom iOS and Android apps designed to bring your ideas to life.",
        },
        {
          id: 3,
          title: "Event Management",
          body: "We help organize and manage events that leave lasting impressions.",
        },
        {
          id: 4,
          title: "Digital Marketing",
          body: "Grow your business with targeted campaigns and online visibility.",
        },
        {
          id: 5,
          title: "Branding & Design",
          body: "We craft unique brand identities and visuals that connect with your audience.",
        },
        {
          id: 6,
          title: "Consulting",
          body: "Expert guidance to help your business grow and adapt in the digital world.",
        },
      ],
    };
  },
};
</script>

<style scoped>
.parent {
  padding: 20px;
  font-family: Arial, sans-serif;
}

.title {
  text-align: center;
  font-size: 28px;
  font-weight: bold;
  margin-bottom: 20px;
  color: #42b983;
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}

.card {
  border: 1px solid #ddd;
  background: #fafafa;
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.08);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.card h3 {
  margin: 0 0 10px;
  color: #333;
  font-size: 20px;
}

.card p {
  margin: 0;
  font-size: 15px;
  color: #444;
  line-height: 1.5;
}
</style>  -->

                   <!--below is try catch error-->
<!-- 
<template>
  <div class="parent">
    <h1 class="title">Our Services</h1>

    <div class="card-grid">
      <div class="card" v-for="post in posts" :key="post.id">
        <h3>{{ post.id }}. {{ post.title }}</h3>
        <p>{{ post.body }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ServiceView",

  async mounted() {
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/posts');
      const data = await response.json();
      this.posts = data;
    } catch (error) {
      console.log(error);
    }
  },

  data() {
    return {
      posts: [
        {
          id: 1,
          title: "Web Development",
          body: "We build modern, responsive, and SEO-friendly websites tailored to your needs.",
        },
        {
          id: 2,
          title: "Mobile Applications",
          body: "Custom iOS and Android apps designed to bring your ideas to life.",
        },
        {
          id: 3,
          title: "Event Management",
          body: "We help organize and manage events that leave lasting impressions.",
        },
        {
          id: 4,
          title: "Digital Marketing",
          body: "Grow your business with targeted campaigns and online visibility.",
        },
        {
          id: 5,
          title: "Branding & Design",
          body: "We craft unique brand identities and visuals that connect with your audience.",
        },
        {
          id: 6,
          title: "Consulting",
          body: "Expert guidance to help your business grow and adapt in the digital world.",
        },
      ],
    };
  },
};
</script>

<style scoped>
.parent {
  padding: 20px;
  font-family: Arial, sans-serif;
}

.title {
  text-align: center;
  font-size: 28px;
  font-weight: bold;
  margin-bottom: 20px;
  color: #42b983;
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}

.card {
  border: 1px solid #ddd;
  background: #fafafa;
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.08);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.card h3 {
  margin: 0 0 10px;
  color: #333;
  font-size: 20px;
}

.card p {
  margin: 0;
  font-size: 15px;
  color: #444;
  line-height: 1.5;
}
</style> -->




                      <!--todos-->
<template>
  <div class="parent">
    <h1 class="title">User Todos</h1>

    <div v-if="error" class="error">{{ error }}</div>

    <div class="card-grid" v-else>
      <div class="card" v-for="todo in todos" :key="todo.id">
        <h3>{{ todo.id }}. {{ todo.title }}</h3>
        <p>Status: <strong :class="{'done': todo.completed, 'pending': !todo.completed}">
          {{ todo.completed ? 'Completed' : 'Pending' }}
        </strong></p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "TodoView",

  data() {
    return {
      todos: [],
      error: null
    };
  },

  async mounted() {
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/users/1/todos');
      if (!response.ok) {
        throw new Error(`HTTP error! status: ${response.status}`);
      }
      const data = await response.json();
      this.todos = data;
    } catch (err) {
      console.error(err);
      this.error = "Failed to fetch todos. Please try again later.";
    }
  }
};
</script>
<style scoped>
.parent {
  padding: 20px;
  font-family: Arial, sans-serif;
}

.title {
  text-align: center;
  font-size: 28px;
  font-weight: bold;
  margin-bottom: 20px;
  color: #42b983;
}

.error {
  color: #d9534f;
  background-color: #f2dede;
  border: 1px solid #ebccd1;
  padding: 12px;
  border-radius: 6px;
  margin-bottom: 20px;
  text-align: center;
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}

.card {
  border: 1px solid #ddd;
  background: #fafafa;
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.08);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.card h3 {
  margin: 0 0 10px;
  color: #333;
  font-size: 18px;
}

.card p {
  margin: 0;
  font-size: 15px;
  color: #444;
}

.done {
  color: green;
}

.pending {
  color: red;
}
</style>




