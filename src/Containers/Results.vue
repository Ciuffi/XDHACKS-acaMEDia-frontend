<template>
    <div id="Results">
        <h1>Results</h1>
        <div id="labItems">
            <lab-item v-bind:go-to-lab-view="goToLabView" v-for="lab in queryResponse" v-bind:lab="lab"></lab-item>
        </div>
    </div>
</template>

<script>
    import LabItem from "../components/labItem";
    export default {
        name: "Results",
        components: {LabItem},
        props: ["switchLabView"],

        methods: {
            goToLabView: function (lab) {
                this.switchLabView(lab)
            }
        },
        data: function () {
            return {
                queryResponse: [
                    {
                        name: "lab1",
                        location: "vancouver",
                        url: "https://google.com",
                        articles: [
                            {
                                title: "article1",
                                date: new Date()
                            },
                            {
                                title: "article2",
                                date: new Date()
                            }
                        ],
                        person: {
                            name: "Fabio Rossi",
                            email: "fa"
                        }
                    },
                    {
                        name: "lab2",
                        location: "Sierra",
                        url: "https://google.ca",
                        articles: [
                            {
                                title: "article3",
                                date: new Date()
                            },
                            {
                                title: "article5",
                                date: new Date()

                            }
                        ],
                        person: {
                            name: "Austin Koby",
                            email: "austin@austin.com"
                        }
                        },
                ]
            }
        }
    }
</script>

<style scoped>

</style>