<template>
    <div id="Results">
        <div id="results-shelf-container" style="text-align: center; margin-top: 5%;">
            <img id="results-shelf" src="../assets/acamedia-results.png" style="display: inline-block;">
        </div>
        <div id="labItems">
            <lab-item v-bind:go-to-lab-view="goToLabView" v-for="lab in queryResponse" v-bind:lab="lab"></lab-item>
            <h2 v-if="!queryResponse">No Results :(</h2>
        </div>
    </div>
</template>

<script>
    import LabItem from "../components/labItem";
    export default {
        name: "Results",
        components: {LabItem},
        props: ["switchLabView", "queryResponse"],

        methods: {
            goToLabView: function (lab) {
                this.switchLabView(lab)
            }
        },
    }
</script>

<style scoped>

</style>