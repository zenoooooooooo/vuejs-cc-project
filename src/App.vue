
<template>
  <div class="container">
    <Header title="Tasks" />
    <Tasks :tasks="tasks" @delete-task="deleteTask" @toggle-reminder="toggleReminder" />
  </div>
  <main>

  </main>
</template>

<script>
import { Header, Tasks } from "./components"

export default {
  name: 'App',
  data() {
    return {
      tasks: []
    }
  },
  methods: {
    deleteTask(id) {
      if (confirm("Are you sure you want to delete this task?")) {
        this.tasks = this.tasks.filter(task => task.id !== id)
      }
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map(task => task.id === id ? { ...task, reminder: !task.reminder } : task);
    }

  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Learn HTML",
        reminder: true,
        description: "The initial step of learning Web Development is to learn HTML"
      },
      {
        id: 2,
        text: "Learn CSS",
        reminder: false,
        description: "After learning HTML, you have to learn CSS to style it"
      },
      {
        id: 3,
        text: "Learn JavaScript",
        reminder: false,
        description: "In order to give your webpage a behavior, you need to learn JavaScript"
      },
      {
        id: 4,
        text: "Learn a front-end framework",
        reminder: false,
        description: "A front-end framework will make the work faster and easier"
      },
      {
        id: 5,
        text: "Learn NodeJS",
        reminder: false,
        description: "This is where the back-end side begins"
      }
    ]
  },
  components: {
    Header,
    Tasks
  }
}
</script>

<style scoped></style>
