<script setup>

    import { computed, ref, watch } from 'vue';

    const emit = defineEmits(["loginStatus"]);

    const isLoged = ref(false);
    const username = ref("");
    const password = ref("");
    const messageStatuss = ref(false);

    const emptyFields = computed(() => {
        if (username.value == "" || password.value == "") {
            return true;
        } else {
            return false;
        }
    })

    watch(emptyFields, () => {
        if (emptyFields.value !== false) {
            console.log("2.3 Login button disabled state reflects validity");
        }
    })

    function login() {
        if (username.value == "arturs.gailitis@va.lv" && password.value == "IT23005") {
            isLoged.value = true;
            emit("loginStatus", isLoged.value);
            console.log("2.4 Login success");
            messageStatuss.value = false;
        } else {
            isLoged.value = false;
            emit("loginStatus", isLoged.value);
            console.log("2.4 Login failed");
            messageStatuss.value = true;
        }
    }

    const prop = defineProps({
        login: Boolean
    });

    watch(() => prop.login, (newLoged) => {
        if (newLoged == false) {
            username.value = "";
            password.value = "";
            console.log("6.2 Login form reset");
        }
    })

</script>

<template>
    <div id="container" v-if="!isLoged">
        <form id="login">
            <h1 id="Title">Login</h1>
            <p id="messageStatus" v-if="messageStatuss">Login failed</p>
            <div class="labelInput">
                <label for="username">Username: <input type="text" id="username" v-model="username" name="username"></label>
            </div>
            <div class="labelInput">
                <label for="password">Password: <input type="password" id="password" v-model="password" name="password"></label>
            </div>
            <button type="button" @click="login" v-bind:disabled="emptyFields">Login</button>
        </form>
    </div>

</template>

<style scoped>

    #container {
        display: flex;
        justify-self: center;
        align-items: center;
        height: 150px auto;
        background-color: #FEC842ff;
        padding-left: 25px;
        padding-right: 25px;
        padding-bottom: 50px;
    }

    .labelInput {
        margin: 5px;
        display: flex;
        color: black;
        justify-self: center;
    }

    #Title {
        color: black;
        text-align: center;
    }

    #login button {
        margin-top: 25px;
        display: flex;
        justify-self: center;
        cursor: pointer;
    }

    #messageStatus {
        color: black;
        text-align: center;
    }

</style>