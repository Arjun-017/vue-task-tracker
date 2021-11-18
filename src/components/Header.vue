<template>
<header>
    <h1>Task Tracker</h1>
    <Button v-show="homePage" @toggle-add-task="$emit('toggle-add-task')" :text="addTaskBtn?'Cancel': 'Add Task'" :color="addTaskBtn?'red':'green'" />
</header>
</template>

<script>
import Button from './Button.vue'

    export default {
        name: "Header",
        components: {
            Button
        },
        props: {
            addTaskBtn: Boolean
        },
        computed: {
            homePage() {
                if(this.$route.path === '/'){
                    return true
                }
                else {
                    return false
                }
            }
        }
    }
</script>

<style scoped>
header{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 40px;
}
h1{
    font-size: 30px;
    font-weight: 500;
    width: 50%;
}
</style>