<template>
    <div id="Results">
        <button class="btn btn-light" style="margin: 5px;" v-on:click="back">Go Back</button>
        <div id="results-shelf-container" style="text-align: center; margin-top: 5%;">
            <img id="results-shelf" src="../assets/acamedia-results.png" style="display: inline-block;">
        </div>
        <div id="labItems">
            <lab-item v-bind:go-to-lab-view="goToLabView" v-for="lab in queryResponse" v-bind:lab="lab"></lab-item>
            <h2 v-if="!queryResponse || queryResponse.length <=0">No Results :(</h2>
        </div>
    </div>
</template>

<script>
    import LabItem from "../components/labItem";
    export default {
        name: "Results",
        components: {LabItem},
        props: ["switchLabView", "queryResponse", "back"],

        methods: {
            goToLabView: function (lab) {
                this.switchLabView(lab)
            }
        },
    }
</script>

<style scoped>
    html, body {
        height: 100%;
        margin: 0;
        padding: 0;
    }

</style>