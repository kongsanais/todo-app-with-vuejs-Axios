<template>
  <v-container grid-list-xs>
    <v-row align="center" justify="center">
      <v-col cols="6" md="4">
        <v-text-field name="name" label="Task" id="id" @keyup.enter="AddTasks" v-model="taskInput">
        </v-text-field>
      </v-col>
      <v-col cols="6" md="2">
        <v-btn @click="AddTasks" color="success">Add</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { uuid } from 'vue-uuid'; 
export default {
  name: "AddTask",
  methods: {
    AddTasks() {
    
      let task = {
        id: uuid.v1(),
        title: this.taskInput,
        completed: false,
      }

      this.$emit("onSubmit", task);
      this.taskInput = "";
    },
  },
  data() {
    return {
      taskInput: "",
    };
  },
};
</script>

<style></style>
