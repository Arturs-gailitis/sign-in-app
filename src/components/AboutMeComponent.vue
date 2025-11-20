<script setup>

const info = {
    name: "Artūrs Gailītis",
    ID: "IT23005",
    email: "arturs.gailitis@va.lv"
}

console.log("5.2 AboutMe rendered");

</script>

<template>
    <div id="aboutMe">
        <h1 id="title">About Me</h1>
        <ul id="list">
            <li>Name: {{ info.name }}</li>
            <li>Email: {{ info.email }}</li>
            <li>ID: {{ info.ID }}</li>
        </ul>
    </div>

</template>

<style scoped>
    #aboutMe {
        display: block;
        position: relative;
        justify-self: center;
        height: 613px;
        width: 83rem;
        margin-top: -30px;
        margin-bottom: -10px;
        margin-right: -260px;
        margin-left: -60px;
        background-color: #DCCCFFff;
    }

    #title {
        justify-self: center;
        position: relative;
        top: 200px;
    }

    #list li {
        padding-top: 20px;
    }

    #list {
        position: relative;
        justify-self: center;
        top: 200px;
        list-style-type: none;
    }
</style>