<template>
<div class="container">
  <Header @toggle-add-task="toggleAddTask" :addTaskBtn = "showAddTask" />
  <router-view :showaddtask="showAddTask" ></router-view>
  <Footer />
</div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';

export default {
  name: "App",
  components: {
    Header,
    Footer
  },
  data(){
    return {
      showAddTask: false
    }
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask
    },
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500&display=swap');
*{
  margin:0;
  padding:0;
}
.container{
  font-family: 'Poppins', sans-serif;
  margin: 100px auto;
  border: 2px solid black;
  width: 500px;
  position: relative;
  padding: 20px 25px;
}
</style>
