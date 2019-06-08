<template>
  <div class="container shadow p-3 mb-5 bg-white rounded">
    <b-table
      selectable
      :select-mode="selectMode"
      selectedVariant="success"
      :items="items"
      @row-selected="rowSelected"
    ></b-table>

    {{ selected }}

<button v-on:click="getOrder('2019-06-04', '2019-06-06','processing',3,20)">getOrder</button>
  </div>
</template>

<script>
import { async } from 'q';
const axios = require('axios');

function getOrder(){
  const filterOrder = {
      dateFrom: "2019-06-04",
      dateTo: "2019-06-06",
      status: "processing",
      page: 3,
      limit: 20
  };
  var url = "https://www.indexlivingmall.com/webservice/dotcom_customer/getOrder";
  const filterJSON = JSON.stringify(filterOrder);
  const formData = new FormData();
  formData.append('filter', filterJSON);
  return axios.post(url, formData).then(function(response){
          return response.data;
        }).catch(function(error){console.log(error)})
}


  export default {
    data() {
      return {
        modes: ['multi'],
        items: [
          { isActive: true, age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
          { isActive: false, age: 21, first_name: 'Larsen', last_name: 'Shaw' },
          { isActive: false, age: 89, first_name: 'Geneva', last_name: 'Wilson' },
          { isActive: true, age: 38, first_name: 'Jami', last_name: 'Carney' }

        ],
        selectMode: 'multi',
        orderCollection: [],
        selected: []
      }
    },
    methods: {
      rowSelected(items) {
        this.selected = items
      },
    getOrder: function(username, password) {

        const filterOrder = {
            dateFrom: "2019-06-04",
            dateTo: "2019-06-06",
            status: "processing",
            page: 3,
            limit: 20
        };
        var url = "https://www.indexlivingmall.com/webservice/dotcom_customer/getOrder";
        const filterJSON = JSON.stringify(filterOrder);
        const formData = new FormData();
        formData.append('filter', filterJSON);
        return axios.post(url, formData).then((response) => {

            console.log(response.data);
            this.items = response.data
          }
        ).catch(function(error){console.log(error)})


      }
      
    }
  }
</script>