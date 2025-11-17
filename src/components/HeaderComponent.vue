<script setup>

    console.log("1.2 Header ready");

    const props = defineProps({
        background: String,
        statuss: Boolean
    })

    const emit = defineEmits(["LogoutStatus"]);
    let newStatuss;

    function logOut() {
        if (props.statuss == true) {
            newStatuss = false;
            console.log("6.1 Logout");
            console.log("6.2 Login form reset");
        }
        emit("LogoutStatus", newStatuss);
    }

</script>

<template> 

    <div id="navBar" v-bind:style="{ 'background-color': background }">
        <div id="header">
            <img src="../pictures/logo.svg" id="logo"></img>
        </div>
        <div id="logout">
            <button type="button" id="logoutButton" v-if="props.statuss" @click="logOut">Log out</button>
        </div>
    </div>

</template>

<style scoped>

    #navBar {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 1rem;
        height: 70px;
    }

    #logo {
        max-height: 50px;
        max-width: 50px;
        height: auto;
        width: auto;
    }

    #logout {
        display: flex;
        position: relative;
        right: 10%;
    }

    #logoutButton {
        background-color: #874FFFff;
        cursor: pointer;
        height: auto;
        padding: 5px;
        padding-left: 5px;
        padding-right: 5px;
    }

</style>