<template>
  <div class="home">
    <v-container >
      <v-row  class="d-flex flex-row align-center" v-for="(item, index) in todos" :key="index">
        <v-checkbox  v-model="value" value="value"></v-checkbox>
        <span>{{item.title}}</span>
        <v-spacer></v-spacer>
        <v-btn color="error" >x</v-btn>
      </v-row>
    </v-container>
  </div>
</template>



<script>
export default {
  name:"home",
  components:{

  },
  data(){
    return{
     todos:[
       {id: 1 , title:"Task 1", completed:false},
       {id: 2 , title:"Task 2", completed:true},
       {id: 3 , title:"Task 3", completed:false},
     ]
    }
  },
};
</script>