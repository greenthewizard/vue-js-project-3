<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <li
                class="list-group-item"
                v-for="server in servers"
                :key="server.id"
                @click="selectServer(server)">
                Server #{{ server.id }}: Status - {{ server.status }}
            </li>
        </ul>
    </div>
</template>

<script>
import { EventBus } from '../../main';

export default {
    data: function () {
        return {
            servers: [
                { id: 1, status: 'Normal' },
                { id: 2, status: 'Normal' },
                { id: 3, status: 'Exquisite' },
                { id: 4, status: 'On Fire' }
            ]
        }
    },
    methods: {
        selectServer: function (server) {
            EventBus.$emit('updateCurrentServer', server);
        }
    }
}
</script>

<style>

</style>
