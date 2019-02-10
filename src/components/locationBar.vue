<template>
    <div id="locationBar">
        <label for="select">Location filter: </label>
        <select id="select"
                v-bind:value="locationSelection"
                v-on:input="$emit('updateOptions', $event.target.value)">
            <option disabled value="">Please select one</option>
            <option v-for="option in locationOptions" v-bind:value="option">
                {{option}}
            </option>
        </select>
    </div>
</template>

<script>

    const locationOptions = [
        "USA",
        "Canada",
        "Mexico",
        "Italy",
        "Nippon"
    ]
    export default {
        name: "locationBar",
        props: ["locationSelection"],
        data: function () {
            return {
                locationOptions: locationOptions,
            }
        },
    }
</script>

<style scoped>

</style>