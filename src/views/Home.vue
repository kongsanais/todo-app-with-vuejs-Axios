<template>
  <div class="home">
    <v-container>
      <AddTask @onSubmit="AddTaskForm" />
      <TaskList  @onRemove="RemoveTaskForm" :todos="todos" />

      <v-row align="center" justify="center" >
         <img
         class="mt-10" 
         src="@/assets/logo.png" alt="">
      </v-row>
     
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
    AddTaskForm(task) {
      this.todos.push(task);
    },
    RemoveTaskForm(id){
      this.todos = this.todos.filter(item=> item.id !== id )
    }
  },
  data() {
    return {
      todos: [
        { id: 1, title: "Task 1", completed: false },
        { id: 2, title: "Task 2", completed: true },
        { id: 3, title: "Task 3", completed: false }
      ],
    };
  },
};
</script>

