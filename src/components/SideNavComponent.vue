<script setup>

    import { ref } from 'vue';

    console.log("1.3 SideNav ready");

    const homeStatus = ref(false);
    const aboutStatus = ref(false);
    const homeButtonColour = ref("white");
    const aboutButtonColour = ref("white");

    const emit = defineEmits(["homeStatus", "aboutStatus"]);

    function clickHome() {
        homeStatus.value = true;
        console.log("4.1 Navigate: Home");
        emit("homeStatus", homeStatus.value);
        homeStatus.value = false;
        homeButtonColour.value = "#56C2B8ff";
        aboutButtonColour.value = "white";
    }

    function clickAbout() {
        aboutStatus.value = true;
        console.log("4.2 Navigate: About");
        emit("aboutStatus", aboutStatus.value);
        aboutStatus.value = false;
        homeButtonColour.value = "white";
        aboutButtonColour.value = "#56C2B8ff";
    }

</script>

<template>

    <div>
        <ul id="sideNavUL">
            <li>
                <button type="button" class="sideNavButtons" @click="clickHome" 
                    v-bind:style="{ 'background-color': homeButtonColour }">Home</button>
            </li>
            <li>
                <button type="button" class="sideNavButtons" @click="clickAbout" 
                    v-bind:style="{ 'background-color': aboutButtonColour }">About Me</button>
            </li>
        </ul>
    </div>

</template>

<style scoped>
    #sideNavUL {
        display: inline-block;
        position: absolute;
        margin-left: 20px;
        list-style: none;
    }

    .sideNavButtons {
        margin-bottom: 20px;
        cursor: pointer;
        background-color: white;
    }

</style>