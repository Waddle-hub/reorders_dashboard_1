<template>
  <v-app id="Inspire" :style="{background : $vuetify.theme.themes.dark.background}">

    <v-container>

      <CallingSheetData />

      <CallingSheetDataDetail />

      
      <!-- 
        <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n8">
        <v-toolbar-title>Team Members</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn rounded small>
          Add Member
        </v-btn>
      </v-toolbar>

      <v-card class=" rounded-lg">
        <v-row>
        
          <v-col cols="12" sm="3">
            <v-list  subheader two-line> 
              <v-list-item>
                <v-badge
                  bordered
                  bottom
                  color="#49D9A0"
                  dot
                  offset-x="28"
                  offset-y="22">
                  <v-list-item-avatar >
                    <v-avatar size="40">
                      <v-img src="https://cdn.vuetifyjs.com/images/lists/2.jpg"></v-img>
                    </v-avatar>
                  </v-list-item-avatar>
                </v-badge>
                <v-list-item-content>
                  <v-list-item-title >AAE Ideapro</v-list-item-title>
                  <v-list-item-subtitle>32 Story point</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-col>
        </v-row>
      </v-card>
    -->
     

    </v-container>
  </v-app>
</template>

<script>
 // import SideBar from '@/components/SideBar.vue';
  import CallingSheetData from '@/components/CallingSheetData.vue';
  import CallingSheetDataDetail from '@/components/CallingSheetDataDetail.vue';

  export default {
    name: 'Home',

    data: () => ({
       toggle_exclusive: 1,
       option: {
         title : {
           text: "Burnson Chart",
           left: "Left"
         },
         tooltip : {
           trigger: "Item",
           formatter: "{a} <br/>{b} : {c} ({d}%)"
         },
         series : [
           {
             name: "Traffic Sources",
             type: "pie",
             radius: "55%",
             center: ["45%", "50%"],
             data:[
               { value:335, name:"Direct" },
               { value:435, name:"Stuff" },
               { value:535, name:"that" },
               { value:635, name:"has" },
               { value:135, name:"an" },
               { value:1035, name:"impact" },
               { value:835, name:"on" }
             ],
             emphasis: {
               itemStyle: {
                 shadowBlur:10,
                 shadowOffsetX:0,
                 shadowColor:"rgba(0,0,0,0)"
               }
             }
           }
         ]
       }
    }),

    components: {
    CallingSheetData,
    CallingSheetDataDetail
},
    methods: {

    },
  }
</script>

<style scoped>
 .space{
  margin-left: -100px;
  margin-right: -100px;
}
</style>
