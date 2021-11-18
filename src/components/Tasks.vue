<template>
    <div :key="task.id" v-for="task in tasks">
        <Task @toggle-reminder = "$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :text="task.text" :date="task.day" :reminder="task.reminder" :id="task.id" />
    </div>
</template>

<script>
import Task from './Task.vue'
    export default{
        name: 'Tasks',
        props: {
            tasks: Array
        },
        components: {
            Task
        },
        emits: ['delete-task', 'toggle-reminder']
    }
</script>