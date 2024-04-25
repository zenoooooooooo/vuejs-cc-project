<template>
    <CustomSection tag="ul" CustomSectionClass="container">
        <Task :key="task.id" v-for="task in tasks" :task="task" @delete-task="$emit('delete-task', task.id)"
            @toggle-reminder="$emit('toggle-reminder', task.id)" />
    </CustomSection>
</template>
<script>
import CustomSection from "./CustomSection.vue";
import Task from "./Task.vue"

export default {
    name: 'Tasks',
    props: {
        tasks: Array,
    },
    components: {
        CustomSection,
        Task
    },
    emits: ["delete-task", "toggle-reminder"]
}
</script>
<style scoped>
.container {
    max-width: 60vw;
    margin: auto;
}

img {
    width: 100vw;
}
</style>