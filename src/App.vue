<template>
  <div class="container">
    <app-header></app-header>
    <hr>
    <div class="row">
      <app-servers serverName3="serverGroup1" status3="Critical" memUse3="16G" strogeUse3="100G"></app-servers>
      <app-servers serverName3="serverGroup2" v-bind:status3="status" memUse3="16G" strogeUse3="100G"></app-servers>
      <app-servers serverName3="serverGroup3" 
        v-bind:status3="status" 
        v-bind:memUse3="memUse"
        strogeUse3="100G"
        v-on:isMoreMenory3="memUse = $event">
      </app-servers>
      <app-servers 
        serverName3="serverGroup4" 
        status3="Normal" 
        memUse="16G"
        v-bind:strogeUse3="strogeUse" 
        v-bind:moreStroge3="moreHDD">
      </app-servers>
      <app-server-details status2="NOT OK2" v-on:isRestartAll="status = $event"></app-server-details>
    </div>
    <hr>
    <app-footer></app-footer>
  </div>
</template>

<script>
  import Header from './share/Header.vue'
  import Footer from './share/Footer.vue'
  import Servers from './server/Servers.vue'
  import ServerDetails from './server/ServerDetails.vue'

  export default {
    data: function() {
      return {
        status: 'down',
        memUse: '16G',
        strogeUse: '100G'
      }
    },
    methods: {
      moreHDD: function() {
        this.strogeUse3 = '200G'
      }
    },
    components: {
      'app-header': Header,
      'app-servers': Servers,
      'app-server-details': ServerDetails,
      'app-footer': Footer
    }
  }

</script>

<style>

</style>
