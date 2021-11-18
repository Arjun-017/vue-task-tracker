<template>
<div @dblclick="$emit('toggle-reminder',id)" :class="[reminder? 'reminder': 'not-reminder', 'task']">
<h3>{{text}} <i @click="$emit('delete-task',id)" class="fas fa-times"></i></h3>
<p>{{date}}</p>
</div>
</template>

<script>
export default {
    name: "Task",
    props: {
        text: String,
        date: String,
        id: Number,
        reminder: Boolean
    }
}
</script>

<style scoped>
 .task{
     background: #eee;
     margin: 5px 0;
     padding: 15px 20px 15px 10px;
 }
 .task h3{
     display: flex;
     justify-content: space-between;
 }
 .fas{
     color: firebrick;
     cursor: pointer;
 }
 .reminder{
     border-left: 5px solid green;
 }
 .not-reminder{
     border-left: 5px solid red;
 }
</style>