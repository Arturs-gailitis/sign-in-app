<script setup>

    console.log("1.2 Header ready");

    defineProps({
        background: String
    })

</script>

<template> 

    <div id="navBar" :style="{ 'background-color': background }">
        <div id="header">
            <img src="../pictures/logo.svg" id="logo"></img>
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

</style>