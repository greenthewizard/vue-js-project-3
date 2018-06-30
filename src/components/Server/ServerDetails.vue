<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!currentServer">Server Not Selected</p>
        <p v-else>Server ID: {{ currentServer }}</p>
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
