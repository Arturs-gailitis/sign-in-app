<script setup>

    import { ref } from 'vue';

    const emit = defineEmits(['loginStatus']);

    const isLoged = ref(false);
    const username = ref('');
    const password = ref('');

    function login() {
        if (username.value == 'arturs.gailitis@va.lv' && password.value == 'IT12345') {
            console.log("2.4 Login success!");
            isLoged.value = true;
            emit('loginStatus', isLoged.value);
        } else {
            console.log("2.4 Login failed!");
            isLoged.value = false;
            emit('loginStatus', isLoged.value);
        }
    }

</script>

<template>
    <div id="container" v-if="!isLoged">
        <form id="login">
            <h1 id="Title">Login</h1>
            <div class="labelInput">
                <label for="username">Username: <input type="text" id="username" v-model="username" name="username"></label>
            </div>
            <div class="labelInput">
                <label for="password">Password: <input type="password" id="password" v-model="password" name="password"></label>
            </div>
            <button type="button" @click="login">Login</button>
        </form>
    </div>

</template>

<style scoped>

    #container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 150px auto;
        background-color: blue;
        padding-left: 25px;
        padding-right: 25px;
        padding-bottom: 50px;
    }

    .labelInput {
        margin: 5px;
        display: flex;
        color: white;
        justify-content: center;
    }

    #Title {
        color: white;
        text-align: center;
    }

    #login button {
        margin-top: 25px;
        margin-left: 45%;
        display: flex;
        justify-content: center;
        cursor: pointer;
    }

</style>