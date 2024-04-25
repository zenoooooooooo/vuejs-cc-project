<template>
    <button @click="handleClick" :class="btnClass">{{ text }}</button>
</template>

<script>
export default {
    name: 'CustomButton',
    props: {
        text: {
            type: String,
            default: "Click"
        },
        btnClass: String,
        onClick: Function
    },
    methods: {
        handleClick() {
            this.onClick()
        }
    }
}

</script>

<style scoped>

</style>