<template>
    <header>
        <h1>{{ title }}</h1>
        <CustomButton btnClass="button" :onClick="addButton" />
    </header>
</template>

<script>
import CustomButton from "./CustomButton.vue"

export default {
    name: "Header",
    components: {
        CustomButton
    },
    props: {
        title: {
            type: String,
            default: "Hello World"
        }
    },
    methods: {
        addButton() {
            console.log("Task Added")
        }
    }
}
</script>

<style scoped>
* {
    margin: 25px;
}

header {
    text-align: center;
    color: blue;
    display: flex;
    justify-content: center;
}

.button {
    padding: 20px;
    width: 100px;
    border: none;
    color: white;
    border-radius: 10%;
    background-color: blue;
    font-weight: bold;
    transition: 250ms;
}

.button:hover {
    opacity: 0.7;
}

.button:active {
    opacity: 0.5;
}
</style>