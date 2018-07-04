<template>
    <div class="col-xs-12 col-sm-6">
        <template v-if="!currentServer">
            <p>Server Not Selected</p>
        </template>
        <template v-else>
            <p>Server ID: {{ currentServer.id }}</p>
            <p>Server Status: {{ currentServer.status }}</p>
        </template>
    </div>

</template>

<script>
    export default {
        props: [
            "currentServer"
        ]
    }
</script>

<style>

</style>
