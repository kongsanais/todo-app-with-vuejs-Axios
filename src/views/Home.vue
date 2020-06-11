<template>
  <div class="home">
    <v-container>
      <AddTask @onSubmit="AddTaskForm" />
      <TaskList @onRemove="RemoveTaskForm" :todos="todos | reversed" />

      <v-row align="center" justify="center">
        <img class="mt-10" src="@/assets/logo.png" alt="" />
      </v-row>
    </v-container>
  </div>
</template>

<script>
import TaskList from "@/components/TaskList.vue";
import AddTask from "@/components/AddTask.vue";
import axios from "axios";

export default {
  name: "home",
  computed: {
    reversedTodo() {
      return this.todos.slice().reverse();
    },
  },
  filters: {
    reversed(value) {
      return value.slice().reverse();
    },
  },
  components: { TaskList, AddTask },
  async mounted() {
    let result = (this.todos = await axios.get(
      "https://jsonplaceholder.typicode.com/todos"
    ));
    this.todos = result.data;
  },
  methods: {
    async AddTaskForm(task) {
      let result = await axios.post(
        "https://jsonplaceholder.typicode.com/todos",
        task
      );
      alert(JSON.stringify(result.data));
      this.todos.push(task);
    },
    RemoveTaskForm(id) {
      axios
        .delete("https://jsonplaceholder.typicode.com/todos/" + id)
        .then(result => {
          alert(JSON.stringify(result.data));
          this.todos = this.todos.filter((item) => item.id !== id);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  data() {
    return {
      todos: [],
      todos_mockup: [
        { id: 1, title: "Task 1", completed: false },
        { id: 2, title: "Task 2", completed: true },
        { id: 3, title: "Task 3", completed: false },
      ],
    };
  },
};
</script>
