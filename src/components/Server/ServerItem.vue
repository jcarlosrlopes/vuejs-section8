<template>        
    <li class="list-group-item" @click="serverSelected(server)">
        Server #{{ server.id }}
    </li>    
</template>

<script>
    import { eventBus }  from '../../main';

    export default {        
        props: ['server'],
        methods: {
            serverSelected(server) {
                eventBus.$emit('load', server);
            }
        }
    }
</script>

<style>
</style>



