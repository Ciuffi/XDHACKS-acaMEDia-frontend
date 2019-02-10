<template>
    <div id="toolbar">
        <nav class="navbar navbar-expand-lg navbar-light bg-light">
            <a class="toolbar-button" v-on:click="$emit('scroll-down', 'home')">Home</a>
            <a class="toolbar-button" v-on:click="$emit('scroll-down', 'about')">About</a>
            <a class="toolbar-button" v-on:click="$emit('scroll-down', 'contact')">Contact</a>
        </nav>
    </div>
</template>

<script>
    export default {
        name: "toolbar"
    }
</script>

<style scoped>
    #toolbar{
    }

</style>