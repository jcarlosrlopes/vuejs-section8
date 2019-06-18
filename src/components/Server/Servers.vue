<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <app-server-item v-for="server in servers" :key="server.id" :server="server"></app-server-item>
        </ul>
    </div>
</template>

<script>
    import ServerItem from './ServerItem.vue'

    export default {
        data: function() {
            return {
                servers: [
                    { id: 1, status: 'Normal'},
                    { id: 2, status: 'Critical'},
                    { id: 3, status: 'Unknown'},
                    { id: 4, status: 'Busy'},
                    { id: 5, status: 'Unstable'}
                ]
            };            
        },
        components: {
            'app-server-item': ServerItem
        }
    }
</script>

<style>

</style>
