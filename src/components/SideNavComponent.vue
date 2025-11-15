<script setup>

    console.log("1.3 SideNav ready");

</script>

<template>

    <div>
        <ul id="sideNavUL">
            <li>
                <button type="button" class="sideNavButtons">Home</button>
            </li>
            <li>
                <button type="button" class="sideNavButtons">About</button>
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
        background-color: transparent;
        color: black;
        border: none;
        cursor: pointer;
    }

</style>