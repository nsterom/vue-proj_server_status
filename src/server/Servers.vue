<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <li class="list-group-list">
                {{ switchServerName() }}: {{ status3 }} {{ memUse3 }} {{ strogeUse3 }}
                <button @click="restart">Restart</button>
                <button @click="moreMemory">more menory</button>
                <button @click="moreStroge3">more stroge</button>
            </li>
        </ul>
    </div>
</template>

<script>
import { eventBus } from '../main'

export default {
    props: {
        serverName3: {
            type: String,
            required: true
        },
        status3: {
            type: String,
            required: true
        },
        memUse3: {
            type: String
        },
        strogeUse3: {
            type: String
        },
        moreStroge3: Function()
    },
    methods: {
        switchServerName: function() {
            return this.serverName3.toUpperCase()
        },
        restart: function() {
            this.status3 = 'normal'
        },
        moreMemory: function() {
            this.memUse3 = '64G'
            this.$emit('isMoreMemory', this.memUse)
        }
    },
    created() {
        eventBus.$on('isRestartAll', (status) => {
            console.log('--------------------------' + status)
            this.status3 = status
        })
    }
}

</script>

<style>

</style>