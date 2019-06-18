<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">Please select a server.</p>
        <div v-else>
            <p>Id: {{ server.id }}</p>
            <p>Status: {{ server.status }}</p>
            <button @click="resetStatus">Change to normal</button>
        </div>
    </div>

</template>

<script>
    import { eventBus } from '../../main';

    export default {
        data: function() {
            return {
                server: null
            };
        },
        methods: {
            resetStatus() {
                this.server.status = "Normal";
            }
        },
        created() {
            eventBus.$on('load', (server) => {
                this.server = server;
            });
        }
    }
</script>

<style>

</style>
