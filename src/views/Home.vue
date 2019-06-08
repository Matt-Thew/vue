<template>
  <div id="app">
    <!-- <Datepicker></Datepicker> -->
    <!-- <Tabletest></Tabletest> -->
    <Order></Order>
  </div>
</template>

<script>

import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'
import { CardPlugin } from 'bootstrap-vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Alerttest from '../components/Alert'
import Tabletest from "../components/Tabletest"
import Datepicker from "../components/Datepicker"
import Order from "../components/Order"
Vue.use(BootstrapVue)


export default {
  name: 'home',
  components: {
    Alerttest,
    Tabletest,
    Datepicker,
    Order,
  },

}
</script>

<style>
</style>
