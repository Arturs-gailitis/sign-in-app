<script>

    console.log("1.2 Header ready");

</script>

<template> 

    <div id="header">
        <div>
            <img src="../pictures/logo.svg" id="logo"></img>
        </div>
    </div>

</template>

<style scoped>

    #header {
        display: flex;
        align-items: center;
        padding: 1rem;
        background-color: blue;
    }

    #logo {
        max-height: 50px;
        max-width: 50px;
        height: auto;
        width: auto;
    }

</style>