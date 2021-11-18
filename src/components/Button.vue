<template>
    <button @click="onClick()" :style="{ background: color }" >{{text}}</button>
</template>

<script>
export default {
    name: 'Button',
    props: {
        text: String,
        color: String
    },
    methods: {
        onClick() {
            this.$emit('toggle-add-task')
        }
    }
}
</script>

<style scoped>
button{
    border: none;
    background: #333;
    color: white;
    width: 90px;
    height: 35px;
    border-radius: 2px;
    margin-right: 20px;
    font-family: 'Poppins', sans-serif;
    font-weight: 500;
}
button:hover{
    opacity: 0.7;
    transition: 200ms;
}
</style>