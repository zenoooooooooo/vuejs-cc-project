<template>
    <component :is="tag" :class="CustomSectionClass" v-bind="$attrs">
        <slot></slot>
    </component>
</template>
<script>

export default {
    name: "CustomSection",
    props: {
        tag: {
            type: String,
            default: 'div'
        },
        CustomSectionClass: String
    }
}
</script>
<style scoped>

</style>