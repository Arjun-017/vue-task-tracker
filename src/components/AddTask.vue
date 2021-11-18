<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
            <label for="text">Task</label>
            <input type="text" v-model="text" name="text" placeholder="Add Task " />
        </div>

        <div class="form-control">
            <label for="date">Day and Time</label>
            <input type="text" v-model="day" name="date" placeholder="Add Day and Time " />
        </div>

        <div class="form-control">
            <label for="reminder">Set Reminder</label>
            <input id="check" v-model="reminder" type="checkbox" name="reminder" placeholder="Add Reminder " />
        </div>
        <input type="submit" value="Save Task" class="submit" />
    </form>
</template>

<script>
export default {
    data() {
        return {
        text: '',
        day: '',
        reminder: false
    }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()
            if(!this.text) {
                alert('Please Add Task')
                return
            }
            const newTask = {
                text: this.text,
                day: this.day,
                reminder: this.reminder
            }
            console.log(newTask)

            this.$emit('add-task', newTask)

            this.text = ''
            this.day = ''
            this.reminder = false
        }
    
    }
    
}
</script>
    
<style scoped>
    .add-form{
        border: 2px solid #333;
        padding: 10px 20px;
        margin-bottom: 10px;
    }
    .form-control{
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 5px 0;
    }
    .form-control input{
        height: 25px;
        width: 50%;
        padding: 0 10px;
        font-size: 15px;
    }
    .submit{
        width: 100%;
        border: none;
        background: #333;
        color: white;
        border-radius: 2px;
        height: 35px;
        font-family: 'Poppins', sans-serif;
        font-weight: 500;
        font-size: 18;
    }

</style>