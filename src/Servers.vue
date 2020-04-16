<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <li class="list-group-list">
                {{ switchServerName() }} # {{ index }}: {{ status }} {{ menUse }}
                <button @click="restart">Restart</button>
                <button @click="restart2">Restart2</button>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        serverName: {
            type: String,
            required: true
        },
        status: {
            type: String,
            required: true
        }
    },
    methods: {
        switchServerName: function() {
            return this.serverName.toUpperCase()
        },
        restart: function() {
            this.status = 'normal'
        },
        restart2: function() {
            this.status = 'super health'
            this.$emit('isRestart', this.status)
        }
    }
}

</script>

<style>

</style>