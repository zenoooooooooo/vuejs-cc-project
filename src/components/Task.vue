<template>
    <CustomSection tag="li" :CustomSectionClass="`task ${task.reminder ? 'reminder' : ''}`" @dblclick="$emit('toggle-reminder', task.id)">
     <h3>{{ task.text }} <i class="fas fa-times" @click="$emit('delete-task', task.id)">
                <div class="deleteMessage">Delete</div>
            </i></h3>
        <p>{{ task.description }}</p>

    </CustomSection>
</template>
<script>
import CustomSection from './CustomSection.vue';
import CustomButton from "./CustomButton.vue"
export default {
    name: 'Task',
    props: {
        task: Object,
    },
    components: {
        CustomSection,
        CustomButton
    }
}
</script>
<style scoped>
.task {
    background: #f4f4f4;
    padding: 10px 20px;
    list-style: none;
}
.reminder {
    border-left: solid 5px green;
}
h3 {
    display: flex;
    justify-content: space-between;
}

.fas {
    cursor: pointer;
    color: red;
}

.deleteMessage {
    position: absolute;
    padding: 15px;
    display: none;
    background-color: red;
    color: white;
    border-radius: 10%;
}

.fas:hover .deleteMessage {
    display: block;
}
</style>