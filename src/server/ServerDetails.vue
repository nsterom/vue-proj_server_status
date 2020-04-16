<template>
    <div class="col-xs-12 col-sm-6">
        <p>{{ status2 }}</p>
        <button v-on:click="restartAll">restart all</button>
        <button v-on:click="restartAll2">restart all 2</button>
    </div>
    
</template>

<script>
import { eventBus } from '../main'

export default {
    props: {
        status2: String
    },
    methods: {
        restartAll: function() {
            this.status2 = 'Normal'
            // this.$emit('isRestartAll', this.status2)
        },
        restartAll2: function() {
            this.status2 = 'Normal2'
            eventBus.$emit('isRestartAll', this.status2)
        }
    }
}

</script>

<style>

</style>