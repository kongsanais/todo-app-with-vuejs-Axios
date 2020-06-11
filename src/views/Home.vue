<template>
  <div class="home">
    <v-container>
      <AddTask @onSubmit="AddTaskForm" />
      <TaskList :todos="todos" />
    </v-container>
  </div>
</template>

<script>
import TaskList from "@/components/TaskList.vue";
import AddTask from "@/components/AddTask.vue";

export default {
  name: "home",
  components: { TaskList, AddTask },
  methods: {
    AddTaskForm(value) {
      this.todos.push({
        id: Math.random,
        title: value,
        completed: false,
      });
    },
  },
  data() {
    return {
      todos: [
        { id: 1, title: "Task 1", completed: false },
        { id: 2, title: "Task 2", completed: true },
        { id: 3, title: "Task 3", completed: false },
      ],
    };
  },
};
</script>

