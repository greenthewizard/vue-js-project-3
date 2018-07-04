<template>
    <div class="container">
        <app-header></app-header>
        <hr>
        <div class="row">
            <app-servers></app-servers>
            <app-server-details :currentServer="currentServer">
            </app-server-details>
        </div>
        <hr>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import Header from './components/Shared/Header.vue';
    import Footer from './components/Shared/Footer.vue';
    import Servers from './components/Server/Servers.vue';
    import ServerDetails from './components/Server/ServerDetails.vue';
    import { EventBus } from './main';

    export default {
        components: {
            appHeader: Header,
            appServers: Servers,
            'app-server-details': ServerDetails,
            'app-footer': Footer
        },
        data: function () {
            return {
                currentServer: null
            }
        },
        created: function () {
            EventBus.$on('updateCurrentServer', server => {
               this.currentServer = server;
            });
        }
    }
</script>

<style>

</style>
