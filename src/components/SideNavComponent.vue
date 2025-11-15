<script>

    console.log("1.3 SideNav ready");

</script>

<template>

    <div>
        <ul id="sideNav">
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
    #sideNav {
        display: flex;
        list-style-type: none;
        gap: 40px;
        margin: 0;
        padding: 0;
    }

    .sideNavButtons {
        padding: 5px 10px;
        background-color: darkblue;
        color: white;
        border: 1px solid black;
        cursor: pointer;
    }

</style>