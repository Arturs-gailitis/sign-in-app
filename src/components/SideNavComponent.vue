<script setup>

    import { ref } from 'vue';

    console.log("1.3 SideNav ready");

    const homeStatus = ref(false);
    const aboutStatus = ref(false);

    const emit = defineEmits(["homeStatus", "aboutStatus"]);

    function clickHome() {
        homeStatus.value = true;
        console.log("4.1 Navigate: Home");
        emit("homeStatus", homeStatus.value);
        homeStatus.value = false;
    }

    function clickAbout() {
        aboutStatus.value = true;
        console.log("4.2 Navigate: About");
        emit("aboutStatus", aboutStatus.value);
        aboutStatus.value = false;
    }

</script>

<template>

    <div>
        <ul id="sideNavUL">
            <li>
                <button type="button" class="sideNavButtons" @click="clickHome">Home</button>
            </li>
            <li>
                <button type="button" class="sideNavButtons" @click="clickAbout">About Me</button>
            </li>
        </ul>
    </div>

</template>

<style scoped>
    #sideNavUL {
        display: flex;
        list-style-type: none;
        gap: 40px;
        margin: 0;
        padding: 0;
        margin-right: 50px;
    }

    .sideNavButtons {
        padding: 5px 10px;
        background-color: green;
        color: black;
        border: 1px solid green;
        cursor: pointer;
    }

</style>