<template>
    <v-row>
        <v-col cols="12">
          <v-row :align="alignment" :justify="justify" class="grey lighten-5">
            <v-card color="#26c6da" dark width="950px">
              <v-card-title>
                <v-icon class="pa-1" large dark>view_list</v-icon>
                <span class="title font-weight-light">List</span>
              </v-card-title>

              <v-card-text class="headline font-weight-bold">
                <v-row
                  class="d-flex flex-row align-center"
                  v-for="(item, index) in todos"
                  :key="index"
                >
                  <v-checkbox v-model="value" value="value"></v-checkbox>
                  <span>{{ item.title }}</span>
                  <v-spacer></v-spacer>
                  <v-btn color="error">x</v-btn>
                </v-row>
              </v-card-text>

              <v-card-actions>
                <v-list-item class="grow">
                  <v-list-item-avatar color="grey darken-3">
                    <v-img
                      class="elevation-6"
                      src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
                    ></v-img>
                  </v-list-item-avatar>

                  <v-list-item-content>
                    <v-list-item-title>Kong Hatsanai</v-list-item-title>
                  </v-list-item-content>

                  <v-row align="center" justify="end">
                    <span class="subheading mr-2">Total : </span>
                    <span class="subheading mr-2">256</span>
                  </v-row>
                </v-list-item>
              </v-card-actions>
            </v-card>
          </v-row>
        </v-col>
        <v-col cols="12">
          <v-row justify="center">
            <v-col cols="6" md="4">
              <v-select
                v-model="alignment"
                :items="alignmentsAvailable"
                label="Align"
              ></v-select>
            </v-col>

            <v-col cols="6" md="2">
              <v-select
                v-model="justify"
                :items="justifyAvailable"
                label="Justify"
              ></v-select>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
</template>

<script>
export default {
    name: "TaskList",
    props:['todos'],
    data() {
        return {
      alignmentsAvailable: ["start", "center", "end", "baseline", "stretch"],
      alignment: "center",
      dense: false,
      justifyAvailable: [
        "start",
        "center",
        "end",
        "space-around",
        "space-between",
      ],
      justify: "center",
        }
    },

}
</script>

<style>

</style>