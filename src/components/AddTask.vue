<template>
  <v-container grid-list-xs>
    <v-row align="center" justify="center">
      <v-col cols="6" md="4">
        <v-text-field name="name" label="Task" id="id" v-model="taskInput">
        </v-text-field>
      </v-col>
      <v-col cols="6" md="2">
        <v-btn @click="AddTask" color="success">Add</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "AddTask",
  methods: {
    AddTask() {
      this.$emit("onSubmit", this.taskInput);
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
