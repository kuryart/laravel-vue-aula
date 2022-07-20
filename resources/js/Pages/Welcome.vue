<template>
    <div class="top-navbar">
        <div class="left">
            <n-image
                @click="home"
                width="100"
                src="/images/LogoFocusBlack.svg"
                preview-disabled
                class="clickable"
            />
            <div>Sobre nós</div>
            <div>Serviço</div>
            <div>Contato</div>
        </div>
        <div class="right">
            <div>teste</div>
            <div>teste1</div>
        </div>
    </div>
</template>

<script setup>
import { NImage } from "naive-ui";
import AppLayout from "@/Layouts/AppLayout.vue";

function home() {
    console.log("home");
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@700&display=swap");

.top-navbar {
    display: flex;
    justify-content: space-between;
    font-family: "Josefin Sans", sans-serif;
    font-size: 20px;
    color: #222222;
    padding: 5vh;
}

.left {
    display: flex;
    justify-content: space-around;
}

.right {
    display: flex;
    justify-content: space-around;
}

/* body {
    background: #333;
} */

.clickable {
    cursor: pointer;
}
</style>
