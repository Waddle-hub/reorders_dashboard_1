<template>
    <v-container >
        <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n10">
        <v-toolbar-title>Active Calling Sheets</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn rounded small>
            See All
            </v-btn>
        </v-toolbar>

        <b-table hover light striped dark
            :items="callslefttomake"
            :fields="callingsheetfields"
            >
        </b-table>
    </v-container>
</template>

<script>
const axios = require('axios');

export default {
    data : () => ({
        callingsheetfields : [
             {
                key : 'calling_sheet_name',
                label : 'Calling Sheet Name',
             },
             {
                key : 'delivery_date',
                label : 'Delivery Date',
             },
             {
                key : 'total',
                label : 'Total',
             },
             {
                key : 'complete_percentage',
                label : 'Completed',
             },
             {
                key : 'invoiced',
                label : 'Invoiced',
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
             }
         ],
         callslefttomake : [ 

         ],
         timer: null
    }),
    methods : {
      async getCallingSheetData  () {
         const path = 'http://127.0.0.1:5000/callingsheetdatadetail';
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
         this.getCallingSheetData()
      }, 10000);
    },

}
</script>

<style>

</style>