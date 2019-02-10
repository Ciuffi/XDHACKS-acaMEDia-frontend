<template>
    <div id="labItem">
        <button v-on:click="back">back</button>
        <h2>{{lab.name}}</h2>
        <div id="data">
            <p>Lab Location: {{lab.location}}</p>
            <p>Person Name: {{lab.person.name}}</p>
            <p style="padding-left: 5%">Person Email: {{lab.person.email}}</p>
            <div id="articleItem" v-for="article in lab.articles">
                <p>Article Name: {{article.title}}</p>
                <p>Article Date: {{formatDate(article.date)}}</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "labView",
        props: ["lab", "back"],
        methods:{
            formatDate: function (date) {
                return date.toJSON().slice(0, 10);
            }
        }
    }
</script>

<style scoped>
    #data{
        border: 2px solid black;
        -webkit-border-radius: 5px;
        -moz-border-radius: 5px;
        border-radius: 5px;
        padding-left: 5%;
        margin-bottom:5%;
    }
    #articleItem{
        border: 2px solid red;
        -webkit-border-radius: 5px;
        -moz-border-radius: 5px;
        border-radius: 5px;
        padding-left: 5%;
    }
</style>