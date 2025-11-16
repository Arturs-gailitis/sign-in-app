<script setup>

const info = {
    name: "John Pork",
    ID: "IT2468",
    email: "john.Pork@example.com"
}

console.log("5.2 AboutMe rendered");

</script>

<template>
    <div id="aboutMe">
        <h1 id="title">About Me</h1>
        <ul id="list">
            <li>Name Surname: {{ info.name }}</li>
            <li>Studen ID: {{ info.ID }}</li>
            <li>Student Email: {{ info.email }}</li>
        </ul>
    </div>

</template>

<style scoped>
    #aboutMe {
        display: flex;
        flex-direction: column;
        justify-content: center;
        margin-left: 600px; 
        margin-top: 100px;
    }

    #title {
        padding-left: 100px;
    }

    #list li {
        padding-top: 20px;
    }

    #list {
        list-style-type: none;
    }
</style>