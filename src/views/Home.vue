<template>
  <div class="home">
    <v-container >
  
   <v-card
    class="mx-auto"
    color="green"
    dark
    max-width="800"
    >
    <v-card-title> 
    <v-icon large color="blue darken-2" style="margin-right:10px">mdi-message-text</v-icon>

      <span class="title font-weight-light">List of Task</span>
    </v-card-title>

    <v-card-text class="headline font-weight-bold">
              <v-row  class="d-flex flex-row align-center" v-for="(item, index) in todos" :key="index">
        <v-checkbox  v-model="value" value="value"></v-checkbox>
        <span>{{item.title}}</span>
        <v-spacer></v-spacer>
        <v-btn color="error" >x</v-btn>
      </v-row>
    </v-card-text>

    <v-card-actions>
      <v-list-item class="grow">

        <v-list-item-content>
          <v-img
            class="elevation-6"
            src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
          >
          </v-img>
          <v-list-item-title>Hatsanai</v-list-item-title>
        </v-list-item-content>

        <v-row
          align="center"
          justify="end"
        >
          <span class="mr-2">Total : </span>
          <span class="subheading mr-2">256</span>
        </v-row>

        
      </v-list-item>
    </v-card-actions>
  </v-card>

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