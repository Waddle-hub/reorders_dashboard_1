<template>
  <v-item-group mandatory class="mt-n2">
        <v-container>
          <v-row class="space">

            <v-col cols="5"  sm="2">

                    <v-item v-slot="{ active, toggle }" > 
                    <v-card 
                        style="background: linear-gradient(144deg,#AF40FF, #5B42F3 50%,#00DDEB)"
                        class="d-flex align-center rounded-xl"
                        dark
                        height="75"
                        @click="toggle">
                            <v-list-item three-line class="mt-3 ml-0.5">
                                <div class="mb-4">                     
                                    <v-icon  x-large :color="'white'">fa-solid fa-droplet</v-icon>                  
                                </div> 
                                <v-list-item-title class="headline mb-1" :class="active ? 'white--text' : 'black--text'">
                                    <a style="text-decoration : none; color: white" ><strong>Aquazania</strong></a>
                                </v-list-item-title>                        
                            </v-list-item>             
                        </v-card>
                    </v-item>
                    <v-btn id="todaydate" color="49D9a0" text class="ml-5">
                        {{currentDateTime()}}
                    </v-btn>
  
            </v-col>

            <v-col cols="10" md="9" sm="12">

                <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n2">
                    <v-toolbar-title><strong>Calls Left To Make</strong></v-toolbar-title>
                </v-toolbar>

                <b-table sticky-header hover small dark striped
                    :items="callslefttomake"
                    :fields="callingsheetfields"
                    >
                </b-table>

            </v-col>

          </v-row>

        </v-container>

      </v-item-group>

</template>

<script>
const axios = require('axios');

export default {
    data:() => ({
         callingsheetfields : [
             {
                key : 'delivery_date',
                label : 'Delivery Date',
             },
             {
                key : 'outstanding',
                label : 'Outstanding',
             },
             {
                key : 'confirmed',
                label : 'Confirmed',
             },
             {
                key : 'done',
                label : 'Done',
             },
             {
                key : 'acc_blocked',
                label : 'Acc Blocked',
             },
             {
                key : 'acc_inactive',
                label : 'Acc Inactive',
             },
             {
                key : 'total',
                label : 'Total',
             } 
 
         ],
         callslefttomake : [
         ],
         timer: null
    }),
    methods: {
      currentDateTime () {
        const current = new Date();
        const date = current.getFullYear()+' '+(current.toLocaleString('default', { month: 'short' }))+' '+ (current.getDate() > 9 ? current.getDate()  : '0' + current.getDate());
        const dateTime = date;

        return dateTime;
      },

      async getCallsLeftToMake () {
         const path = 'http://127.0.0.1:5000/callslefttomake';
         await axios.get(path)
            .then((res) => {
               console.log(res)
               this.callslefttomake = res.data;
            })
            .catch((error) => {
               console.error(error);
            })
      }
    },
    mounted () {
      this.timer = setInterval(() => {
         this.getCallsLeftToMake()
      }, 100000);
    }
}
</script>

<style>

</style>